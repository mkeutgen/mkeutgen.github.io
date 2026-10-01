+++
title   = "Unpacking AI Weather Emulators: What and How Do They Learn?"
kicker  = "Workshop notes — IMSI, University of Chicago (28 September – 2 October 2026)"
deck    = "Three talks on what autoregressive emulators of the atmosphere and ocean actually learn: whether they separate CO₂ from sea-surface temperature, how to make them conserve what the physics conserves, and where scientific machine learning tends to fail."
date    = "2026-09-29"
tags    = ["machine-learning", "emulation", "climate", "weather", "ocean-modelling", "IMSI"]
author  = "Maxime Keutgen De Greef"
toc     = true
draft   = true
+++

The Institute for Mathematical and Statistical Innovation (IMSI) workshop brought
together applied mathematicians, statisticians, atmospheric scientists and
computer scientists around one question: when an AI emulator reproduces the
atmosphere or the ocean, what has it actually learned? These notes cover three
talks.

---

## CO₂ versus sea-surface temperature in ACE2 — Chris Bretherton (Ai2)

_Talk title: "AI2's Climate Emulators: What do we do when they don't learn the right thing?"_

### What ACE2 is

ACE2 is the second version of the Ai2 Climate Emulator (ACE), an autoregressive
neural network that steps the global atmosphere forward in time. Compared with
the first version, it represents the stratosphere explicitly, predicts the
shortwave (SW) and longwave (LW) radiative fluxes at the top of the atmosphere
(TOA), and exchanges fluxes with the surface. It is forced by prescribed
sea-surface temperature (SST) and atmospheric CO₂.

### The problem: CO₂ and SST are confounded in the training data

In the historical record, CO₂ and surface temperature both rise. ACE2 learns a
positive correlation between them. But they are different variables with
different physical effects, and the historical period cannot tell them apart.

The future can. Many scenarios in the Coupled Model Intercomparison Project
Phase 7 (CMIP7) contain periods where CO₂ falls while temperature keeps rising.
An emulator that has merely learned "more CO₂ goes with warmer surface" will get
those periods wrong.

The same confound affects Atmospheric Model Intercomparison Project (AMIP)
runs — atmosphere-only simulations forced by observed SST. Any warming trend in
such a run could come from CO₂ or from SST, and the emulator has to attribute it
correctly.

### Three physical tests

The proposed diagnostics are borrowed from the Cloud Feedback Model
Intercomparison Project (CFMIP), where they are standard tests for physical
climate models:

1. **Increase CO₂ with SST held fixed.** The expected response is a small
   surface warming over land, a cooling of the stratosphere, and a change in
   the TOA radiation balance — the radiative forcing.
2. **Warm the SST uniformly by +4 K with CO₂ fixed.** This isolates the
   atmospheric response to ocean warming, and its pattern of surface warming.
3. **Abruptly quadruple CO₂ (abrupt-4xCO₂) with a coupled ocean.** This tests
   the full coupled response, not just the atmospheric piece.

Passing these tests is what qualifies ACE2 as the atmospheric component of a
coupled Earth system model (ESM) used for anthropogenically forced climate change.

---

## Building ocean emulators — Laure Zanna (NYU)

### Why emulate the ocean

The bottleneck in ocean and climate modelling is **time to solution**:
calibration and spin-up require running a model for thousands of simulated years.
Autoregressive (AR) emulators — networks that predict the next state from the
current one, then feed their own output back in — offer several advantages:

- They are not bound by the Courant–Friedrichs–Lewy (CFL) condition, the
  stability limit that ties a numerical model's time step to its grid spacing.
- They need no spin-up.
- They do not need to carry every variable, or the full spatial resolution.
- They may be easier to train directly on observations.

In return they give long simulations, large ensembles, broad access for users
without supercomputers, and a cheap way to explore mechanisms and "what if"
experiments across scales.

Samudra[^samudra] is the group's fully AI ocean emulator.

### Challenge 1: out-of-distribution forcing and trends

