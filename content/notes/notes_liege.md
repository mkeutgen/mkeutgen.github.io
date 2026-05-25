+++
title   = "57th Liège Colloquium on Ocean Dynamics — submesoscale processes"
kicker  = "Conference notes — 57th International Liège Colloquium on Ocean Dynamics, Université de Liège, 25–29 May 2026"
deck    = "Talks on remote sensing of vertical velocity, SWOT-based reconstructions in the Agulhas, river plumes, variational surface-current interpolation, and methods for retrieving ocean currents from geostationary satellites."
date    = "2026-05-25"
tags    = ["SWOT", "submesoscale", "vertical-velocity", "altimetry", "Liège-Colloquium", "conference"]
author  = "Maxime Keutgen De Greef"
toc     = true
draft   = true
+++

The 57th edition of the [Liège Colloquium on Ocean Dynamics](https://www.ocean-colloquium.uliege.be/) is dedicated to **Submesoscale Processes in the Ocean** and runs 25–29 May 2026 at the Université de Liège (GHER). What follows are running notes from talks I attended — bullet-style, faithful to the speaker, with my own questions in sidenotes.

---

## Eric D'Asaro — Remote sensing of vertical velocity

*Applied Physics Laboratory, University of Washington.*

**Framing question:** does surface horizontal divergence measure vertical velocity — and *which* vertical velocity?

Torres et al. (2025) compute ocean vertical heat flux from surface divergence and Sea Surface Temperature (SST) by assuming a strong correlation between the two.[^torres-2025] D'Asaro's question: how accurate is that assumption?

Continuity gives, schematically,

$$
w(z) \;\approx\; -\!\int_{0}^{z} \!\bigl(\nabla_{\!h}\!\cdot\!\mathbf{u}_h\bigr)\,dz'
\;\approx\; -\bigl(\nabla_{\!h}\!\cdot\!\mathbf{u}_h\bigr)\,H,
$$

where $H$ is a characteristic depth over which the surface divergence is taken to be representative. He then compares this proxy to direct vertical-velocity observations from Lagrangian floats.

### Scale separation between horizontal and vertical velocity

- Vertical velocities span $\sim 10^{-7}$ to $\sim 1\ \mathrm{m\,s^{-1}}$ — a factor of roughly $10^{6}$ in magnitude across spatial scales.
- **Horizontal velocity** wavenumber spectra: slope $\sim k^{-2}$ over a wide range → variance dominated by **large scales**.
- **Vertical velocity** wavenumber spectra: roughly *white* → variance dominated by **small scales**.
- Consequence: $w$ is much more sensitive to the space and time scales of the measurement than $u_h$ is.

### Tom Farrar's submesoscale campaign as a reference dataset

The Sub-Mesoscale Ocean Dynamics Experiment (S-MODE), led by Tom Farrar (Woods Hole Oceanographic Institution, WHOI), measured horizontal velocity from DopplerScatt — JPL's airborne Ka-band Doppler scatterometer — during the Surface Water and Ocean Topography (SWOT) satellite Calibration/Validation (CalVal) campaign in the California Current. Pilot deployment October 2021, full deployments 2023 and April–May 2024.[^farrar-2025]

- DopplerScatt divergence is averaged over multiple passes (2–3 hours, ~2 km smoothing) before comparison with float-derived $w$.
- D'Asaro looks at frequency spectra and a quadrant plot of $w$ vs. $\nabla_{\!h}\!\cdot\!\mathbf{u}_h$.

### Quadrant analysis: when does $w \sim -\delta$ hold?

- **Downward $w$, negative surface divergence, strong gradient of vertical vorticity** at fronts → downwelling driven by frontal instability. As expected.
- **Surface $\delta \approx 0$ but positive $w$** at 3 points → consistent with Langmuir cells, wind-driven response, or atmospheric submesoscale forcing that creates $w$ without a clean signature in $\delta$.
- A separate quadrant shows **high positive $\delta$ paired with positive $w$**.

**Takeaway:** the $w$–$\delta$ relationship depends on the local structure and dynamics:

- **Low baroclinic-mode Ekman pumping**: $\delta$ measures $w$ well.
- **Mixed-Layer Instability (MLI)**: large $\delta$ but small $w$.
- $w$ and $\delta$ are best correlated for *downward* motions; upward motions appear weaker and noisier.
- Open question: contribution of symmetric instability?

### Summary

- $w$ depends on space and time scale — there is no single "vertical velocity."
- D'Asaro measured $\delta$ just below the surface and $w$ just below the mixed layer.
- $\mathrm{corr}(w,\delta)$ is best for downward motions; upward motions remain harder to constrain.
- Hopefully the start of more extensive measurements of $w$ over a wide range of scales.

{{< sidenote >}}This is exactly the calibration problem I'd want addressed before trusting any product that translates surface divergence directly into a vertical heat flux.{{< /sidenote >}}

---

## Solange Coadou-Chaventon — SWOT-derived vertical velocities in the Agulhas region

*LMD/IPSL, École Normale Supérieure (PSL), Paris.*

**Research question:** what are the spatial and temporal patterns of vertical velocities reconstructed from SWOT altimetry in the Cape Basin and the Agulhas retroflection region?

### Method: effective Surface Quasi-Geostrophy (eSQG)

eSQG extends Surface Quasi-Geostrophic (SQG) theory by tuning an effective stratification so that interior potential vorticity anomalies behave as surface buoyancy anomalies. It reconstructs $w$ for structures larger than ~40 km, from 150 m down to 1500 m, using sea surface height alone.

How much of the $w$ field can eSQG actually recover?

- **Spatial correlation** between modelled $w$ and $w_{\text{SQG}}$: $\approx 0.6$.
- **Spectral coherence** drops below 100 km.
- A few-day to week-long events of enhanced $w$, of order $100\ \mathrm{m\,day^{-1}}$ (slide 13).
- $w$ is strongly correlated with surface strain. The Agulhas retroflection is indeed an area of enhanced $w$; signal still present at 400 m depth.

### Model/observation discrepancies

- Model: daily averages.
- SWOT: snapshots.
- Enhanced $w$ in the vicinity of the Agulhas retroflection (vertical-velocity snapshot).

**Key points:**

- Strong regional variability — highest mean $w$ inside the Agulhas retroflection.
- Large $w$ values are driven by strain-dominated features (not vorticity-dominated eddies).

**Caveats:** contaminated SWOT pixels and the low temporal frequency of SWOT (~21-day repeat cycle) prevent thorough temporal analysis.

**References:** the published Agulhas-fronts paper is in *GRL* 2025;[^coadou-2025] the vertical-velocity paper is in preparation.

---

## Alexei Sentchev — Mekong river plume from SWOT and in-situ data

*Laboratoire d'Océanologie et de Géosciences (LOG, CNRS / Université de Lille / ULCO).*

Fine-scale structure and dynamics of the Mekong River plume from satellite-derived sea surface height and in-situ measurements.

**Why it matters:**

- ~1/3 of Vietnam's total population live in the delta region.
- 65% of Vietnamese aquaculture production.
- 95% of rice exports.

**Challenges:**

- Strong space/time variability of the plume.
- Complex biogeochemical–physical coupling.
- Sparse and heterogeneous observational data.
- Modelling: high-resolution physics coupled with biology and sediment transport.

**Findings (highlights):**

- A two-layer circulation structure consistent across observations and model.
- Further analysis requires higher-resolution SWOT products than currently available.

---

## Abel Dechenne — High-resolution surface-current interpolation in the Balearic Sea

*GHER, Université de Liège.*

Transport of heat, salinity, nutrients, and plankton in the Balearic Sea — interpolating multi-source surface currents to a regular grid.

**Three guiding questions:**

1. Which observations are used?
2. How does the interpolation operate?
3. What are the resolution and parameters?

### Data: the FaSt-SWOT campaign

FaSt-SWOT phase: April–July 2023. Objective: evaluate surface-current interpolation capabilities. Collected datasets:

- Lagrangian drifters.
- SWOT tracks (Level-3, gridded).
- High-Frequency (HF) Radar observations.

### Method: variational inverse interpolation (DIVAnd)

DIVAnd (Data-Interpolating Variational Analysis, n-dimensional) is a GHER tool that minimises a cost function balancing:

- Observation–field misfit.
- Field–background misfit.
- A smoothness penalty on abrupt variations.

Several physical constraints are added: presence of the coastline, horizontal-divergence penalty, temporal coherence.

**Resolution:**

- Temporal: ~2 days (daily observation cadence).
- Spatial: 0.08° grid.

### Validation

- Cross-validation: 25% of drifters held out at random.
- Relative-error variances: HF radars (large, due to dataset redundancy), drifters, and SWOT (~0.01277).
- Correlation lengths: 150 km in space, 0.5 day in time.
- Validation against zonal/meridional drifter velocities: $\mathrm{corr}(u) \approx 0.67$.
- RMSE $<10\ \mathrm{cm\,s^{-1}}$.

### Future directions (as presented)

- Better definition of the background estimate.
- Comparison of the field with temperature, salinity, and chlorophyll observations.
- Decomposition of the field into orthogonal functions.

{{< sidenote >}}My question to him afterwards: why not enforce a Helmholtz decomposition explicitly (rotational + divergent) rather than a divergence penalty? The penalty regularises but does not impose the physical constraint.{{< /sidenote >}}

---

## Alexei V. Kouraev — Submesoscale eddies in large deep Eurasian lakes

*LEGOS, Toulouse.*

Eddies are everywhere in oceans *and* lakes. In lakes, density is governed almost entirely by temperature; lakes "turn over" twice a year through vertical overturning. **Cold-core eddies are poorly studied.**

**Lake Baikal ice rings:** circular features 5–7 km in diameter where the ice cover is thinner than the surroundings.

- Appear in different years and different places.
- Largely unpredictable.
- Candidate explanations: atmospheric forcing, biological activity, methane release.
- Anomalous water structure observed beneath the rings: lens-like (intrathermocline) eddies.

---

## René Schubert — Submesoscale imbalances in a flow-following framework

*Affiliation — to be filled in._*

Only a fragment captured: the talk touched on the role of centripetal and isallobaric effects, and on inertial oscillations as a source of imbalance in the ocean velocity field. Full notes — _(to be filled in)_.

---

## Aurélien Deniau — Global correlations between remote-sensing chlorophyll and SWOT ocean surface topography

*Affiliation — to be filled in._*

**Context:** the literature reports strong correlations between SWOT topography and surface chlorophyll. Main goal of the talk: better understand the biogeochemical interactions at small scales.

### Data

- **DUACS** (Data Unification and Altimeter Combination System) gridded altimetry.
- **KaRIn** (Ka-band Radar Interferometer) SWOT swath product.
- Gridded chlorophyll: multi-mission product, daily, 4 km × 4 km.

### Methods

- Interpolation and filtering: DUACS and chlorophyll grids interpolated onto the SWOT swath.
- Filter applied to suppress large-scale gradients and speckle-like noise.
- Focus on correlation at small scales.
- "Overlapped" correlation coefficient.

### Results

- DUACS Absolute Dynamic Topography (ADT) vs. KaRIn ADT: no major difference except in the equatorial band.
- Small-scale (<100 km) results: exact colocation between altimetry pixels and chlorophyll pixels remains hard.

{{< sidenote >}}The Deniau paper itself I haven't been able to track down — _(to be filled in)_.{{< /sidenote >}}

---

## "An unprecedented view of ocean currents from geostationary satellites" — GOFLOW

*Speaker affiliation noted as Scripps in my notes; lead author Kaushik Srinivasan is at UCLA, with Luc Lenain at Scripps. Speaker identity — to be confirmed._*

The talk presents the GOFLOW approach for retrieving surface currents from geostationary infrared imagery.[^srinivasan-2026]

- **Loss function:** velocity loss is computed on $\log|\nabla T|$, under the assumption that the SST field is dominated by horizontal temperature advection. The velocity loss is mixed with a *spectral* loss.
- In Q&A the speaker acknowledged this is challenging — a classical double-objective optimisation problem.

{{< sidenote >}}They enforce a spectral loss — **how exactly?** This could be useful for my own emulator. Worth reading the methods section closely.{{< /sidenote >}}

---

## References

[^torres-2025]: Torres, H. S., Klein, P., Wang, J., Farrar, J. T., Wineteer, A., Perkovic-Martin, D., Siegelman, L., Rodriguez, E., et al. (2025). Submesoscale eddy contribution to ocean vertical heat flux diagnosed from airborne observations. *Geophysical Research Letters*, 52, e2024GL112278. <https://doi.org/10.1029/2024GL112278>

[^farrar-2025]: Farrar, J. T., D'Asaro, E. A., Rodriguez, E., Shcherbina, A. Y., Czech, E., Matthias, V., Nicholson, D. P., Bingham, F. M., et al. (2025). S-MODE: The Sub-Mesoscale Ocean Dynamics Experiment. *Bulletin of the American Meteorological Society*, 106(4), E810–E834. <https://doi.org/10.1175/BAMS-D-23-0178.1>

[^coadou-2025]: Coadou-Chaventon, S., Swart, S., Novelli, G., & Speich, S. (2025). Resolving sharper fronts of the Agulhas Current retroflection using SWOT altimetry. *Geophysical Research Letters*, 52, e2025GL115203. <https://doi.org/10.1029/2025GL115203>

[^srinivasan-2026]: Srinivasan, K., Lenain, L., Barkan, R., & Pizzo, N. (2026). An unprecedented view of ocean currents from geostationary satellites. *Nature Geoscience*. <https://doi.org/10.1038/s41561-026-01943-0>
