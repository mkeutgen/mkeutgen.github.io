+++
title   = "Climate Controls on Weather Extremes: Studies of Heat, Rain and Drought"
kicker  = "PhD defense notes — Sofia Menemenlis (Princeton)"
deck    = "How global warming shapes physical weather hazards at the scales people live in — and what to do when observations, theory and models disagree."
date    = "2026-10-08"
tags    = ["extremes", "heat", "precipitation", "sea-surface-temperature", "hurricanes", "observational-uncertainty", "central-US"]
author  = "Maxime Keutgen De Greef"
toc     = true
draft   = true
+++

These are notes from Sofia Menemenlis's Final Public Oral (FPO), the public
PhD defense in Princeton's Program in Atmospheric and Oceanic Sciences. The
thesis has four parts: the 2023 global temperature spike, the slow warming of
the central United States, extreme rainfall from Hurricane Ida, and projected
dangerous heat exposure.

## Motivation: from global CO₂ to local hazards

The talk opened with carbon dioxide (CO₂) at four scales:

1. A reanalysis showing plumes of CO₂ in the atmosphere downwind of emitting
   regions.
2. The Mauna Loa record of atmospheric CO₂ concentration.
3. The same record extended back 10,000 years.
4. Deep-time analogues from Tierney et al. (2020).[^tierney] The closest
   analogue to today's CO₂ level is the Pliocene. Around 900 ppm corresponds
   to the early Eocene; around 1000 ppm to the mid-Cretaceous.

This is a global story. People experience climate change through local
weather: a heatwave in one city, a flood in one basin. The thesis asks:

> How does global warming influence physical weather hazards on the spatial
> and temporal scales relevant to humans?

### Three tools, and what happens when they disagree

Three tools are available to answer it:

- **Simple models** of one aspect of the climate system. They are useful and
  transparent, but they do not capture the complex interactions of the full
  system.
- **Observations.**
- **Numerical models**, chiefly General Circulation Models (GCMs). They allow
  controlled experiments and future projections, but they carry biases.

When all three agree, confidence is high. The interesting cases are those in
which they disagree.

## Part 1 — Did the 2023 temperature spike contradict models and theory?

Global mean surface temperature (GMST) jumped sharply in 2023. Press coverage
framed the jump as a heat anomaly that climate models could not explain. This
chapter asks a different question: is observational uncertainty alone large
enough to account for the apparent mismatch?

### How GMST is reconstructed

GMST combines land air temperature with sea surface temperature (SST). The
ocean part draws on satellite remote sensing, moored buoys, drifting buoys,
Argo floats and ships. Several groups produce independent reconstructions:

- **Global (land + ocean):** NASA Goddard, the UK Met Office, NOAA, Berkeley
  Earth, and the China Meteorological Administration.
- **SST:** the Japan Meteorological Agency, NOAA, and the UK Met Office.

### Two kinds of uncertainty

- **Parametric uncertainty** lives within one dataset. It comes from that
  dataset's own error model.
- **Structural uncertainty** is the systematic difference between datasets. It
  comes from different methodological choices made by each group.

Structural uncertainty is larger than parametric uncertainty. Including all
SST datasets, rather than one, widens the uncertainty range on the global
(land + ocean) temperature. A related paper documents how far satellite-era
SST trends differ across datasets.[^sst] Sofia is also a co-author on a study
attributing the 2023 spike to the El Niño–Southern Oscillation (ENSO).[^raghuraman]

## Part 2 — The hidden SST pattern effect on the central US

The central United States has warmed only moderately since the start of the
satellite era.

La Niña-like SST patterns, with a cooler tropical Pacific, favour drying and
warming over the central US. The observed SST pattern over recent decades has
been La Niña-like. Atmospheric General Circulation Models (AGCMs) forced with
observed SSTs therefore produce strong central US warming. The observed
warming sits at the very low end of the AGCM range.

In Sofia's seminar abstract on this work, the mechanism runs through the circulation: the SST
pattern shifts large-scale atmospheric circulation, which reduces springtime
precipitation, dries the surface, and increases sensible heating.[^centralus]

Two questions follow:

1. Why do observations warm more slowly than the models?
2. Will the observed trends continue?

### Models

- **GFDL AM2.1** (atmosphere only) and **CM2.1** (coupled atmosphere–ocean),
  from the Geophysical Fluid Dynamics Laboratory (GFDL).
- Roughly 200 km horizontal grid spacing.
- LM2 land model.
- Historical greenhouse gas and aerosol forcing.

### Findings

