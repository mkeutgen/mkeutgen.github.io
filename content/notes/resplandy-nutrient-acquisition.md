+++
title   = "Nutrient Acquisition: What Limits Phytoplankton Growth"
kicker  = "GEO428 Biological Oceanography — Laure Resplandy (Princeton)"
deck    = "Building biomass takes more than carbon: Redfield stoichiometry, Liebig's law of the minimum, which elements are scarce relative to need, and the ways two nutrients can limit growth together."
date    = "2026-09-23"
tags    = ["nutrients", "Redfield-ratio", "nutrient-limitation", "co-limitation", "trace-metals", "biological-oceanography", "geo428"]
author  = "Maxime Keutgen De Greef"
toc     = true
draft   = true
+++

Building biomass takes more than carbon. The lecture had three parts:

1. Nutrient limitation.
2. Modelling nutrient uptake and cell growth rate.
3. Growth and uptake strategies, and what lab experiments can and cannot tell
   us.

These notes cover the first part. _(to be filled in: parts 2 and 3)_

## The phytoplankton recipe: the Redfield ratio

Phytoplankton turn photosynthetic sugars into lipids, proteins and nucleic
acids in roughly fixed proportions. On average, the cellular ratio of carbon to
nitrogen to phosphorus is

$$
\mathrm{C : N : P} = 106 : 16 : 1,
$$

the Redfield ratio.[^redfield] A cell therefore needs about $16/106 \approx 0.15$
atoms of nitrogen (N) for every atom of carbon (C).

## Carbon does not limit growth

Compare what seawater supplies with what cells need.

- Dissolved Inorganic Carbon (DIC) is about 2000 µM.
- Nitrate (NO₃⁻) is about 10–40 µM in the deep ocean, and close to zero at
  the surface of the subtropical gyres.

Seawater C:N is then about $2000/30 \approx 70$, against a cellular need of
$106/16 \approx 6.6$. Carbon is about ten times in excess relative to
nitrogen, so total carbon does not limit how much biomass can form.

{{< sidenote >}}
This sits alongside the photosynthesis lecture, where CO₂ *was* a problem.
There the issue was kinetic: dissolved CO₂ is a small fraction of DIC and
RuBisCO has a low affinity for it. Cells solve that with carbon-concentrating
mechanisms. The total supply of carbon is not the constraint.
{{< /sidenote >}}

## Liebig's law of the minimum

Growth is limited by the nutrient in shortest supply **relative to the cell's
requirement**, not by the scarcest nutrient in absolute terms. The usual image
is a barrel with staves of different lengths: the water level is set by the
shortest stave. In this view only one nutrient limits at a time.

Strictly, Liebig's law is about **yield**: how much biomass can be built from
the stock available. Yield is set by mass conservation and stoichiometry.
With plenty of light and carbon but no nitrogen, no biomass forms. This is
different from limitation of growth **rate**, which is the subject of the
uptake models in part 2.

## Which elements might limit?

To rank candidates, divide each element's concentration in seawater by the
phytoplankton requirement, and normalise to nitrogen. An element with a ratio
above 1 runs out after nitrogen; one below 1 runs out first.[^moore]

- **Calcium and nickel** are close to 1 but still in excess relative to
  nitrogen. They are not limiting.
- **Cobalt, manganese and iron** are deficient relative to nitrogen. They are
  likely to limit.
- Among phosphorus, cobalt, iron, cadmium and manganese, cobalt looks the most
  deficient on this measure. In practice, cobalt is far more **substitutable**
  than nitrogen: other metals can take over its roles in the cell. The ratio
  alone overstates how limiting it is.

## Co-limitation

Liebig's one-at-a-time rule often fails. **Co-limitation** means two or more
nutrients limit growth together. The lecture's examples map onto the three
types defined by Saito et al. (2008):[^saito]

1. **Independent (simultaneous) co-limitation.** Two nutrients are drawn down
   equally relative to what cells need. In the subtropical gyres, nitrogen and
   phosphorus are both drawn down in proportion to cell requirements.
2. **Substitution.** Either nutrient can do the same job. Zinc and cobalt can
   each serve as the metal at the active site of carbonic anhydrase in diatoms.
3. **Dependence.** One nutrient is needed to acquire another. Adding
   phosphorus and iron triggers nitrogen fixation by *Trichodesmium* in the
   North Atlantic.[^mills] Nitrogen fixers take nitrogen from the atmosphere,
   but the nitrogen-fixing enzyme (nitrogenase) is iron-rich, and growth still
   needs phosphorus.

A fourth case comes from diversity rather than physiology. In **community
co-limitation**, different phytoplankton in the same water are limited by
different nutrients. Adding one nutrient stimulates one group; adding another
stimulates a different group. The community as a whole looks co-limited.

## References

[^redfield]: Redfield, A. C. (1958). The biological control of chemical factors in the environment. *American Scientist*, 46(3), 205–221.

[^moore]: Source of the seawater-to-requirement figure shown in lecture. _(to be filled in: possibly Moore, C. M., et al. (2013). Processes and patterns of oceanic nutrient limitation. *Nature Geoscience*, 6, 701–710.)_

[^saito]: Saito, M. A., Goepfert, T. J., & Ritt, J. T. (2008). Some thoughts on the concept of colimitation: Three definitions and the importance of bioavailability. *Limnology and Oceanography*, 53(1), 276–290.

[^mills]: Mills, M. M., Ridame, C., Davey, M., La Roche, J., & Geider, R. J. (2004). Iron and phosphorus co-limit nitrogen fixation in the eastern tropical North Atlantic. *Nature*, 429, 292–294. _(to be filled in: confirm this is the study shown in lecture)_
