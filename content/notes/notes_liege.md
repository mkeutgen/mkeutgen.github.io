+++
title   = "57th Liège Colloquium on Ocean Dynamics — submesoscale processes"
kicker  = "Conference notes — 57th International Liège Colloquium on Ocean Dynamics, Université de Liège, 25–29 May 2026"
deck    = "Running notes on remote sensing of vertical velocity, SWOT reconstructions in the Agulhas, submesoscale subduction and tracer transport, mixed-layer-eddy parametrisation, coupled air-sea energetics, and the Southern Ocean carbon and heat budget."
date    = "2026-05-25"
tags    = ["SWOT", "submesoscale", "vertical-velocity", "altimetry", "subduction", "parametrisation", "Southern-Ocean", "carbon-pump", "Liège-Colloquium", "conference"]
author  = "Maxime Keutgen De Greef"
toc     = true
draft   = false
+++

The 57th edition of the [Liège Colloquium on Ocean Dynamics](https://www.ocean-colloquium.uliege.be/) is dedicated to **Submesoscale Processes in the Ocean** and runs 25–29 May 2026 at the Université de Liège (GHER). What follows are running notes from talks I attended — bullet-style, hopefully faithful to the speaker, with my own questions in sidenotes.

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

### Q&A — Helmholtz decomposition and scale-dependent balance

I asked whether a Helmholtz decomposition of the 2D velocity field

$$
\mathbf{u} \;=\; \nabla^{\!\perp}\!\psi \;+\; \nabla\phi
$$

— with $\psi$ the streamfunction (rotational part) and $\phi$ the velocity potential (divergent part) — would be more natural than a soft divergence penalty applied to the interpolated velocity. The motivation rests on **platform-to-component mapping**:

- The SWOT-derived geostrophic current $\mathbf{u}_g = (g/f)\nabla^{\!\perp}\!\eta$ is the perpendicular gradient of a scalar, so $\nabla\!\cdot\!\mathbf{u}_g = 0$ identically (modulo a tiny $\beta$-effect). **SWOT is, by construction, blind to surface divergence** — it constrains $\psi \approx (g/f)\eta$ and nothing else.
- Drifters and HF radar, by contrast, sample the **total** surface velocity, divergent component included.
- In potential space one could let SWOT pin $\psi$ directly, while drifters and HF radar additionally constrain $\phi$ — with separate correlation scales and variances for each, which is physically motivated since divergent kinetic energy is finer-scale and lower-energy than rotational KE.
- The no-normal-flow coastline condition is naturally $\psi = \mathrm{const}$ along the boundary, rather than an awkward joint condition on $(u,v)$.

A cleaner validation diagnostic than scalar RMSE on $(u,v)$ would be a rotational/divergent partition of the kinetic-energy spectrum (à la Bühler–Callies–Ferrari) — it would say where in the dynamics the interpolation gains or loses skill, which a scalar RMSE hides.

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

## Aurélien Deniau — Global correlations between remote-sensing chlorophyll and SWOT ocean surface topography

*CNES.*

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


---

## "An unprecedented view of ocean currents from geostationary satellites" — GOFLOW

*Lead author Kaushik Srinivasan is at UCLA, with Luc Lenain at Scripps.*

The talk presents the GOFLOW approach for retrieving surface currents from geostationary infrared imagery.[^srinivasan-2026]

- **Loss function:** velocity loss is computed on $\log|\nabla T|$, under the assumption that the SST field is dominated by horizontal temperature advection. The velocity loss is mixed with a *spectral* loss.
- In Q&A the speaker acknowledged this is challenging — a classical double-objective optimisation problem.

{{< sidenote >}}They enforce a spectral loss — **how exactly?** This could be useful for my own emulator. Worth reading the methods section closely.{{< /sidenote >}}

---


## Amala Mahadevan — Vertical tracer transport by submesoscale subduction

*Woods Hole Oceanographic Institution (WHOI).*

**Framing question:** where, and how much, do submesoscale motions carry surface tracers into the ocean interior?

### Where divergence comes from: curvature, not just frontogenesis

Along-front divergence accounts for most of the horizontal divergence at a front, and a large part of it comes from the *change of curvature* along the flow path.[^wu-2025]

- Where the rate of change of curvature is positive → convergence; where negative → divergence.
- A water parcel therefore changes depth as it circumnavigates an elliptical eddy, without any classical frontogenetic strain being required.
- Ship tracks crossing such features sample a continuously changing curvature, which is one reason single transects are hard to interpret.

### Why the vertical tracer flux reduces to a correlation

For a tracer concentration $c$ and vertical velocity $w$, apply a Reynolds decomposition $w = \langle w\rangle + w'$, $c = \langle c\rangle + c'$, where $\langle\cdot\rangle$ is an average over the region and $\langle w'\rangle = \langle c'\rangle = 0$ by construction. Then

$$
\langle wc\rangle
= \langle w\rangle\langle c\rangle
+ \langle w\rangle\langle c'\rangle
+ \langle c\rangle\langle w'\rangle
+ \langle w'c'\rangle
= \langle w\rangle\langle c\rangle + \langle w'c'\rangle ,
$$

since the two cross terms vanish. If the domain-averaged vertical velocity is zero — as it must be, to leading order, in a closed region with no net upwelling — then

$$
\langle wc\rangle = \langle w'c'\rangle .
$$

The **net vertical tracer flux is entirely an eddy correlation**: it is not the mean vertical motion that matters but whether downward-moving water is systematically richer or poorer in tracer than upward-moving water.

A negative net flux $\langle w'c'\rangle_{(x,y)} < 0$ acts to homogenise $c$ in the vertical; biological or physical processes must then restore the vertical gradient of $c$ for a steady state to exist.

### Three-dimensional subduction pathways

Models show that tracer subduction pathways are genuinely three-dimensional, and subduction combined with lateral advection forms **coherent intrusions** in the pycnocline.[^freilich-2024] These can be traced with biological tracers.

Observed signature of an intrusion, below the euphotic zone:

- Positive chlorophyll anomaly (a subsurface layer, distinct from the deep chlorophyll maximum).
- Positive oxygen anomaly.
- Positive temperature anomaly.
- Negative nitrate anomaly.

The obvious question about such a feature is: **what is the age of that water** — how long since it left the surface?

### Dating an intrusion from tracer attenuation

Oxygen, chlorophyll and organic carbon all attenuate as they subduct, at a rate set by microbial respiration. Writing the budget for a tracer $\mathrm{Tr}$ with attenuation rate $\lambda$ and horizontal/vertical mixing coefficients $K_h$, $K_v$:

$$
\frac{D\,\mathrm{Tr}}{Dt}
= -\lambda\,\mathrm{Tr}
+ K_h \nabla_{\!H}^{2}\,\mathrm{Tr}
+ K_v \frac{\partial^{2}\mathrm{Tr}}{\partial z^{2}} .
$$

Integrating along a trajectory and treating the mixing operator $\mathcal{M}$ as linear gives, at elapsed time $\tau$,

$$
\mathrm{Tr}(\tau) = \mathrm{Tr}(0)\,e^{(-\lambda + \mathcal{M})\tau} .
$$

Inverting for $\tau$ gives the time since the water left the surface — provided the surface value $\mathrm{Tr}(0)$ is known. Measured attenuation rates for oxygen and for chlorophyll supply the two independent estimates.

The method was tested in a process-study model and validated against ages computed directly from particle trajectories.[^abbott-thesis]

### From age to vertical velocity

A Lagrangian vertical velocity follows directly from the age and the depth displacement:

$$
w_L = \frac{\Delta z}{\tau}.
$$

Comparing age distributions from particles and from the tracer inversion across multiple intrusions, and restricting to water younger than 10 days, gives a probability distribution of $w_L$. Applied to the observations, subduction velocities fall between **20 and 50 m per day**.

### Summary

- Subduction is confined to selective regions — roughly **1–5% of the area** — set by frontogenesis and by changes in flow curvature.
- Coherent three-dimensional pathways form intrusions that transport surface water, and its carbon, into the interior.

---

## Andrey Shcherbina & Eric D'Asaro — Mind the tail: recovering subsurface vertical velocity

*Applied Physics Laboratory, University of Washington.*

Vertical velocity is weak, intermittent and hard to measure directly, yet it is central to vertical fluxes. **How well can surface observations recover subsurface $w$?**

### The hidden assumption in going from surface divergence to $w$

Converting a measured surface divergence into a vertical velocity requires assuming a vertical structure. The same surface divergence is compatible with very different profiles $w(z)$ — and the choice of profile is rarely stated.

### Setup

A Regional Ocean Modeling System (ROMS) simulation from UCLA: 200 m resolution, a 500 km × 500 km nested domain covering the S-MODE region.

### Findings

- The vertical structure of $w$ is complex, but surface divergence does predict upper-ocean $w$.
- A **slab-plus-ramp model** works well in the mixed layer — *statistically*.
- The statistics, however, are dominated by internal-gravity-wave-like (IGW-like) motions.
- Submesoscale frontal $w(z)$ has a very different vertical structure from the IGW-dominated bulk.
- **The flux-relevant vertical velocity lives in the statistical tails** — which is where a fit tuned to the bulk statistics performs worst.

---

## Warm filaments at submesoscale salinity fronts

*Speaker — (to be filled in).*

**Question:** what creates the narrow warm filaments seen in SST imagery?

Proposed mechanism: warm-water convergence at submesoscale *salinity* fronts, forming narrow SST filaments. Tested with an offline Lagrangian simulation, asking whether the submesoscale flow alone can stir an initial vertical temperature gradient into the observed surface pattern.

---

## Anna Lo Piccolo — Enhancing entrainment in submesoscale fluxes

Parametrisation development and its impact.

**Context:** entrainment and subduction are the exchanges between the mixed layer and the ocean interior. They are associated with Mixed-Layer Eddies (MLEs) and, being sub-grid-scale, must be parametrised in global Earth System Models (ESMs).

Two questions:

1. How do submesoscales enhance entrainment and subduction?
2. Can that enhancement be captured in a physics-based parametrisation?

### High-resolution simulations

A Reynolds-Averaged Navier–Stokes (RANS) simulation with a double mixed-layer front in geostrophic balance.

- Subduction occurs *below* the mixed-layer base.
- The depth reached by entrainment depends on the mixed-layer depth and the Richardson number: it is easier to break the stratification below when that stratification is weak.
- As the Brunt–Väisälä frequency $N$ increases, stratification resists entrainment and the effect weakens.

### The parametrisation

Under scaling assumptions, the mean tracer equation is

$$
\partial_t \overline{\tau} + \overline{\mathbf{u}}\cdot\nabla\overline{\tau}
= -\nabla\cdot\bigl(\overline{\mathbf{u}'\tau'}\bigr),
$$

closed with a flux–gradient relation $\overline{\mathbf{u}'\tau'} = -\mathbf{R}\,\nabla\overline{\tau}$. The advective part is expressed through an overturning streamfunction, following the Fox-Kemper–Ferrari–Hallberg mixed-layer-eddy parametrisation, in which the streamfunction is set by the vertical buoyancy flux.[^fox-kemper-2008]

The proposed modification lets the vertical structure function extend **below** the mixed-layer depth $H$:

- Local **restratification** = isopycnal slope reduces.
- Local **destratification** = isopycnal slope increases.
- Mixed-layer eddies expand the front laterally and vertically; the mixed layer expands and the entrainment layer grows with it.

### Q&A — Redi diffusion at the submesoscale

The applicability of Redi isopycnal diffusion as a closure for submesoscale fluxes was raised. In submesoscale regimes isopycnal slopes are steeper than in the mesoscale case, but not steep enough to violate the small-angle approximation that Redi diffusion relies on.

---

## Multiscale stirring and mixing during eddy separation

*Speaker — (to be filled in).*

**Question:** how should advective transport actually be computed?

- **State of the art:** Eulerian finite-difference and finite-volume methods.
- **Lagrangian alternative:** particle-based methods. Benefits: no numerical diffusion, and trivially parallelisable. Drawback: non-uniform sampling of the domain.

The Lagrangian route is framed through **flow maps** — where did the tracer end up at the final time, and where did it come from at the start time. If the tracer is passively transported with fluid parcels, the flow map carries the full transport information from 3D parcel locations, with **no compounding of numerical errors** over the integration.

---

## Frontogenesis or frontolysis? The role of vertical mixing

*Speaker — (to be filled in).*

Submesoscale fronts drive large downwelling (of order $100\ \mathrm{m\,day^{-1}}$), restratification, and energetic transfers — and the secondary circulation of the front controls most of these consequences.

**Question:** does vertical mixing sharpen fronts (frontogenesis) or weaken them (frontolysis)?

The source of confusion is the vertical eddy viscosity: vertical momentum mixing can create the convergence that sharpens a front, while the vertical buoyancy flux acts to weaken it. Which wins is a quantitative question, explored over three non-dimensional parameters:

- **Rossby number** $Ro$: 0.25, 0.5, 1, 2.
- **Ekman number** $Ek = \nu_v / (f h^{2})$, measuring mixing intensity: $10^{-3}$ to $10^{-1}$.
- **Turbulent Prandtl number**: the ratio of momentum to buoyancy mixing.

Result as presented: momentum mixing drives frontogenesis, the vertical buoyancy flux drives frontolysis.

---

## Coupled air–sea interaction at the submesoscale: the role of available potential energy

*Speaker — (to be filled in).*

Framing follows the review of submesoscale mechanisms and ageostrophic pathways towards turbulence.[^taylor-thompson-2023]

**Current feedback on stress** leads to *eddy killing* through negative wind work, $\overline{\boldsymbol{\tau}' \cdot \mathbf{u}'} < 0$. This talk focused instead on the **thermal** feedback and on the surface flux of Available Potential Energy (APE).

- Coupled numerical experiments in which submesoscale SST is filtered out of the air–sea fluxes isolate the thermal feedback.
- The surface potential-energy flux depends on the degree of temperature/salinity density compensation at the front.

---

## Momme C. Hell — A scale-aware coupled framework

**Approach:** use an exact scale-selective equation for the coupled ocean/atmosphere Ekman layer, and diagnose it with structure functions.

- **PyTurbo** *(name to confirm)*: computes $n$-th order structure functions on arbitrary domains to a chosen confidence level.
- Bootstrapped structure functions are used for process analysis through the kinetic-energy budget.
- Oceanic cross-scale advection and wind work are both **episodic**, and are related to energy imbalances between the atmospheric and oceanic boundary layers.
- Compared against the S-MODE field campaign.

**Takeaway:** the pathways of turbulent air–sea kinetic-energy transfer are scale-dependent and episodic — which raises the question of whether bulk formulae remain appropriate below 1° resolution.

---

## Tides, internal waves and bathymetry

*Speaker — (to be filled in).*

Themes: remote forcing of tides, interaction with bathymetry, and the transition from wave to vortical dynamics.

At the mesoscale, the question is how internal tides interact with bathymetry and what internal-tide energy fluxes result. Setup notes:

- Dynamic Orlanski open boundary conditions.
- Typical grid-size ratio between nests: ~3.

Application: the California Undercurrent (CUC) salinity anomaly. The local flow at 200 m combines the CUC's local branch, tidally rectified flow, internal tides, and Potential Vorticity (PV) generation upstream of the gap in the ridge.

---

## Abigail Bodner — A data-driven submesoscale parametrisation

Global ocean models are sensitive to how submesoscales are coupled to boundary-layer turbulence.

**Setup:** train on a $1/48°$ simulation. Inputs are the mixed-layer depth, boundary-layer depth, buoyancy gradient, Coriolis parameter, stratification, surface wind stress, surface heat flux, strain, vorticity and divergence; the output is the submesoscale vertical buoyancy flux. The network predicts the fluxes directly, rather than predicting the terms of an assumed closure.

**Why does the Convolutional Neural Network (CNN) perform well?** Interpreted by removing input features one at a time and by computing sensitivities (gradients) with respect to each input:

- At large scales, **strain** is the most important feature.
- At the local scale, **mixed-layer depth** is the most important feature.

---

## Southern Ocean carbon, heat and sea ice — do submesoscales matter to the large scale?

*Speaker — Channing Prend (name to confirm).*

### Context

The zonal-mean Southern Ocean carbon cycle splits into an anthropogenic component — a major sink — and a natural component dominated by upwelling of Dissolved Inorganic Carbon (DIC) at low latitudes.[^gruber-2019] The question is how carbon is moved between the surface ocean and the interior, and whether submesoscales contribute materially to that transport.

### A shift in the sea-ice state

Antarctic sea ice was broadly growing until 2015, then shifted: December 2016, and the record lows of 2023 and 2024. The 2023 winter extent reached **6.4 standard deviations below the 1991–2020 mean**.[^purich-2023] The shift co-occurred with an accumulation of subsurface heat — and a very rapid heat flux is required to produce it.

### Evidence that submesoscales matter

- **Iron:** vertical eddy iron fluxes are of leading-order importance in sustaining Southern Ocean phytoplankton blooms, and are enhanced by roughly a factor of 2 in submesoscale-resolving regional simulations.[^rosso-2016]
- **Eddy subduction:** submesoscales restratify the mixed layer and transport nutrients upward, but they also drive subduction, moving tracers downward into the interior. In an Antarctic Circumpolar Current (ACC) channel model, a 1 km simulation takes up ~50% more tracer than a 20 km one.
- **Glider observations** from the Southern Ocean show enhanced ventilation and subduction attributable to submesoscale processes.

Mixed-Layer Instability (MLI) is an efficient mechanism for generating these submesoscale flows.

### How to observe them

Gliders sample at the scales needed to resolve submesoscale motions, and targeted glider campaigns are the main source of in-situ observations from Southern Ocean marginal ice zones. A second platform: **elephant seals carrying Conductivity–Temperature–Depth (CTD) tags**, which return a circumpolar dataset.

Testing the seal platform by subsampling a model along observed seal tracks in the Weddell Sea, and comparing cumulative vertical heat transport:

- Seals underestimate frontal strength, but qualitatively track buoyancy fluxes.
- Parametrised fluxes underestimate the true vertical heat transport.
- The Fox-Kemper parametrisation is designed for models, but it is cheap enough that with an estimate of $N^2$ one can compute submesoscale heat and buoyancy fluxes directly from the observations.
- Both the parametrised mixed-layer-eddy flux and the diagnosed vertical heat flux peak in persistent frontal regions — the slope current, the coastal current, and near the ACC fronts.

### The eddy subduction pump, and the size of the uncertainty

Estimates of the eddy subduction pump's contribution to Particulate Organic Carbon (POC) export vary widely with method and region: around 50% in the original mid-latitude bloom estimate,[^omand-2015] around 20% for the Southern Ocean with a different methodology, and about 5% in an annual global model.[^resplandy-2019] **How large are these uncertainties at the large scale?** One useful diagnostic is the percentage of total variance explained by each frequency band.

### Final thoughts

- The importance of submesoscale fluxes to large-scale upper-ocean heat, carbon and nutrient budgets likely varies by region and by season.
- The open problem is how to extrapolate observations that are local in space and time to a quantitative assessment of the submesoscale role in large-scale sea-ice and biogeochemical variability.
- Sampling aliasing may distort the temporal variability inferred from sparse measurements.
- Phytoplankton patchiness is well observed by satellites, but attributing it to physical versus biological drivers remains a challenge.

{{< sidenote >}}The spread from ~5% to ~50% for the same physical pump is the number I keep coming back to — it is method and region, not physics, that separates those estimates.{{< /sidenote >}}

---

## Machine learning for Southern Ocean chlorophyll

*Speaker — (to be filled in).*

Satellite data show an increasing trend in chlorophyll-a in the Southern Ocean. The modelling side uses the MIT General Circulation Model (MITgcm) with BLING (Biogeochemistry with Light, Iron, Nutrients and Gases), a simplified biogeochemical model.

First part of the work: prediction of Net Primary Production (NPP). A caution raised on the correlation analysis — it is not correct to treat the Southern Ocean as a single basin when computing basin-wide correlations.

---

## Mara Freilich — Reactive and passive submesoscale biophysical processes in eastern boundary currents

*Brown University.*

**Goal:** disentangle the reactive from the passive contributions to submesoscale biophysical variability.

### Parametrising the eddy flux

Write the horizontal eddy chlorophyll flux as a downgradient closure,

$$
\langle \mathbf{u}'\,\mathrm{chl}'\rangle = -D_e\,\nabla\langle \mathrm{chl}\rangle ,
$$

with $D_e$ an effective diffusivity. The chlorophyll variance $V = \langle \mathrm{chl}'\,\mathrm{chl}'\rangle$ is observed to follow a power law in the mean, $V \propto \langle \mathrm{chl}\rangle^{2}$.

The chlorophyll variance equation then implies that if both the effective diffusivity and the variance dissipation are spatially constant, the mean offshore velocity must also be constant — a testable consistency condition.

### What is relevant about the submesoscale for biology?

- Spatial scales of 1–10 km at mid-latitudes, with Rossby number of order 1.
- For biology, **temporal** scales may matter more than spatial ones: submesoscale dynamical timescales match microbial process timescales, so resource supply (light, nutrients) arrives on timescales at which populations can actually respond.[^freilich-2022]
- Balanced and unbalanced motions interact, producing irreversible transport. Separated here with a spectral wave–vortex decomposition.

**Question addressed:** what generates and what dissipates chlorophyll variance at the submesoscale? The diagnosed submesoscale offshore carbon flux is $0.04\ \mathrm{mmol\,m^{-2}\,s^{-1}}$ *(units to confirm)*.

---
## References

[^torres-2025]: Torres, H. S., Klein, P., Wang, J., Farrar, J. T., Wineteer, A., Perkovic-Martin, D., Siegelman, L., Rodriguez, E., et al. (2025). Submesoscale eddy contribution to ocean vertical heat flux diagnosed from airborne observations. *Geophysical Research Letters*, 52, e2024GL112278. <https://doi.org/10.1029/2024GL112278>

[^farrar-2025]: Farrar, J. T., D'Asaro, E. A., Rodriguez, E., Shcherbina, A. Y., Czech, E., Matthias, V., Nicholson, D. P., Bingham, F. M., et al. (2025). S-MODE: The Sub-Mesoscale Ocean Dynamics Experiment. *Bulletin of the American Meteorological Society*, 106(4), E810–E834. <https://doi.org/10.1175/BAMS-D-23-0178.1>

[^coadou-2025]: Coadou-Chaventon, S., Swart, S., Novelli, G., & Speich, S. (2025). Resolving sharper fronts of the Agulhas Current retroflection using SWOT altimetry. *Geophysical Research Letters*, 52, e2025GL115203. <https://doi.org/10.1029/2025GL115203>

[^srinivasan-2026]: Srinivasan, K., Lenain, L., Barkan, R., & Pizzo, N. (2026). An unprecedented view of ocean currents from geostationary satellites. *Nature Geoscience*. <https://doi.org/10.1038/s41561-026-01943-0>

[^wu-2025]: Wu, Y., et al. (2025). _(full citation to be filled in)_ — on along-front divergence and the role of changing flow curvature.

[^freilich-2024]: Freilich, M. A., et al. (2024). Three-dimensional subduction pathways and coherent intrusions in the pycnocline. *Proceedings of the National Academy of Sciences*. _(volume and DOI to be filled in)_

[^abbott-thesis]: Abbott, K. (2026). PhD thesis, Massachusetts Institute of Technology / WHOI Joint Program. _(exact title and institution to be confirmed)_

[^fox-kemper-2008]: Fox-Kemper, B., Ferrari, R., & Hallberg, R. (2008). Parameterization of mixed layer eddies. Part I: Theory and diagnosis. *Journal of Physical Oceanography*, 38(6), 1145–1165. <https://doi.org/10.1175/2007JPO3792.1>

[^taylor-thompson-2023]: Taylor, J. R., & Thompson, A. F. (2023). Submesoscale dynamics in the upper ocean. *Annual Review of Fluid Mechanics*, 55, 103–127. <https://doi.org/10.1146/annurev-fluid-031422-095147>

[^gruber-2019]: Gruber, N., Landschützer, P., & Lovenduski, N. S. (2019). The variable Southern Ocean carbon sink. *Annual Review of Marine Science*, 11, 159–186. <https://doi.org/10.1146/annurev-marine-121916-063407>

[^purich-2023]: Purich, A., & Doddridge, E. W. (2023). Record low Antarctic sea ice coverage indicates a new sea ice state. *Communications Earth & Environment*, 4, 314. <https://doi.org/10.1038/s43247-023-00961-9>

[^rosso-2016]: Rosso, I., Hogg, A. McC., Matear, R., & Strutton, P. G. (2016). Quantifying the influence of sub-mesoscale dynamics on the supply of iron to Southern Ocean phytoplankton blooms. *Deep-Sea Research Part I*, 115, 199–209. <https://doi.org/10.1016/j.dsr.2016.06.009>

[^omand-2015]: Omand, M. M., D'Asaro, E. A., Lee, C. M., Perry, M. J., Briggs, N., Cetinić, I., & Mahadevan, A. (2015). Eddy-driven subduction exports particulate organic carbon from the spring bloom. *Science*, 348(6231), 222–225. <https://doi.org/10.1126/science.1260062>

[^resplandy-2019]: Resplandy, L., Lévy, M., & McGillicuddy, D. J. (2019). Effects of eddy-driven subduction on ocean biological carbon pump. *Global Biogeochemical Cycles*, 33(8), 1071–1084. <https://doi.org/10.1029/2018GB006125>

[^freilich-2022]: Freilich, M., et al. (2022). _(full citation to be filled in)_ *Geophysical Research Letters* — on the match between submesoscale and microbial timescales.
