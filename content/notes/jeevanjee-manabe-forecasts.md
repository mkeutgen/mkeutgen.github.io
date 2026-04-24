+++
title = "What Can We Learn from Manabe's Climate Forecasts?"
kicker = "Seminar notes — Nadir Jeevanjee (Geophysical Fluid Dynamics Laboratory, GFDL)"
deck = "Five specific predictions made by Syukuro Manabe's early climate models — from CO₂ sensitivity to delayed Southern Ocean warming — and why their confirmation, decades later, is the strongest answer to persistent model skepticism."
date = "2026-04-24"
tags = ["climate", "climate-models", "manabe", "gfdl", "seminar-notes"]
author = "Maxime Keutgen De Greef"
toc = true
+++

## Context

Talk by Nadir Jeevanjee (GFDL, Princeton). Jeevanjee opened by noting
that Syukuro ("Suki") Manabe's 2021 Nobel Prize in Physics is widely
associated with radiative–convective equilibrium (RCE), but that this
framing undersells what the prize really celebrates: a sequence of very
specific, quantitative climate forecasts made decades ago and since borne
out by observations. The talk's purpose — and why Jeevanjee now gives it
often, including to non-specialist audiences — is to make that case
explicitly.

## Motivation: persistent skepticism of climate models

The United States Department of Energy (DOE) Climate Working Group
(2025)[^doe2025] wrote:

> The world's several dozen global climate models offer little guidance on
> how much climate responds to elevated CO₂. Overly sensitive models yield
> exaggerated projections of future warming.

Steven Koonin's *Unsettled*[^koonin2021] voices a similar line — "too
many tuned models" — and William Happer has pressed the same argument.
Jeevanjee told us he has spoken with Happer directly, and the exchange
left him asking a sharper question: *why* do we trust climate models? We
must have reasons; what is the skeptics' camp missing?

The standard response is a figure like "natural + anthropogenic forcing,
observations versus the Coupled Model Intercomparison Project (CMIP)
phases 3 and 5 multi-model means": the ensemble mean tracks the
observed global temperature well.

But there are wrinkles. Out-of-the-box models do *not* reproduce
observations. Matching the instrumental record requires tuning
(Mauritsen & Roeckner, 2020[^mauritsen2020]). It is not an a priori
match.

Surely we have more than this?

Jeevanjee's answer: yes. What follows are **five forecasts** that early
climate models got right — made decades before their observational
confirmation.

## From weather to climate: the founding of GFDL

The transition from weather to climate modelling has Princeton roots.
John von Neumann pursued numerical weather prediction (NWP) at the
Institute for Advanced Study (IAS) under J. Robert Oppenheimer's
direction. Using Jule Charney's quasi-geostrophic (QG) equations, his
group ran the first numerical weather forecasts.

{{< sidenote >}}Manabe told Jeevanjee that the Wikipedia page on von
Neumann is well worth reading — "a visionary."{{< /sidenote >}}

The technology transferred quickly to operational NWP. The climate idea
then follows naturally: run a weather model indefinitely on a global
domain, collect statistics, and *that* is the climate. Von Neumann's
seven-page proposal led to the founding of GFDL. Joseph Smagorinsky —
who had worked with both von Neumann and Charney — was chosen as its
first director.

## The building blocks of a climate model

A climate model needs an atmosphere model and an ocean model, coupled,
integrated long enough to close Earth's energy balance:

$$ \text{absorbed sunlight} \;=\; \text{emitted infrared (IR) radiation}. $$

Smagorinsky recruited a radiation expert from Germany _(name to be
filled in)_ with the explicit goal of testing the radiation scheme
inside a full global model.

The simplified radiation picture: sunlight enters the atmosphere;
greenhouse gases (GHGs) absorb outgoing IR and re-emit it downward.
Something else must carry heat upward — convection, and more broadly
atmospheric dynamics. The heart of a climate model is the *coupling*
between the greenhouse effect and convection.

Manabe's 1967 paper with Wetherald[^manabe1967] encoded this in a
one-dimensional radiative–convective column. With a tuned albedo, it
reproduced the observed surface temperature. But Manabe did not stop
there — he used the model as an instrument for experiments. It already
had the key knobs: CO₂ concentration, clouds, water vapour, ozone. He
ran what we would now call an ablation study.

---

## Forecast 1 — Global warming from doubled CO₂

In one section of the 1967 paper, Manabe doubled CO₂. Global-average
surface temperature rose by **≈ 2.9 °C** — remarkably close to today's
central estimate of equilibrium climate sensitivity.

