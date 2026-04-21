+++
title = "Welcome"
description = "Research notes from Princeton AOS."
date = "2024-12-05"
tags = ["research", "climate", "biogeochemistry"]
author = "Maxime Keutgen De Greef"
+++

Welcome to my notes and updates as I work toward my PhD in atmospheric and oceanic sciences at Princeton University. My research centers on climate science and biogeochemistry, with past projects in geochemistry and compositional data analysis.

I completed my undergraduate degree in geosciences at the University of Namur, a small institution located in the heart of Wallonia, the French-speaking region of Belgium. There, I learnt how to solve not too complicated differential equations, how to map 300 million years old coral reefs and how to dissect a shark and a crab, among other things.

Then, I moved to Leuven to pursue my Master's degree in statistics at the Catholic University of Leuven, a 600-year-old institution that counts among its alumni many Renaissance figures, among them Mercator, after whom the map projection is named.

For my general written exam at Princeton, I worked on the eddy subduction pump, a biological carbon pump driven by submesoscale eddies (scales below ~20 km). Together with Prof. Laure Resplandy and Mathieu Poupon, we detected this pump activity at the _global scale_ for the first time — previous work had been confined to specific ocean regions such as parts of the Southern Ocean, the Gulf Stream, and the Kuroshio. Central to this was a _statistical detection algorithm_ that replaced earlier detection methods and made it possible to apply the analysis globally using Argo float data. This work is now published in *Global Biogeochemical Cycles* [^keutgen2026] and was covered by [Phys.org](https://phys.org/news/2026-04-ocean-eddies-carbon.html) and [Eos](https://eos.org/research-spotlights/eddy-or-not-do-eddies-actually-transport-that-much-carbon).

Currently, I am developing a new type of ocean biogeochemical models. Ocean biogeochemical models are ocean models which tell us where phytoplankton, zooplankton, and chemical elements such as carbon, oxygen, nitrogen are transported and through which processes.

Typically, ocean biogeochemical models are actually (at least) 2 models coupled together : the physical-dynamical model, which model the water currents, salinity and temperature and the biogeochemical model proper. Moreover, they can be further coupled to models of the atmosphere or of the land, to build a full-fledged Earth System Model.

The practical challenge is scale and complexity. These models are initialized from imperfect estimates of past ocean states and then solve large systems of equations every few minutes, across millions of spatial locations, for decades of simulated time. They are powerful, but also expensive, opaque, and difficult to experiment with.

Most importantly, because these are big complicated machines to work with, it means that currently, very few institutions in the _world_ have both the money and the people to run them. My research may change that. 

I am currently building AI models of the ocean, trained on Princeton's traditional biogeochemical models. These AI models run much faster than the models they are trained on, and on far less expensive hardware — think one $5,000 GPU instead of a $1,000,000 high-performance computing cluster. This holds promise for researchers at Princeton who want to understand their models faster and more cheaply, but most importantly it could address a _fundamental resource gap_ between top-tier institutions such as MIT, IPSL, Princeton, the Max Planck Institute, and Tsinghua, and institutions that lack the resources to run traditional ocean models.


If you would like to get in touch—about research, science and society, the PhD application process at Princeton, or related topics—feel free to send me an email.

[^keutgen2026]: Keutgen De Greef, M., Resplandy, L., & Poupon, M. A. (2026). Global eddy subduction carbon pump from Argo floats. *Global Biogeochemical Cycles*, 40, e2025GB008912. https://doi.org/10.1029/2025GB008912
