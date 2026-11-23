+++
title   = "The Fate of Primary Production: Recycling, Export and Burial"
kicker  = "GEO428 Biological Oceanography — Laure Resplandy (Princeton)"
deck    = "Where the carbon fixed by phytoplankton goes: new versus regenerated production, the f-ratio and its nitrification problem, the pathways of the biological pump, and how fast sinking flux fades with depth."
date    = "2026-11-02"
tags    = ["new-production", "f-ratio", "nitrification", "biological-pump", "export", "Martin-curve", "biological-oceanography", "geo428"]
author  = "Maxime Keutgen De Greef"
toc     = true
draft   = true
+++

## Three fates

Organic matter made by phytoplankton has three possible fates:

1. **Recycling** in the surface ocean, where it fuels more production.
2. **Export** below the surface layer.
3. **Burial** in sediments.

## New and regenerated production

The paradigm set up in the late 1970s splits primary production by the source
of its nitrogen.[^dugdale][^eppley]

- **New production** uses nitrogen brought in from outside the euphotic zone:
  nitrate (NO₃⁻) mixed or upwelled from below, and dinitrogen (N₂) fixed from
  the atmosphere.
- **Regenerated production** uses nitrogen recycled inside the euphotic zone:
  ammonium (NH₄⁺), urea and other forms of Dissolved Organic Nitrogen (DON).
  Urea is a form of DON, but it behaves like ammonium: a readily available,
  recycled nutrient.

Eppley and Peterson (1979) argued that **at steady state, new production
balances export**. Nitrogen that enters the sunlit layer must leave it, mostly
as sinking Particulate Organic Carbon (POC). Export is tied to new production,
not to total Net Primary Production (NPP).

The **f-ratio** is the fraction of production that is new:

$$
f = \frac{\text{NP}}{\text{NP} + \text{RP}},
$$

where NP is new production and RP regenerated production.

- **High f-ratio:** subpolar and upwelling regions, with a high nutrient
  supply. Large cells such as diatoms take up the new nitrate.
- **Low f-ratio:** subtropical gyres. Small cells dominate and rely on
  recycled nitrogen.

## Two shifts in the paradigm

**The microbial loop (1980s).** Much of production is recycled through
bacteria and protists before it can be exported (see the microbial-loop
lecture).

**Nitrification in the euphotic zone.** Nitrification is the microbial
oxidation of ammonium to nitrite and then nitrate:

$$
\mathrm{NH_4^+} \rightarrow \mathrm{NO_2^-} \rightarrow \mathrm{NO_3^-}.
$$

It was long assumed that light inhibits nitrification, so all nitrate in the
sunlit layer had to come from below. Bess Ward's work showed that nitrifying
microbes are active in the euphotic zone.[^ward] This matters because nitrate
was the classical label of new production. Nitrate made by nitrification in the
euphotic zone is recycled nitrogen, so counting its uptake as new production
**misattributes regenerated production to new production** and overestimates
the f-ratio.

The lecture's figure: euphotic-zone nitrification may supply more than half of
the nitrate that phytoplankton use, in line with the global estimate of Yool et
al. (2007).[^yool] Correcting for it lowers f-ratio estimates substantially.
_(to be filled in: the before and after f-ratio values from the slide)_ This
was a big shift in how we think about export.

## How much is exported?

Organic carbon leaves the surface by three pathways:

1. **Sinking particles** (the gravitational pump).
2. **Physical transport** of dissolved and suspended organic matter by mixing
   and subduction (the physical pumps).
3. **Vertical migration** of zooplankton and fish, which feed at the surface
   and respire or excrete at depth. Day and night depth profiles of
   size-fractionated zooplankton biomass show this shift directly.

Global export budget from the lecture, in petagrams of carbon per year
(1 Pg = 10¹⁵ g):

| Component | Export (Pg C yr⁻¹) |
|---|---|
| Particulate organic carbon (POC) | 10 ± 4.5 |
| Dissolved organic carbon (DOC) | 2 ± 1 |
| Total organic carbon | 12.5 ± 4.5 |
| Particulate inorganic carbon (PIC, calcium carbonate) | 1.5 ± 1.5 |
| **Total** | **14 ± 5** |

By pathway: sinking about 70%, physical pumps about 20%, migration about
10%.[^nowicki] The lecture quoted a global f-ratio of about 0.4.

In nitrogen units, using the Redfield ratio:

$$
14~\text{Pg C} \times \frac{16~\text{mol N}}{106~\text{mol C}} \times \frac{14~\text{g N mol}^{-1}}{12~\text{g C mol}^{-1}} \approx 2.5~\text{Pg N yr}^{-1}.
$$

More than 95% of exported material is remineralised in the water column before
it reaches the sea floor. Burial is a small leftover.

## What the biological pump is

Laure defines the biological carbon pump as the **set of processes that
maintain the vertical gradient** of Dissolved Inorganic Carbon (DIC): low at
the surface, high at depth. The gradient results from the combined effect of
the downward export flux and the upward return of remineralised carbon by
circulation and mixing.

## Flux attenuation: the Martin curve

Sinking flux fades with depth as particles are eaten and remineralised. The
standard description is a power law, the Martin curve:[^martin]

