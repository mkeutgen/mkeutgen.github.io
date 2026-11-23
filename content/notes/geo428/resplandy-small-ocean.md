+++
title   = "The Power and Challenges of Being Small in the Ocean"
kicker  = "GEO428 Biological Oceanography — Laure Resplandy (Princeton)"
deck    = "A tour of the physics that governs plankton life: the surface-area-to-volume argument for smallness, diffusion-limited nutrient uptake, the scallop theorem, Stokes sinking, and the phycosphere."
date    = "2026-09-14"
tags    = ["plankton", "Reynolds-number", "viscosity", "diffusion", "phycosphere", "biological-oceanography", "geo428"]
author  = "Maxime Keutgen De Greef"
toc     = true
draft   = false
+++

## The plankton size spectrum

Ocean life spans an extraordinary range of sizes. The standard plankton size classes step up by a factor of ten:[^sieburth]

| Size class | Size | Typical members |
|---|---|---|
| Femtoplankton | 0.02–0.2 µm | Viruses |
| Picoplankton | 0.2–2 µm | Bacteria, archaea, *Prochlorococcus*, *Synechococcus* |
| Nanoplankton | 2–20 µm | Small flagellates, coccolithophores |
| Microplankton | 20–200 µm | Diatoms, dinoflagellates, ciliates |
| Mesoplankton | 0.2–20 mm | Copepods and most other zooplankton |

Why are the primary producers of the ocean so small? The standard answer involves a trade-off between nutrient acquisition and body size, enforced by diffusion physics.

## Why small? The surface-area-to-volume argument

For a sphere of radius $r$, the Surface-Area-to-Volume ratio (SA/V) is

$$
\frac{\text{SA}}{\text{V}} = \frac{4\pi r^2}{\frac{4}{3}\pi r^3} = \frac{3}{r}.
$$

As the cell shrinks, SA/V increases: a cell 10 µm across (radius 5 µm) has SA/V $\approx$ 600 mm⁻¹, while a cell 100 µm across has SA/V $\approx$ 60 mm⁻¹. More surface per unit volume means more membrane available for nutrient exchange relative to the metabolic demand of the cell interior.

The contrast with land is instructive. Soil water carries higher nutrient concentrations than open seawater, replenished continuously by the adjacent mineral phase. This richer supply supports the large, complex body plans of terrestrial plants. In the nutrient-dilute ocean, cells must maximise their uptake surface — and the most effective way to do that is to stay small.

## Nutrient uptake at the diffusion limit

Each cell is surrounded by a **boundary layer** — a thin shell of fluid through which nutrients must diffuse to reach the cell membrane. Molecular diffusion across this layer is the rate-limiting step for nutrient uptake.

### Fick's law and diffusive flux to a sphere

Fick's law describes the diffusive flux of a dissolved species:

$$
J = -D\,\frac{dC}{dx},
$$

where $J$ is the flux (mol per unit area per unit time), $D$ is the molecular diffusion coefficient (units of area per time, typically $\sim 10^{-9}$ m²/s for small dissolved molecules in water), and $dC/dx$ is the concentration gradient.

For a spherical cell of radius $r_0$ in a medium with far-field concentration $C_\infty$ and surface concentration $C_0$, solving the steady-state diffusion equation in spherical coordinates gives the total diffusive transport:

$$
Q_D = 4\pi\,D\,r_0\,(C_\infty - C_0).
$$

Two consequences follow:

1. **Influx** — a phytoplankton cell assimilating nitrate draws the surface concentration $C_0$ below the ambient $C_\infty$. The steeper the gradient, the larger the flux.
2. **Efflux** — a dying cell or a particle leaks dissolved organic matter, creating a concentration gradient that bacteria can detect and follow by chemotaxis.

### Nutrient affinity favours small cells

**Nutrient affinity** — uptake normalised by cell volume — scales as

