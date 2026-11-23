+++
title   = "Fisheries: From Primary Production to Fish Catch"
kicker  = "GEO428 Biological Oceanography — Laure Resplandy (Princeton)"
deck    = "How much ocean production it takes to feed global fisheries, how fishing has changed marine biomass, what controls fish stocks from below and above, and why spawning timing matters."
date    = "2026-11-16"
tags    = ["fisheries", "trophic-transfer", "primary-production-required", "stock-assessment", "match-mismatch", "biological-oceanography", "geo428"]
author  = "Maxime Keutgen De Greef"
toc     = true
draft   = false
+++

## Why fisheries matter

Economic weight (2020 figures from the lecture): 1.7 million jobs, USD 253
billion in sales and USD 117 billion in value added. These match the United
States figures published by the National Oceanic and Atmospheric
Administration (NOAA). _(to be filled in: confirm the source)_

For scale: one million tonnes of fish fills about a million cubic metres,
since fish are about as dense as water. That is a 100 m × 100 m square stacked
100 m high. The lecture's image was a football field piled 100 m high.

Global fish catch is about 120 million tonnes a year. Bottom trawls and pelagic
trawls take a large share, but purse seines, small-scale fisheries, longlines
and gillnets are all significant. Bottom trawling, which drags nets along the
sea floor, has large negative impacts.

Aquaculture now produces about 140 million tonnes a year, more than capture
fisheries.

## Fishing and whaling have changed marine biomass

- Whaling divided marine mammal biomass by about five.
- Total fish biomass is about 0.6; the exploited part is about 0.15, down by
  about 0.1. Fishing has removed almost half of the exploited fish biomass.
  _(to be filled in: units and source of these numbers)_

## The unit stock

A **unit stock** is a self-contained group of individuals of one species that
live in a defined geographic area and share a common gene pool (they breed with
each other). Examples: Northeast Arctic cod, off northern Norway; southern
bluefin tuna. Members share behaviour and biology.

The point of the concept is to capture the real population dynamics, genetics
and reproductive capacity of the species.

A **fishery** or **management unit** is a fraction of a unit stock grouped
together for practical commercial or regulatory purposes.

The biomass $B$ of a stock changes as

$$
\Delta B = R + G - M - F,
$$

where $R$ is recruitment (young fish joining the stock), $G$ growth of the
individuals already in it, $M$ natural mortality and $F$ fishing mortality
(the catch).[^russell]

## Salmon as a nutrient pump

Salmon grow at sea, then swim upriver to spawn and die. Their bodies carry
marine nitrogen and phosphorus into streams and the forests around them. They
act as a biogeochemical pump, moving nutrients against the usual downhill flow
from land to sea.

## Trophic transfer efficiency

Each step up a food chain loses most of the energy, to respiration, waste and
uneaten food. The rule of thumb is that about 10% passes to the next level and
90% is lost.

Real efficiencies depart from this rule. Marine transfer efficiencies are
often below 10%. Terrestrial ones are lower still _(to be filled in: the
lecture's value, recorded in my notes as "1.52%")_. The reason: phytoplankton
are easy to digest, while land plants are built of hard-to-digest structural
material such as cellulose.

The lecture's example: 100 kg of phytoplankton makes about 3 kg of anchovies,
100 g of cod or 1 g of tuna. At 10% per step, these correspond to about 1.5, 3
and 5 steps above phytoplankton.

## How much fish can the ocean make?

Ryther (1969) estimated fish production as[^ryther]

$$
P_{\text{fish}} = \text{NPP} \times E^{\,n},
$$

where NPP is Net Primary Production, $E$ the ecological transfer efficiency per
step, and $n$ the number of trophic steps. Ryther split the ocean into three
regions with very different food chains:

| Region | Trophic steps $n$ | Efficiency $E$ |
|---|---|---|
| Open ocean | 5 | 10% |
| Coastal | 3 | 15% |
| Upwelling | 1.5 | 20% |

Upwelling regions have short chains and high efficiency, so they produce far
more fish per unit of NPP. The global answer is about 200 million tonnes of
fish a year.

## Turning it around: primary production required

How much NPP does our catch need? This is the **Primary Production Required
(PPR)** to sustain fisheries.

**Vitousek et al. (1986)** estimated about 2% of ocean NPP.[^vitousek] The
message: there are plenty more fish to catch.

**Pauly and Christensen (1995)** showed this was not robust.[^pauly] Vitousek
used one global linear scaling. It ignored spatial heterogeneity (most catch
comes from productive shelves and upwelling zones) and unreported extraction
(discards and bycatch). Redoing the calculation by ecosystem and by the trophic
level of each catch gives about 8% globally, and 25–35% in coastal and
upwelling systems.

## What controls fish stocks?

- **Bottom-up control:** nutrient availability, primary production, ocean
  physics.
- **Top-down control:** predators regulate their prey; removing a predator
  can set off a trophic cascade down the food web.
- **Wasp-waist control:** a mid-trophic-level forage species, such as sardine
  or anchovy, regulates both the plankton below it and the predators above
  it.[^cury]

NPP and fish yield are decoupled: across ecosystems, there is no correlation
between NPP and fish catch, while chlorophyll *a* does better.[^friedland]
Real food webs are a tangled network (a "hairball"), not a linear chain.
Mechanistic ecosystem models now run from ocean dynamics and phytoplankton up
to fish, and capture the structure and function of marine ecosystems. _(to be
filled in: which model the lecture showed)_

## The match–mismatch hypothesis

Cushing's match–mismatch hypothesis:[^cushing69][^cushing90] the survival of a
year's fish larvae depends on whether they hatch when their plankton food
peaks. A match gives a strong year class; a mismatch gives a weak one.

## Sardines and anchovies

**Spawning.** Sardines spawn in warmer water, 13–16 °C. Anchovies spawn over a
lower, broader range, 10–14 °C.

**Feeding.** _(to be filled in)_

## References

[^russell]: Russell, E. S. (1931). Some theoretical considerations on the "overfishing" problem. *Journal du Conseil International pour l'Exploration de la Mer*, 6(1), 3–20.

[^ryther]: Ryther, J. H. (1969). Photosynthesis and fish production in the sea. *Science*, 166, 72–76.

[^vitousek]: Vitousek, P. M., Ehrlich, P. R., Ehrlich, A. H., & Matson, P. A. (1986). Human appropriation of the products of photosynthesis. *BioScience*, 36(6), 368–373.

[^pauly]: Pauly, D., & Christensen, V. (1995). Primary production required to sustain global fisheries. *Nature*, 374, 255–257.

[^cury]: Cury, P., Bakun, A., Crawford, R. J. M., Jarre, A., Quiñones, R. A., Shannon, L. J., & Verheye, H. M. (2000). Small pelagics in upwelling systems: patterns of interaction and structural changes in "wasp-waist" ecosystems. *ICES Journal of Marine Science*, 57(3), 603–618.

[^friedland]: Possibly Friedland, K. D., Stock, C., et al. (2012). Pathways between primary production and fisheries yields of large marine ecosystems. *PLoS ONE*, 7(1), e28945. _(to be filled in: confirm this is the study shown in lecture)_

[^cushing69]: Cushing, D. H. (1969). The regularity of the spawning season of some fishes. *Journal du Conseil International pour l'Exploration de la Mer*, 33(1), 81–92.

[^cushing90]: Cushing, D. H. (1990). Plankton production and year-class strength in fish populations: an update of the match/mismatch hypothesis. *Advances in Marine Biology*, 26, 249–293.