Manabe's "special sauce":

- he accounted for convection;
- he represented water vapour, CO₂, ozone, and the greenhouse effect
  realistically;
- he held **relative humidity** fixed. This single choice encapsulates
  the water-vapour feedback. Fixing *absolute* humidity instead would
  have halved the predicted warming.

## Forecast 2 — Stratospheric cooling

The 1-D model also emulated the vertical structure of the stratosphere
at different levels and predicted broad cooling of the upper atmosphere
near 25 km altitude. _(original reference to be filled in.)_

Observations confirm this. Santer et al. (2023)[^santer2023] report a
cumulative stratospheric cooling of about **−2.2 °C**, consistent with
the ~8–10 K cooling per CO₂ doubling implied by the 1-D model.

## Forecast 3 — Arctic amplification

Manabe's Model II coupled a quasi-global atmosphere to a slab ocean
(half land, half sea, coarse resolution). Despite the crudeness, it
produced Arctic amplification, the correct height-versus-latitude
structure of warming, and again stratospheric cooling.

At low latitudes it gave 6–7 K of warming; Arctic warming was predicted
to be roughly **three times the global average**.

Zhou et al. (2024)[^zhou2024] — "Steady threefold Arctic amplification
of externally forced warming masked by natural variability" — confirm
the factor, decades after the prediction.

Consequences: sea-ice loss in the tens of percent, and downstream
geopolitical implications for Arctic shipping routes.

## Forecast 4 — Land–ocean warming contrast

Manabe III added a global atmosphere–ocean model with realistic
continents (≈ 4–5° resolution). In 1991 the group ran transient CO₂
forcing.

Prediction: the ocean warms ~1 °C relative to a 1980 baseline while
land warms ~1.5 °C. Wallace and Joshi (2018)[^wallace2018] confirmed
this ~30 years later.

## Forecast 5 — Delayed Southern Ocean warming

Manabe, Stouffer, Spelman, and Bryan (1991)[^manabe1991] predicted a
delayed warming response in the Southern Ocean. Observational
confirmation: _(reference to be filled in)_.

---

## Summary

| # | Forecast | Predicted | Confirmed |
|---|---|---|---|
| 1 | Global warming from CO₂ doubling (≈ 2.9 °C) | 1967 | consensus today |
| 2 | Stratospheric cooling | 1967 | 2023 |
| 3 | Arctic amplification (~3× global) | 1975 | 2009 / 2024 |
| 4 | Land–ocean warming contrast | 1991 | 2018 |
| 5 | Delayed Southern Ocean warming | 1991 | _(to be filled in)_ |

Five early, specific predictions — not post-hoc fits — that have since
been borne out. This, Jeevanjee argues, is the case for trusting climate
models that the skeptical literature tends to step around.

---

[^doe2025]: United States Department of Energy Climate Working Group (2025). _(full citation to be filled in.)_

[^koonin2021]: Koonin, S. E. (2021). *Unsettled: What Climate Science Tells Us, What It Doesn't, and Why It Matters*. BenBella Books.

[^mauritsen2020]: Mauritsen, T., & Roeckner, E. (2020). Tuning the MPI‑ESM1.2 global climate model to improve the match with instrumental record warming by lowering its climate sensitivity. *Journal of Advances in Modeling Earth Systems*, 12(5), e2019MS002037.

[^manabe1967]: Manabe, S., & Wetherald, R. T. (1967). Thermal equilibrium of the atmosphere with a given distribution of relative humidity. *Journal of the Atmospheric Sciences*, 24(3), 241–259. _(The talk referred to this as "the 1966 paper"; the standard citation is 1967.)_

[^santer2023]: Santer, B. D., et al. (2023). Exceptional stratospheric contribution to human fingerprints on atmospheric temperature. _(full citation to be filled in.)_

[^zhou2024]: Zhou, W., et al. (2024). Steady threefold Arctic amplification of externally forced warming masked by natural variability. _(full citation to be filled in.)_

[^wallace2018]: Wallace, J. M., & Joshi, M. (2018). Land–sea warming contrast under increasing CO₂. _(full citation to be filled in.)_

[^manabe1991]: Manabe, S., Stouffer, R. J., Spelman, M. J., & Bryan, K. (1991). Transient responses of a coupled ocean–atmosphere model to gradual changes of atmospheric CO₂. Part I: Annual mean response. *Journal of Climate*, 4(8), 785–818.