The test period contains only a small amount of warming. The emulator has seen
some warming during training, but possibly not enough to extrapolate. Open
questions: does it need more data, or is the forced signal simply too small
relative to variability?

{{< sidenote >}}My own hypothesis: the issue may be the rollout length rather than the
data volume. Training uses windows of roughly 40 days, which is short compared with
the time scale over which a forced trend emerges.{{< /sidenote >}}

### Challenge 2: minimizing physical inconsistencies

Three approaches, in increasing order of difficulty:

- **Global conservation** in the loss function, or as a hard constraint. ACE
  and CAMulator[^camulator] do this. It has various failure modes, and can be
  combined with training on more datasets.
- **Rebuild the fluxes from the emulator state** (not too hard). Demonstrated
  with an ocean emulator trained on the Community Earth System Model version 2
  (CESM2) 1%-per-year CO₂ increase experiment (1pctCO2).
- **Local conservation by learning the fluxes** (hard). Instead of predicting the
  next state directly, the network predicts each term of the tendency and the
  budget is closed in every grid cell. This is still difficult for the ocean
  state. For sea ice it works: FloeNet, by Will Gregory[^floenet], tracks the
  training data much better, with no extra constraint in the loss — local physical
  conservation comes from the structure of the prediction itself.

### Challenge 3: multiscale forcing and shortcut learning

In idealized models, emulators can learn shortcuts: they latch onto a forcing
signal that is easy to predict rather than the multiscale dynamics that produce
the response. Distinguishing the two is an open problem.

---

## Foundations and failure modes of scientific ML — Michael Mahoney (UC Berkeley)

_Talk title: "Some Thoughts on Foundations of AI Weather Emulators and Scientific Machine Learning"_

### Foundations and implementations

Papers cited in the talk:

- On foundations: the implicit biases introduced by design choices in time-series
  foundation models[^ts-biases]. Worth reading.
- On implementations: neural scaling laws for weather emulation under continual
  training[^scaling], and zero-shot forecasting from models trained on simulation
  alone[^zeroshot].

The talk framed these results as a "bitter sweet lesson" — a play on Sutton's
"bitter lesson" that general methods leveraging computation beat hand-built
structure.

### Failure modes of scientific machine learning

Three families of methods, each with a documented failure mode:

- **Physics-informed neural networks (PINNs)**, which add the residual of a
  differential equation to the loss, can fail to train even on simple problems
  because the physics term makes the optimization landscape hard[^pinns].
- **Neural ordinary differential equations (neural ODEs)** do not automatically
  learn a continuous model of continuous physics; what they learn depends on how
  they are discretized and trained[^node].
- **Neural operators**, often advertised as resolution-independent, do not deliver
  zero-shot super-resolution: evaluating them at a resolution they were not
  trained on does not give accurate fine-scale output[^operators].

---

## References

[^samudra]: Dheeshjith, S., et al. (2025). Samudra: An AI global ocean emulator for climate. *Geophysical Research Letters*. _(volume and DOI to be filled in)_

[^camulator]: Chapman, W. E., et al. (2025). CAMulator. _(full citation to be filled in)_

[^floenet]: Gregory, W., et al. FloeNet. _(full citation to be filled in)_

[^ts-biases]: Understanding the implicit biases of design choices for time series foundation models. _(authors and venue to be filled in)_

[^scaling]: On neural scaling laws for weather emulation through continual training. _(authors and venue to be filled in)_

[^zeroshot]: Zero-shot forecasting by simulation alone. _(authors and venue to be filled in)_

[^pinns]: Krishnapriyan, A. S., Gholami, A., Zhe, S., Kirby, R. M., & Mahoney, M. W. (2021). Characterizing possible failure modes in physics-informed neural networks. *Advances in Neural Information Processing Systems*, 34.

[^node]: Krishnapriyan, A. S., Queiruga, A. F., Erichson, N. B., & Mahoney, M. W. (2023). Learning continuous models for continuous physics. *Communications Physics*. _(volume and DOI to be filled in)_

[^operators]: On the false promise of zero-shot super-resolution in machine-learned operators. _(authors and venue to be filled in)_
