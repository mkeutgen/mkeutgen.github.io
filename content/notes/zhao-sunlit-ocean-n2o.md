+++
title = "The Sunlit Ocean as an Overlooked Source of Nitrous Oxide"
kicker = "Seminar notes — Yangyang Zhao (Princeton)"
deck = "A process-based N₂O scheme in MOM6-COBALTv3 suggests the euphotic zone is a widespread source missed by empirical models — and that the ocean N₂O–climate feedback may be positive, not negative."
date = "2026-06-15"
tags = ["biogeochemistry", "nitrous-oxide", "ocean-modelling", "climate-feedbacks", "nitrogen-cycle"]
author = "Maxime Keutgen De Greef"
toc = true
draft = true
+++

## Why oceanic N₂O matters

The ocean contributes roughly **one-third of global natural nitrous oxide
(N₂O) emissions**. N₂O is a long-lived greenhouse gas, so getting the ocean
source right matters for climate projections.

There is a persistent **model–observation mismatch**: many ocean models
underestimate oceanic N₂O emissions, by up to ~50% relative to observations.
A natural suspicion is that the models are missing a production term.

## Two production pathways

N₂O is produced through two major microbial pathways:

1. **Nitrification** — modulated by light and ammonium (NH₄⁺). N₂O is a
   byproduct of the oxidation of ammonium toward nitrate.
2. **Denitrification** — modulated by oxygen, substrate availability, and
   particulate organic matter (POM). N₂O appears as an intermediate.

Under very low oxygen, N₂O can also be produced along the denitrification
pathway.

## Observational evidence for production in the euphotic zone

Several lines of evidence point to N₂O being produced *in situ* within the
sunlit **euphotic zone (EZ)**, rather than only being supplied from below:

- **Supersaturation maxima in sunlit surface water.** N₂O supersaturation
  peaks have been observed near the surface [^wan].
- **Air–sea fluxes exceed the diapycnal supply** from the subsurface
  [^charpentier2007] — if more N₂O leaves the surface than mixing can deliver
  from depth, the balance must come from **local production**.
- This implicates **nitrification within the EZ** as the missing source.

Collectively, these findings point to a widespread sunlit-ocean source of N₂O
that is overlooked in current global ocean models and Earth System Models
(ESMs) using conventional **empirical** N₂O schemes — potentially leading to
systematic biases in the simulated source.

## Modelling the sunlit source: MOM6-COBALTv3

The talk uses **MOM6-COBALTv3** with an N₂O module that resolves both
pathways explicitly:

- **Nitrification** — N₂O as a byproduct.
- **Denitrification** — N₂O as an intermediate.

The key experiment contrasts two configurations:

| Configuration | N₂O in the euphotic zone | Nature |
|---|---|---|
| **EZ off** | suppressed | conventional empirical scheme |
| **EZ on** | resolved | process-based scheme |

**Main results:**

- Sunlit-ocean N₂O production is **underestimated by the empirical (EZ off)
  scheme** relative to the process-based (EZ on) scheme.
- In the process scheme, the **N₂O hotspot sits in the top ~100 m**, inside
  the euphotic zone.
- About **8% of the emission increase** comes from denitrification within the
  EZ; the remainder is supplied by **transport from the subsurface**.

{{< sidenote >}}
The mechanism hinges on a community-level interaction: phytoplankton and
nitrifiers **compete for ammonium (NH₄⁺)**. When phytoplankton demand for
NH₄⁺ falls, more substrate is left for nitrifiers — and therefore more N₂O.
{{< /sidenote >}}

A further consequence: **ecosystem dynamics decouple N₂O from oxygen and net
primary production (NPP)** at mid-to-high latitudes, so the simple "low oxygen
→ more N₂O" intuition does not hold everywhere.

## Implications for climate feedbacks

**Core claim:** the sign of the oceanic N₂O–climate feedback may be
**positive**, not negative as conventionally assumed. This is a paradigm-level
revision with direct consequences for ESM projections.

### Conventional paradigm — negative feedback

The standard view holds that the **Oxygen Deficient Zone (ODZ)** in the deep
ocean interior is the primary source of oceanic N₂O, produced mainly via
denitrification under low-oxygen conditions. The chain runs:

$$
\text{warming} \to \text{stratification} \uparrow \;\to\; \text{NPP} \downarrow
\;\to\; \text{O}_2\text{ consumption} \downarrow \;\to\; \text{ODZ} \downarrow
\;\to\; \text{denitrification} \downarrow \;\to\; \text{N}_2\text{O} \downarrow
$$

Increased stratification suppresses nutrient supply to the surface, lowering
NPP. Less organic matter sinks, so less oxygen is consumed at depth, which
constrains ODZ expansion — or even causes contraction. Fewer anoxic
conditions mean less denitrification, less N₂O, and reduced emissions.
**Warming partially dampens itself.**

### Revised paradigm — positive feedback

The new framework shifts the primary N₂O source **upward**, to the shallow
subsurface and mesopelagic, where **nitrification** (NH₄⁺ → NO₂⁻ → NO₃⁻, with
N₂O as a byproduct) dominates. Three mechanisms collectively flip the sign:

1. **Phytoplankton–nitrifier competition for NH₄⁺** (nutrient-depleted
   tropics and subtropics). When warming suppresses NPP, phytoplankton demand
   for ammonium falls, leaving more NH₄⁺ for nitrifiers. More substrate → more
   nitrification → more N₂O. Strikingly, the **same NPP decline** that reduces
   N₂O in the conventional model **increases** it here, by relieving
   competitive pressure on nitrifiers.
2. **Direct thermal acceleration of microbial metabolism** (nutrient-rich
   upwelling zones and high latitudes). Nitrification and denitrification
   rates are temperature-sensitive; where substrate is not limiting, warming
   alone raises enzymatic throughput and thus N₂O yield. A straightforward
   kinetic effect, apparently underweighted in prior budgets.
3. **Uncertain transport pathways** (upwelling vs. subtropical gyres). How
   subsurface N₂O reaches the surface — via upwelling in productive eastern
   boundary systems or via gas exchange across subtropical gyres — remains
   poorly constrained. This uncertainty propagates into emission estimates and
   may explain part of the inter-model spread.

### Why the sign reversal matters

N₂O has a global warming potential (GWP) roughly **270–300× that of CO₂** on a
100-year horizon, and it is not short-lived. Even a modest increase in ocean
N₂O emissions under warming is a meaningful **amplifying** feedback. If ESMs
are parameterized around ODZ-dominated denitrification as the primary source,
they misrepresent the **vertical distribution** of N₂O production and will
systematically underestimate future emissions.

## Broader context

This fits a recurring pattern in ocean biogeochemistry: the **vertical
dimension** is where most of the mechanistic action lives, yet it is also
where observational coverage is weakest and where models diverge most. The
phytoplankton–nitrifier competition for NH₄⁺ plays out in the euphotic zone
and just below — a depth range that Argo floats sample inconsistently and that
biogeochemical models often represent with coarse vertical resolution.

## References

[^wan]: Wan, X. S. et al. *N₂O supersaturation maxima in the sunlit surface
    ocean.* Nature Geoscience. _(year and full citation to be filled in.)_

[^charpentier2007]: Charpentier, J. et al. (2007). *N₂O distribution and its
    air–sea flux versus diapycnal supply in the South Pacific.* _(full
    citation to be filled in.)_