Coupled models are more likely to simulate the observed central US trend, but
for the wrong reason: they do not reproduce the observed SST pattern. Given
the observed SSTs, the moderate observed warming resembles an unlikely outcome
of internal atmospheric variability.

The SST pattern effect was hidden by internal variability in the past. It is
likely to become important in the future.

## Part 3 — Extreme rainfall risk in Hurricane Ida's aftermath

{{< sidenote >}}My notes on this part were brief. The details below follow the
published paper.{{< /sidenote >}}

In its extratropical stage, Hurricane Ida (2021) brought extreme sub-daily
rainfall and devastating flooding to eastern Pennsylvania, New Jersey and New
York.[^ida]

The study uses 31-member ensembles of hindcasts, each started from slightly
perturbed initial conditions. The model is T-SHiELD, GFDL's System for
High-resolution prediction on Earth-to-Local Domains: a 13 km global weather
model with a 3 km nested grid that resolves convection.

- At lead times up to 4 days, the ensembles capture the most extreme observed
  hourly and daily rainfall totals. They underestimate the spatial extent of
  heavy rainfall.
- In Ida's **tropical stage**, the spread in extreme hourly rainfall across
  ensemble members is well predicted by large-scale moisture convergence.
- In Ida's **extratropical stage**, the most extreme rainfall is governed by
  mesoscale processes that take chaotic and diverse forms across members.

The implication for preparedness: before an extratropical transition, plan
for severe localized impacts anywhere across a wide area.

## Part 4 — Projected increase in dangerous heat exposure

By mid-century, dangerous heat will reach millions of people.[^heat]

The heat metric combines temperature and humidity. The change in exposure
$\Delta E$ splits into three terms:

$$
\Delta E = \Delta E_{T_{\max}} + \Delta E_{\bar{q}} + \Delta E_{T_{\max} \times \bar{q}}
$$

Here $T_{\max}$ is daily maximum temperature and $\bar{q}$ is mean specific
humidity. The first term is the change from temperature alone, with humidity
held at its baseline. The second is the change from humidity alone. The third
is their interaction.

- **Humidity dominates:** 68% of the increase in population-weighted
  dangerous heat exposure is attributable to humidity.
- **Extremely dangerous heat** (heat index of 125 °F, about 52 °C, or more) was
  very rare in the 1990–2009 baseline. Only 3 facilities, all in southern
  Texas, saw more than 10 such days per year.
- **By mid-century**, exposure rises from 1.7 to 12.9 million person-days. The
  number of facilities exposed 10 or more days per year rises from 3 to 947.

## Summary

1. Structural differences between SST reconstructions widen the uncertainty
   on global temperature.
2. The moderate observed warming in the central US disagrees with the forced
   trends in AGCMs. Observed SSTs favour strong warming; history resembles an
   unlikely outcome of internal atmospheric variability.
3. Large-ensemble hindcasts identify the physical drivers of rainfall
   extremes: large-scale moisture convergence in Ida's tropical stage,
   mesoscale processes in its extratropical stage.
4. Humidity drives most of the projected increase in dangerous heat exposure.

---

[^tierney]: Tierney, J. E., Poulsen, C. J., Montañez, I. P., et al. (2020). Past climates inform our future. *Science*, 370(6517), eaay3701. https://doi.org/10.1126/science.aay3701

[^sst]: Menemenlis, S., Vecchi, G. A., Yang, W., Fueglistaler, S., & Raghuraman, S. (2025). Consequential differences in satellite-era sea surface temperature trends across datasets. Preprint, *Research Square*. https://doi.org/10.21203/rs.3.rs-5493841/v1

[^raghuraman]: Raghuraman, S. P., Soden, B., Clement, A., Vecchi, G. A., Menemenlis, S., & Yang, W. (2024). The 2023 global warming spike was driven by the El Niño–Southern Oscillation. *Atmospheric Chemistry and Physics*, 24, 11275–11283. https://doi.org/10.5194/acp-24-11275-2024

[^centralus]: Menemenlis, S., et al. The missing SST pattern effect on central US climate trends. _(to be filled in)_

[^ida]: Menemenlis, S., Vecchi, G. A., Gao, K., Smith, J. A., & Cheng, K.-Y. (2024). Extreme rainfall risk in Hurricane Ida's extratropical stage: An analysis with convection-permitting ensemble hindcasts. *Journal of the Atmospheric Sciences*, 81(7), 1165–1179. https://doi.org/10.1175/JAS-D-23-0160.1

[^heat]: Menemenlis, S., et al. Projected dangerous heat exposure. _(to be filled in)_