$$
\frac{Q_D}{V} = \frac{4\pi\,D\,r_0\,(C_\infty - C_0)}{\frac{4}{3}\pi\,r_0^3} = \frac{3D\,(C_\infty - C_0)}{r_0^2}.
$$

Affinity therefore increases as $1/r_0^2$: a cell half the radius has four times the volume-specific uptake rate. At best, uptake is bounded by the maximum diffusion limit. Smaller cells like cyanobacteria approach this limit more closely than larger cells like dinoflagellates — one reason small phytoplankton dominate nutrient-poor open-ocean waters.

{{< sidenote >}}
A natural question arises: if being small is so advantageous for nutrient acquisition, why did phytoplankton "accept" being vulnerable to predation by staying small? The answer loops back to the same constraint — nutrient limitation in the open ocean selects so strongly for high SA/V that the predation cost is paid.
{{< /sidenote >}}

A useful perspective on ocean productivity: global marine net primary production is comparable in magnitude to net primary production on land, yet the standing biomass of marine primary producers is orders of magnitude smaller. Phytoplankton turn over in days; trees persist for decades. The ocean's biological pump runs fast on small cells.

## Life at low Reynolds number

### Viscosity dominates

The Reynolds number (Re) measures the ratio of inertial to viscous forces:

$$
\text{Re} = \frac{UL}{\nu},
$$

where $U$ is the characteristic velocity, $L$ is the characteristic length, and $\nu$ is the kinematic viscosity of the fluid ($\sim 10^{-6}$ m²/s for seawater at 20 °C).

| Organism | Typical Re |
|---|---|
| Human swimming | $\sim 10^6$ |
| Copepods | $\sim 1$–$100$ |
| Phytoplankton and protists | $\sim 10^{-4}$–$10^{-1}$ |
| Bacteria | $\sim 10^{-5}$ |

At high Re (the human world), inertia dominates: a swimmer who stops stroking glides forward. At low Re (the microbial world), **viscosity dominates and inertial effects are negligible**. When a bacterium stops swimming, viscous forces remove its momentum almost at once. Purcell estimated that it coasts about 0.1 Å, less than the width of an atom.[^purcell] Copepods sit at intermediate Re, where inertia still plays a small part.

{{< sidenote >}}
The viscous force is the internal resistance that smooths velocity gradients by dissipating momentum (and thus kinetic energy) into heat. The inertial force is the force needed to accelerate a body to its current velocity, or equivalently to bring it to rest. At low Re, the viscous force overwhelms inertia at every instant.
{{< /sidenote >}}

### The scallop theorem

At low Re the governing equations (Stokes flow) are time-reversible. This has a profound consequence known as the **scallop theorem**:[^purcell] any reciprocal motion — a motion that looks identical when played backward — produces zero net displacement. A scallop opens and closes its shell symmetrically; at macroscopic Re this works because inertia carries the animal forward during the fast close. At low Re the same motion gets you nowhere.

How, then, do microorganisms swim? They need **non-reciprocal** (asymmetric) motions:

- **Bacteria** rotate a helical flagellum — a corkscrew that breaks time-reversal symmetry.
- **Eukaryotic flagellates** use a flexible oar with distinct power and recovery strokes.

{{< sidenote >}}
The scallop is invoked as a macroscopic analogy for symmetric motion, not as an example of a low-Re swimmer. Real scallops operate at high Re and rely on inertia.
{{< /sidenote >}}

### Feeding is equally constrained

In a viscous world, you cannot rely on inertia to drive water (and food particles) toward you. There is no equivalent of casting a net and letting momentum do the work. Feeding strategies at low Re must generate continuous flow.

## Temperature, viscosity, and the cost of motion

Water viscosity is strongly temperature-dependent: it roughly **triples** between 40 °C and 0 °C. Cold-water organisms pay a steep price — the same swimming motion requires about three times more energy in polar waters than in tropical waters.

There is a partial compensation: higher viscosity **slows sinking**, which helps cells maintain their position in the water column. The cost of locomotion rises, but the penalty of sinking out of the euphotic zone falls.

