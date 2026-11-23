+++
title   = "Zooplankton: Ecological and Biogeochemical Roles"
kicker  = "GEO428 Biological Oceanography — Laure Resplandy (Princeton)"
deck    = "A survey of the main zooplankton groups, how gelatinous tunicates differ from jellyfish, how zooplankton avoid predators, and the three standard shapes of grazing response."
date    = "2026-10-12"
tags    = ["zooplankton", "tunicates", "grazing", "biogeochemistry", "biological-oceanography", "geo428"]
author  = "Maxime Keutgen De Greef"
toc     = true
draft   = true
+++

## Why zooplankton matter

Zooplankton are the ocean's secondary producers: they eat phytoplankton and other small cells, and turn that food into biomass that higher trophic levels can use. Three themes frame the lecture:

- **Microbial loop.** Zooplankton graze on the bacteria and small protists that recycle dissolved organic matter, and so link the microbial loop to larger food webs.
- **Export.** Their fecal pellets and carcasses sink fast, giving rapid export of Particulate Organic Carbon (POC) to depth.
- **Mixoplankton paradigm.** Many plankton do not fit the old split between photosynthetic "phytoplankton" and grazing "zooplankton". Mixoplankton do both.

## Key groups

### Protists

- **Dinoflagellates** are mixotrophs: they photosynthesize *and* graze.
- **Radiolaria and Foraminifera** build mineral shells: silica in radiolarians, calcium carbonate in foraminifera. Their shells sink and are preserved in sediments, so they carry a record of past ocean conditions. _(to be filled in: which proxies the lecture mentioned)_

### Crustaceans

Copepods and krill are the most abundant zooplankton, and most zooplankton research is done on copepods. This is partly a sampling bias: they are easier to catch. Two features matter for biogeochemistry:

- They migrate vertically, on a daily (diel) and a seasonal cycle.
- They are rich in lipids, which makes them a high-energy food for fish and whales.

### Gelatinous zooplankton

This is a functional group, not a taxonomic one. It spans several trophic levels and phyla, but members share a body plan: mostly water, neutrally buoyant, and generally transparent, which hides them from predators. Some grow very large. Fish and amphipods are sometimes seen riding inside a salp.

**Cnidaria** are the true jellyfish. They include siphonophores such as the Portuguese man-of-war. They are passive ambush predators: tentacles carry stinging cells (cnidoblasts) with venom-filled harpoons, used both to catch prey and for defense.

**Ctenophores** (comb jellies) are the other jelly-like phylum with radial symmetry.

**Tunicates** matter most for biogeochemical cycles, and they are *not* jellyfish. They are invertebrate chordates, closer to vertebrates than to cnidarians. Differences from jellyfish:

| | Cnidaria, ctenophores | Tunicates |
|---|---|---|
| Symmetry | Radial | Bilateral |
| Tissue layers | Two (diploblastic) | Three (triploblastic) |
| Muscles and organs | Absent | True muscles and organs |

Tunicates are filter feeders with a high clearance rate: the volume of water cleared of prey per unit time. At high prey concentration the clearance rate drops and ingestion saturates. Ingestion rate depends on body size.

**Molluscs** (for example pteropods and heteropods) also contribute to the group. _(to be filled in: details from the lecture)_

## Strategies against predation

1. **Behavior.** Diel vertical migration (hide at depth by day, feed near the surface at night) and fast escape or jumping.
2. **Optical and visual.** Transparency. Counterillumination: producing light (bioluminescence) on the underside to match the light from above, so the animal casts no silhouette. Bioluminescent flashes that disrupt a predator's attack.
3. **Morphological and structural.** Be small, or be big. Spines and other defensive structures.

## Grazing dynamics

A functional response describes how a grazer's ingestion rate $I$ changes with prey concentration $P$. Three standard shapes, named after Holling:[^holling]

- **Type I.** Ingestion rises linearly with prey concentration, then stays constant at a ceiling: $I = \min(aP,\, I_{\max})$, where $a$ is the clearance rate.
- **Type II.** Ingestion rises hyperbolically and saturates. The limit is handling time $h$: the grazer spends more of its time processing prey than finding it. $I = aP/(1 + ahP)$, which levels off at $1/h$. The tunicate clearance behavior above looks like this.
- **Type III.** Ingestion follows an S-shaped (sigmoidal) curve, for example $I = aP^2/(1 + ahP^2)$. It is low at low prey density, which gives prey a refuge. This reflects prey switching or a feeding threshold.

## References

[^holling]: Holling, C. S. (1959). Some characteristics of simple types of predation and parasitism. _The Canadian Entomologist_, 91, 385–398. _(to be filled in: confirm this is the reference used in the lecture)_
