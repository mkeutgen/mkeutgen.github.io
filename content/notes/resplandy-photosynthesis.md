+++
title   = "Photosynthesis: Light Reactions, the Calvin Cycle and the Carbon Problem"
kicker  = "GEO428 Biological Oceanography — Laure Resplandy (Princeton)"
deck    = "How phytoplankton turn light into chemical energy and fix carbon, and why a slow, CO₂-hungry enzyme forces them to concentrate carbon inside the cell."
date    = "2026-09-21"
tags    = ["photosynthesis", "Calvin-cycle", "RuBisCO", "pigments", "carbon-concentrating-mechanisms", "biological-oceanography", "geo428"]
author  = "Maxime Keutgen De Greef"
toc     = true
draft   = true
+++

## Two linked reactions

Photosynthesis runs in two stages.

1. **Light reactions.** Pigments absorb photons. The absorbed energy splits
   water, which releases oxygen (O₂) and frees electrons and protons. These
   drive the production of two energy carriers: nicotinamide adenine
   dinucleotide phosphate (NADPH), which supplies reducing power, and
   adenosine triphosphate (ATP), which stores chemical energy.
2. **Dark, or light-independent, reactions.** The Calvin cycle spends that ATP
   and NADPH to fix carbon dioxide (CO₂) into sugar.

The net reaction is

$$
6\,\mathrm{CO_2} + 6\,\mathrm{H_2O} \xrightarrow{\ \text{light}\ } \mathrm{C_6H_{12}O_6} + 6\,\mathrm{O_2}.
$$

"Dark" is a misnomer. The Calvin cycle runs during the day; it just does not
use photons directly.

## Where it happens

In eukaryotic algae, photosynthesis takes place in the chloroplast. Its
structure follows its function: the chloroplast is packed with membranes.

- The **thylakoids** are flattened membrane sacs. They carry all the
  pigment–protein complexes of the light reactions. In land plants and green
  algae, thylakoids sit in stacks called **grana**.
- The **stroma** is the fluid around the thylakoids. The Calvin cycle runs
  there.

Cyanobacteria have no chloroplasts. Their thylakoids sit directly in the cell.
Chloroplasts are in fact descended from a cyanobacterium that a eukaryotic cell
engulfed and kept (endosymbiosis).

## Which light drives photosynthesis: Engelmann's experiment

In 1882, Theodor Engelmann projected a spectrum (light split by a prism) along a
filament of green alga in water that also held aerobic bacteria.[^engelmann]
These bacteria swim toward oxygen. They crowded along the parts of the filament
lit by red and by blue-violet light, with only a few in the green. The alga
releases oxygen as it photosynthesizes, so the crowd of bacteria maps the rate
of photosynthesis by wavelength. This was an early **action spectrum**.

{{< sidenote >}}
My question: the bacteria are spread continuously, not in discrete red and
blue bands, so some sit in the green. Why? The bacteria are not coloured; they
report oxygen. Two effects smooth the pattern. First, absorption in the green
is low but not zero: chlorophyll absorbs little there, but carotenoids and
other accessory pigments absorb some. Second, oxygen diffuses away from where
it is made, and the bacteria move, which blurs any sharp boundary. Engelmann's
result is a population-level measure of rate, not an on/off map.
{{< /sidenote >}}

## Why a bloom looks green

Water colour is the light that is *not* absorbed. Chlorophyll absorbs strongly
in the blue and the red and weakly in the green. A dense bloom therefore sends
green light back to the eye, and to ocean-colour satellites, which use this to
estimate chlorophyll.

Accessory pigments fill part of this "green gap". **Phycoerythrin** absorbs
green light; it is found in cyanobacteria such as *Synechococcus* and in red
algae. **Phycocyanin**, by contrast, absorbs orange-red light (around 620 nm)
and looks blue.

## The Calvin cycle

The cycle has three phases.

1. **Fixation.** The enzyme ribulose-1,5-bisphosphate carboxylase/oxygenase
   (RuBisCO) attaches CO₂ to a five-carbon sugar, ribulose-1,5-bisphosphate
   (RuBP). The product splits into two three-carbon molecules of
   3-phosphoglycerate (3-PGA).
2. **Reduction.** ATP and NADPH from the light reactions convert 3-PGA into
   glyceraldehyde-3-phosphate (G3P), a three-carbon sugar.
3. **Regeneration.** Most of the G3P is rearranged, at a further cost in ATP,
   back into RuBP so the cycle can continue.

The bookkeeping: three turns fix 3 CO₂ and make 6 G3P. Five G3P are recycled
into 3 RuBP; one leaves the cycle as net product. Two of those make one
glucose. The cost per 3 CO₂ fixed is 9 ATP and 6 NADPH.

## How much CO₂ is there in seawater?

Not much. Dissolved Inorganic Carbon (DIC) in surface seawater is about
2000 µmol kg⁻¹, but about 90% of it is bicarbonate (HCO₃⁻) and most of the rest
is carbonate (CO₃²⁻). Dissolved CO₂ itself is only about 1% of DIC, roughly
10–20 µM.[^frenger]

## RuBisCO is slow and has a low affinity for CO₂

Enzyme kinetics follow the Michaelis–Menten equation:

$$
V = \frac{V_{\max}\,[S]}{K_M + [S]},
$$

where $V$ is the reaction rate, $[S]$ the substrate concentration, $V_{\max}$
the rate when the enzyme is saturated, and $K_M$ the **half-saturation
constant**: the concentration at which $V = V_{\max}/2$. $K_M$ is an inverse
measure of affinity. A low $K_M$ means the enzyme works well at low
concentration.

For RuBisCO and CO₂, the lecture gave:

- **Diatoms:** $K_M \approx$ 20–100 µM.
- **Cyanobacteria:** $K_M >$ 100 µM.
- **Ambient seawater:** CO₂ below 20 µM.

So RuBisCO would run well below half speed on ambient CO₂. A diatom enzyme with
$K_M = 50$ µM in 15 µM CO₂ runs at $15/(50+15) \approx 23\%$ of $V_{\max}$. A
cyanobacterial enzyme with $K_M = 150$ µM runs at about 9%.

RuBisCO also reacts with O₂ (the "oxygenase" in its name), which wastes energy.
The enzyme evolved when the atmosphere held far more CO₂ and almost no O₂. It
has become more CO₂-specific over time.

## Carbon-concentrating mechanisms

The way out is to raise CO₂ around RuBisCO. Phytoplankton do this with
Carbon-Concentrating Mechanisms (CCMs):

- They **pump bicarbonate**, the abundant form of DIC, into the cell.
- The enzyme **carbonic anhydrase** speeds up the conversion of HCO₃⁻ to CO₂
  next to RuBisCO.

In cyanobacteria, RuBisCO and carbonic anhydrase are packed together in protein
compartments called carboxysomes. Many eukaryotic algae use a comparable
structure, the pyrenoid. An effective CCM is why cyanobacteria can afford a
low-affinity RuBisCO.

## References

[^engelmann]: Engelmann, T. W. (1882). Ueber Sauerstoffausscheidung von Pflanzenzellen im Mikrospektrum. *Botanische Zeitung*, 40, 419–426.

[^frenger]: Frenger et al. — the paper cited in lecture for seawater CO₂. _(to be filled in)_