## Sinking dynamics and Stokes' law

For a small sphere sinking under gravity in a viscous fluid, the terminal velocity is given by Stokes' law:

$$
v = \frac{2}{9}\,\frac{g\,r^2\,(\rho' - \rho)}{\eta},
$$

where $g$ is gravitational acceleration, $r$ is the cell radius, $\rho'$ is the cell density, $\rho$ is the fluid density, and $\eta$ is the dynamic viscosity ($\sim 10^{-3}$ Pa·s for seawater).

Because sinking speed scales as $r^2$, cell size has a dramatic effect:

| Cell radius | Typical sinking speed | Size class |
|---|---|---|
| < 1 µm | $\sim$ 1 mm/hour | Bacteria, picoplankton |
| $\sim$ 10 µm | $\sim$ 0.1 m/hour | Nanoplankton, small phytoplankton |
| > 100 µm | > 10 m/hour | Large phytoplankton |

### The boundary-layer benefit of sinking

Sinking (or swimming) is not only a means of staying in the euphotic zone — it also **reduces the thickness of the diffusive boundary layer**. A cell that moves through the water continually renews the fluid around it, avoiding the nutrient-depleted stagnation zone that would otherwise develop. Higher speeds thus translate into higher nutrient fluxes. The gain depends on size, though. For a cell of about 1 µm, diffusion is so fast compared with the flow that sinking or swimming barely changes uptake. The advantage becomes significant only for larger cells, tens of micrometres and up.[^karpboss]

Cells can also actively adjust their buoyancy. Accumulating low-density compounds such as lipid droplets (oil) decreases the effective density difference $(\rho' - \rho)$ and slows sinking.

## The phycosphere

The **phycosphere** is the microscale zone of enhanced dissolved organic matter concentration surrounding a phytoplankton cell — the aquatic analogue of the rhizosphere around a plant root. Its spatial extent scales with cell size: a 20 µm cell maintains a larger phycosphere than a 5 µm cell, because a larger cell leaks more exudate and the diffusion geometry extends the enriched zone further from the surface.

Within the phycosphere, a rich set of ecological interactions plays out:

- **Synergistic** — bacteria consume leaked organic carbon in exchange for vitamins or iron that the phytoplankton cell cannot produce.
- **Parasitic** — pathogens exploit the nutrient-rich zone to locate and infect host cells.
- **Competitive** — free-living bacteria and the host cell compete for the same recycled nutrients.

These interactions are particularly well studied in **diatoms**, whose silica frustules and copious exudate production create prominent phycospheres.

## Summary

Five physical principles define the experience of being small in the ocean:

1. **Diffusion controls exchange** — molecular diffusion through the boundary layer is the bottleneck for nutrient uptake, and SA/V scaling makes small cells the winners.
2. **Viscosity rules** — at Re $\ll 1$, there is no inertia; every motion is instantaneously damped.
3. **The scallop theorem constrains locomotion** — only non-reciprocal strokes produce net displacement.
4. **Stokes' law governs sinking** — sinking speed scales as $r^2$, spanning orders of magnitude across the plankton size spectrum.
5. **The phycosphere mediates ecology** — the diffusive microenvironment around each cell is the arena for parasitic, competitive, and mutualistic interactions.

## References

[^sieburth]: Sieburth, J. McN., Smetacek, V., & Lenz, J. (1978). Pelagic ecosystem structure: Heterotrophic compartments of the plankton and their relationship to plankton size fractions. *Limnology and Oceanography*, 23(6), 1256–1263.

[^karpboss]: Karp-Boss, L., Boss, E., & Jumars, P. A. (1996). Nutrient fluxes to planktonic osmotrophs in the presence of fluid motion. *Oceanography and Marine Biology: An Annual Review*, 34, 71–107.

[^purcell]: Purcell, E. M. (1977). Life at low Reynolds number. *American Journal of Physics*, 45(1), 3–11.
