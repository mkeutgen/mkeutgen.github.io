+++
title = "AI for Climate — Princeton Workshop"
kicker = "Workshop notes — AI4Climate, Princeton"
deck = "Three short takes: Socolow on AI energy demand and 1970s electricity parallels; Lin on AI-assisted tropical cyclone impact modelling; Lam on workflow gaps."
date = "2026-04-21"
tags = ["climate", "machine-learning", "energy", "tropical-cyclones"]
author = "Maxime Keutgen De Greef"
toc = true
+++

Opened by Natalie, with the 1968 *Earthrise* photograph as the first slide.

---

## Robert Socolow — AI energy demand in historical perspective

Socolow arrived at Princeton in 1971. At the time, electricity demand was
growing exponentially and projections extrapolated that curve indefinitely.
It levelled off. What the 1970s forecasters missed was the transition from
throughput-intensive to service-intensive use.

His claim: AI is a new large energy consumer that will follow the same arc.
The question is not whether demand will level off but when, and how much
carbon will be emitted before it does.

He organises the problem across four domains:

| Domain | Examples |
|---|---|
| Data acquisition | Submetering |
| Thermodynamics | Cogeneration, heat pumps |
| Engineering design | Cooling, drag, embodied energy in hardware |
| Ethics | Who benefits, who bears the cost? |

Familiar analogues from other sectors: Corporate Average Fuel Economy
(CAFE)-style standards and labelling,
Jevons rebound effects, overshoot risks (tight buildings → indoor air
quality; leaded gasoline → water contamination).

**Provocative framing**: is today's data centre the 1960s car — large,
inefficient, with no market pressure to improve — before the efficiency
revolution arrived? Socolow's bet: the improvements will come from *outside*
the incumbent AI firms: architects, statisticians, and system designers who
do not have a vested interest in large-scale compute.

---

## Grace Lam — Workflow gaps

The bottleneck in climate AI is not data. The question is how to use AI to
improve **workflows**: the human-in-the-loop processes around data
interpretation, model output communication, and decision support.

---

## Ning Lin — AI for tropical cyclone impact modelling

Lin works on climate impacts of tropical cyclones. The modelling chain runs
from global climate scenarios down to individual infrastructure decisions:

1. **Global scenarios** — plausible future climate states.
2. **TC generation** — General Circulation Models (GCMs) cannot resolve
   TCs at native resolution; dedicated downscaling is required.
3. **Hazard modelling** — wind, storm surge, flooding.
4. **Impact modelling** — effects on people, buildings, infrastructure.
5. **Decision support** — how to act on the information.

AI enters at every step. Three areas Lin highlighted:

**Replace**: several AI models are now competitive with Numerical Weather
Prediction (NWP) for short-range
forecasting. Open question: can we *trust* them? The reliability of the AI
model depends partly on the reliability of the physical model used for
training — and that physical model cannot resolve TCs well to begin with.

**Speed up**: run far larger ensembles at a fraction of the cost.

**Decision-making under uncertainty**: reinforcement learning applied to
coastal protection design, using large ensembles to explore the space of
interventions.