$$
F(z) = F_{100} \left(\frac{z}{100}\right)^{-b},
$$

where $F(z)$ is the flux at depth $z$ (m), $F_{100}$ the flux at 100 m, and $b$
the attenuation exponent, typically 0.7–0.9. A larger $b$ means faster
attenuation. With $b = 0.86$, only about 14% of the flux at 100 m reaches
1000 m.

## Not all pumps are equally efficient

Three ratios measure efficiency:

- **e-ratio** = export flux at a shallow reference depth / NPP.
- **Ez-ratio** = export flux at the base of the euphotic zone / NPP.[^buesseler09]
- **Transfer efficiency** $T_{\text{eff}}$ = export flux at a deeper depth /
  export flux at a shallower depth.

### ALOHA versus K2

The lecture compared two sites from the VERtical Transport In the Global Ocean
(VERTIGO) study.[^vertigo]

- **Station ALOHA** (A Long-term Oligotrophic Habitat Assessment), north of
  Hawaii, in the subtropical gyre. Small cells, mostly regenerated production.
- **K2**, in the western subarctic North Pacific. Diatoms, more new
  production.

At steady state, export balances new production. ALOHA relies mostly on
regenerated production, has a low f-ratio, and so exports less relative to its
NPP than K2.

Transfer efficiency differs too. VERTIGO found that about 20% of the flux at
150 m reached 500 m at ALOHA, against about 50% at K2. Flux fades faster
(larger $b$) at ALOHA. K2 remineralises a smaller *fraction* of its sinking
flux in the twilight zone, though more carbon in absolute terms, because it
exports more. Three reasons:

- Large diatom aggregates and big fecal pellets at K2 sink fast, so they spend
  less time being eaten on the way down.
- Cold water slows bacterial respiration. Across sites, $b$ rises with the
  temperature of the upper 500 m.[^marsay]
- At ALOHA, small, slow-sinking particles are mostly recycled near the top.

The pattern depends on the depth range. Below about 1000 m, syntheses of
sediment-trap data find the opposite: high latitudes transfer carbon less
efficiently than the subtropics, probably because carbonate minerals weigh
down and protect particles at depth.[^henson]

{{< sidenote >}}
My raw note recorded $b$ as higher at K2 than at ALOHA. That matches the
deep-trap pattern, not VERTIGO's 150–500 m result. Check which depth range the
slide used. My note also placed K2 in the North Atlantic; it is in the North
Pacific.
{{< /sidenote >}}

## From export to carbon storage

Deeper injection of carbon gives longer storage. Carbon remineralised at a few
hundred metres can return to the surface within years to decades. Carbon
released below about 1000 m typically stays away from the atmosphere for
centuries.[^siegel]

## References

[^dugdale]: Dugdale, R. C., & Goering, J. J. (1967). Uptake of new and regenerated forms of nitrogen in primary productivity. *Limnology and Oceanography*, 12(2), 196–206.

[^eppley]: Eppley, R. W., & Peterson, B. J. (1979). Particulate organic matter flux and planktonic new production in the deep ocean. *Nature*, 282, 677–680.

[^ward]: Ward, B. B. — work on nitrification in the euphotic zone. _(to be filled in: the paper shown in lecture)_

[^yool]: Yool, A., Martin, A. P., Fernández, C., & Clark, D. R. (2007). The significance of nitrification for oceanic new production. *Nature*, 447, 999–1002.

[^nowicki]: Source of the export budget and pathway shares shown in lecture. _(to be filled in; the pathway shares match Nowicki, M., DeVries, T., & Siegel, D. A. (2022). Quantifying the carbon export and sequestration pathways of the ocean's biological carbon pump. *Global Biogeochemical Cycles*, 36, e2021GB007083.)_

[^martin]: Martin, J. H., Knauer, G. A., Karl, D. M., & Broenkow, W. W. (1987). VERTEX: carbon cycling in the northeast Pacific. *Deep-Sea Research Part A*, 34(2), 267–285.

[^buesseler09]: Buesseler, K. O., & Boyd, P. W. (2009). Shedding light on processes that control particle export and flux attenuation in the twilight zone of the open ocean. *Limnology and Oceanography*, 54(4), 1210–1232.

[^vertigo]: Buesseler, K. O., Lamborg, C. H., Boyd, P. W., et al. (2007). Revisiting carbon flux through the ocean's twilight zone. *Science*, 316, 567–570.

[^marsay]: Marsay, C. M., Sanders, R. J., Henson, S. A., Pabortsava, K., Achterberg, E. P., & Lampitt, R. S. (2015). Attenuation of sinking particulate organic carbon flux through the mesopelagic ocean. *Proceedings of the National Academy of Sciences*, 112(4), 1089–1094.

[^henson]: Henson, S. A., Sanders, R., & Madsen, E. (2012). Global patterns in efficiency of particulate organic carbon export and transfer to the deep ocean. *Global Biogeochemical Cycles*, 26, GB1028.

[^siegel]: Siegel, D. A., DeVries, T., Doney, S. C., & Bell, T. (2021). Assessing the sequestration time scales of some ocean-based carbon dioxide reduction strategies. *Environmental Research Letters*, 16, 104003.
