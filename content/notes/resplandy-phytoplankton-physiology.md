+++
title   = "Phytoplankton Physiology and Growth: Light Limitation"
kicker  = "GEO428 Biological Oceanography — Laure Resplandy (Princeton)"
deck    = "The light side of the nutrient–light trade-off: photosynthetically active radiation, how light fades with depth, optical water types, and the photosynthesis–irradiance curve."
date    = "2026-10-05"
tags    = ["light-limitation", "euphotic-zone", "P-I-curve", "ocean-optics", "biological-oceanography", "geo428"]
author  = "Maxime Keutgen De Greef"
toc     = true
draft   = true
+++

My notes from this lecture are an outline only. The sections below give the
standard definitions behind each heading; values specific to the lecture are
marked to be filled in.

## The nutrient–light trade-off

Light comes from above; nutrients come from below. In stratified water the
surface is bright but stripped of nutrients, while deep water is rich in
nutrients but dark. Phytoplankton live where the two overlap. In the
subtropical gyres this overlap shows up as a deep chlorophyll maximum, well
below the surface.

## Photosynthetically active radiation

Phytoplankton use light between 400 and 700 nm: Photosynthetically Active
Radiation (PAR). PAR is measured as a **photon flux** (µmol photons m⁻² s⁻¹),
not as energy, because photosynthesis depends on the number of photons
absorbed.

## Light attenuation and the euphotic zone

Light decays roughly exponentially with depth (the Beer–Lambert law):

$$
I(z) = I_0 \, e^{-K_d z},
$$

where $I_0$ is PAR just below the surface and $K_d$ (m⁻¹) is the diffuse
attenuation coefficient. $K_d$ grows with everything in the water that absorbs
or scatters light: the water itself, phytoplankton, coloured dissolved organic
matter, and suspended particles.

The **euphotic zone** is the layer where there is enough light for
photosynthesis. By convention its base is the depth where PAR falls to 1% of
its surface value:

$$
z_{eu} = \frac{\ln 100}{K_d} \approx \frac{4.6}{K_d}.
$$

In clear gyre water ($K_d \approx 0.04$ m⁻¹) this gives about 115 m. In a
turbid coastal bay ($K_d \approx 0.3$ m⁻¹) it gives about 15 m.

## Case 1 and Case 2 waters

Ocean optics sorts water into two types.[^morel]

- **Case 1:** optical properties set by phytoplankton and the material that
  varies with them. Most of the open ocean.
- **Case 2:** also shaped by material that varies independently of
  phytoplankton, such as suspended sediment and coloured dissolved organic
  matter from rivers. Typical of coastal water.

_(to be filled in: what the lecture said about the two cases)_

## The photosynthesis–irradiance curve

The photosynthesis–irradiance (P–I) curve gives the photosynthetic rate $P$ as
a function of light $I$. It has three regions:

1. **Light-limited.** At low light, $P$ rises linearly with initial slope
   $\alpha$.
2. **Light-saturated.** At high light, $P$ levels off at $P_{\max}$. The
   transition is marked by the saturation irradiance $I_k = P_{\max}/\alpha$.
3. **Photoinhibited.** At very high light, $P$ can fall again as the
   photosynthetic machinery is damaged.

A common fit without photoinhibition is[^jassby]

$$
P = P_{\max} \tanh\!\left(\frac{\alpha I}{P_{\max}}\right).
$$

_(to be filled in: the lecture's P–I parameters and examples)_

## References

[^morel]: Morel, A., & Prieur, L. (1977). Analysis of variations in ocean color. *Limnology and Oceanography*, 22(4), 709–722.

[^jassby]: Jassby, A. D., & Platt, T. (1976). Mathematical formulation of the relationship between photosynthesis and light for phytoplankton. *Limnology and Oceanography*, 21(4), 540–547.
