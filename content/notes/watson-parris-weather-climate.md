+++
title   = "Weather and climate are worlds apart"
kicker  = "Seminar notes — Duncan Watson-Parris (Scripps Institution of Oceanography and Halıcıoğlu Data Science Institute, UC San Diego), M²LInES seminar series"
deck    = "Why a machine-learning model that forecasts weather well is not thereby a climate model — and a concrete proposal for how to score the ones that claim to be."
date    = "2026-09-02"
tags    = ["machine-learning", "climate", "weather", "emulation", "benchmarking", "M2LInES"]
author  = "Maxime Keutgen De Greef"
toc     = true
+++

**Opening claim:** weather is an initial-value problem; climate is not. A model that
excels at propagating an initial state forward for ten days has not, by that fact,
demonstrated anything about its response to a forcing applied over decades.

---

## Where the uncertainty actually lives

Decomposing the uncertainty in a projection into internal variability, model
uncertainty and scenario uncertainty — the classic partition of Hawkins and
Sutton, applied to emissions-driven projections[^watson-parris-2021] — gives a
clear time dependence:

- **2020 to 2040:** dominated by internal variability and **model** uncertainty.
- **From ~2040 onward:** **scenario** uncertainty takes over.

Model uncertainty here means aerosol–cloud interactions, cloud feedbacks, and the
like. Scenario uncertainty is a different animal: it is not a deficiency of the
model, it is that we do not know what humans will emit. No amount of model
improvement removes it.

{{< sidenote >}}Worth being explicit about, because emulator papers routinely report skill
in the 2020–2040 window — exactly the window where model error, the thing an emulator
inherits wholesale from its training model, is the dominant term.{{< /sidenote >}}

---

## What are we actually emulating?

A useful taxonomy, ordered by how much of the host model is replaced:

1. **Learned initial estimate** — a better starting guess, solver otherwise untouched.
2. **Derived quantity** — skip the state entirely and predict the diagnostic actually
   wanted.
3. **Subcomponent** — one physics term inside the solver: radiation, convection,
   microphysics.
4. **Component** — a whole model of one part of the coupled system (Samudra for the
   ocean, or a boundary-layer scheme).
5. **Full model replacement** — end to end. The only option when no host model will
   run, the fastest, and the hardest to verify.

The verification difficulty rises monotonically down that list, and so does the
appetite for building them.

---

## ClimateBench v1, and why it was too easy

The task: given a set of emissions, predict temperature change. It began as a
hackathon for a workshop, with a split consensus on whether it was tractable.

It turned out to be a fairly easy task — **linear models do a good job**. Follow-up
work has pushed on explainability, multi-fidelity approaches, and physical
constraints, including linear-model baselines[^lutjens-2025] and flow
matching.[^irvin-2025] Spatiotemporal pyramid flow matching separates *flow time*
from *physical time*, which is the interesting structural idea there.

---

## A physically constrained emulator

Start from a Finite-amplitude Impulse Response (FaIR)-style model, where the
temperature response is built from a sum of exponentially relaxing boxes:

$$
\frac{dS_i(t)}{dt} \;=\; q_i\,F(t) \;-\; \frac{S_i(t)}{d_i},
$$

with $S_i$ the response of box $i$, $q_i$ its sensitivity, $d_i$ its relaxation
timescale, and $F(t)$ the forcing. The forcing itself takes an assumed structural
form for each agent, from empirical relationships.

The move: **use this as the mean function of a Gaussian process**, with a white-noise
term for internal variability. The result

- retains the original physical formulation where no data is present, and
- provides a robust Bayesian route to adjusting it where data *are* present.

Evaluated on held-out future projections, the decomposition reads

$$
\underbrace{T(t)}_{\text{prior}} \;+\; \underbrace{\Delta T(t)}_{\text{posterior mean correction}}
\;=\; \underbrace{T(t)\,|\,\mathcal{D}}_{\text{posterior}} .
$$

---

## The real question: how do you test a climate model?

Nascent climate emulators are appearing quickly — LUCIE[^guan-2025] and
SamudrACE[^samudrace-2025] among them — and several large groups would like to claim
they have the best climate model. So: **how do we test one?**

We do not know the truth. That does not mean we know nothing. There is information in
the available observations that constrains the likelihood of different climate
outcomes, and — importantly — there is **more** information in the observations now
than there was 10–15 years ago.

---

## ClimateBench 2.0: probabilistic climate model scoring

**The task:** given a plausible future emissions pathway, what are the regional
temperature and precipitation changes in 2050 relative to 1990–2020?

This is a deliberately narrow view of what a climate model does, but it is a useful
and sizeable task, chosen for four reasons:

- **Transient, not equilibrium** — more policy-relevant, and easier to discern from
  observations.
- **Minimises baseline uncertainty** — measured relative to a well-observed late-20th-century state.
- Regional, so it is not trivially satisfied by getting global mean temperature right.
- **Verifiable within Duncan's career.**

### A three-tier scoring protocol

**Tier 1 — the physical entry ticket.** Sanity checks a model must pass before its
predictions are scored at all:

- Top-of-Atmosphere (TOA) energy balance closed to within $0.1\ \mathrm{W\,m^{-2}}$.
- Arctic amplification: the Arctic must warm more than 1.5× the global mean under
  CO₂ forcing.
- Land–ocean warming contrast: land warms 1.2–1.6× faster than ocean, from lower heat
  capacity and reduced evaporation.
- Coupled variability: an El Niño–Southern Oscillation (ENSO) check.

**Tier 2 — benchmarking against observations,** crucially on held-out data. Core
evaluation variables: 2 m temperature, temperature extremes, precipitation, TOA
radiative fluxes, sea ice, and sensible and latent heat fluxes. The train/test split
is temporal: **all observational data after 2015 are off-limits for training.**

**Tier 3 — out-of-distribution generalisation.** The ultimate test of predictive skill
is forecasting genuinely unseen climate states. Two routes:

*Paleoclimate targets*

| Period | Forcing | Response |
|---|---|---|
| Last Interglacial (127 ka) | Orbital | Strong high-latitude warming, reduced Arctic sea ice, smaller Greenland ice sheet (+0.5 K) |
| Last Glacial Maximum | CO₂ at 190 ppm | −5 to −7 K |
| Mid-Holocene ("green Sahara") | Orbital | Small $\Delta T$ |

*Perfect-model experiments,* for machine-learning models: train on one target Earth
System Model's (ESM) historical output, evaluate against that model's held-out future
simulation. Candidate hosts: CESM2, MPI-ESM, GISS ModelE2. A large-ensemble test
(>20 members, against the CESM Large Ensemble) checks the spread across
initial-condition perturbations under a common forced signal — which probes the
interaction of forcing with internal variability, not just the forced mean.

---

## JAX-GCM: fast adjoints without emulators

**The calibration problem.** Emulator-augmented Perturbed Parameter Ensembles (PPEs)
are currently the standard approach: run the full-complexity model across a range of
uncertain parameters to generate training data, fit an emulator, then do inference
over the emulator.

The cost of generating that training data is the bottleneck. And there is a subtler
issue: this procedure answers a different question from the one asked — it recovers
the **emulated** response, not the model's actual response.

**The alternative:** make the model itself differentiable.

JAX-GCM is a fully differentiable physical atmospheric model in Python, with gradients
from JAX for calibration and sensitivity analysis available out of the box.

- SPEEDY-based physics.
- Plug-and-play parametrisations, enabling flexible experimentation and online learning.
- Runs on CPU, GPU and TPU.
- Validated against the Fortran baseline.
- Includes a JAX aerosol module.

### Gradient-based calibration

Minimise a weighted misfit between observations and model output,

$$
\mathcal{L}(u) \;=\; \bigl\lVert\, R^{-1/2}\bigl(y - \mathcal{G}_\tau(u, z_0)\bigr) \,\bigr\rVert_2^2,
$$

where $\mathcal{G}_\tau$ is the expensive forward model integrated to time $\tau$,
$y$ the observations, $R$ the observational error covariance (so $R^{-1/2}$ weights
each observation by its precision), $z_0$ the initial state, and $u$ the uncertain
parameters — stratiform cloud albedo, the relative-humidity threshold, and maximum
entrainment.

Compared against ensemble methods, the gradient-based route shows **accelerated
convergence**, and the advantage is perturbation-size dependent: for a large
perturbation there is no need for a large ensemble, while the ensemble cost grows as
the perturbation shrinks. Composability — chaining differentiable components — is the
other structural benefit.

{{< sidenote >}}The point that the emulator answers a different question than the model
generalises well beyond calibration. It is the same objection as the one against scoring
an emulator only in the 2020–2040 window.{{< /sidenote >}}

---

## References

[^watson-parris-2021]: Watson-Parris, D., et al. (2021). _(full citation to be filled in)_ — emissions-driven uncertainty partition, after Hawkins, E., & Sutton, R. (2009). The potential to narrow uncertainty in regional climate predictions. *Bulletin of the American Meteorological Society*, 90(8), 1095–1107. <https://doi.org/10.1175/2009BAMS2607.1>

[^lutjens-2025]: Lütjens, B., et al. (2025). *Journal of Advances in Modeling Earth Systems* (JAMES). _(full citation to be filled in)_

[^irvin-2025]: Irvin, J., et al. (2025). Flow matching for climate emulation. _(full citation to be filled in)_

[^guan-2025]: Guan, H., et al. (2025). LUCIE: a lightweight stable climate emulator. *Journal of Advances in Modeling Earth Systems* (JAMES). _(volume and DOI to be filled in)_

[^samudrace-2025]: Duncan, J., et al. (2025). SamudrACE. *arXiv preprint*. _(arXiv identifier to be filled in)_
