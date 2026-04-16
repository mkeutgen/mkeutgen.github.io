+++
title = "Foundation Models for Physical Systems"
kicker = "Seminar notes — Rudy Morel"
deck = "Can a transformer trained across many PDE families learn to discover the evolution operator itself? A talk on DISCO and what it means for inferring physics from data."
date = "2026-04-15"
tags = ["machine-learning", "physics", "foundation-models", "pdes"]
author = "Maxime Keutgen"
toc = true
+++

## Motivation: solar physics

Hard to understand which active region is going to flare. The Sun is one of
the rare objects where the surface is colder than the atmosphere (contrary
to most planets) — order of $\sim 500$ times hotter corona. This is the
**coronal heating puzzle**.

## Two categories of problems

1. **Prediction** — weather forecasting (what's going to happen?)
2. **Inference** — what drives the dynamics? (understanding the physics)

## Foundation models for physical systems

How to tackle these problems across domains: biomedical imaging,
gravitational physics, quantum chemistry, astrophysics, weather prediction
$\Rightarrow$ **foundation models** — models built to learn joint
representations of the same underlying objects.

Two key concepts:

- Model trained on a **broad** set of data
- If trained correctly, can be used for a number of downstream tasks:
  retrieving rare objects, classification, etc.

Central question (Morel): *"What constitutes broad data?"*

### Weather prediction example

For short-range forecasting ($\leq 6$ hours), **Earth2** (NVIDIA) is the
first ML model that is SOTA, beating standard physics-based models.
Impressive — but what enables such predictive power?

## Probing for physics in spatio-temporal systems

Spatio-temporal systems with underlying PDEs — is the model aware that
there are underlying PDEs? If so, can we extract them?

### Setup: a simple PDE system

$$
\partial_t \, u_t(x) = g\!\Big(u_t(x),\; \nabla_x u_t(x),\; \nabla_x^2 u_t(x),\; \ldots\Big)
$$

Continuous dynamics. If we don't know the underlying PDE, we train on
different datasets with variability in:

- **Initial condition** $u_0(x)$
- **PDE coefficients** (e.g. diffusion constant, advection speed)
- **PDE class** (e.g. heat equation vs. wave equation vs. Navier–Stokes)

### Task formulation

Given a context of $T$ states $(u_{t-T+1}, \ldots, u_t)$, predict the next
state $u_{t+1}$. This is fundamentally an **in-context learning** task.
SOTA architecture: **Vision Transformers** — compute interactions between
patches in a sequence. The hope is that the transformer learns to condition
on the context to adapt its prediction.

### Two goals, two outcomes

| Goal | Achievable? |
|---|---|
| **Predicting** the dynamics | Yes |
| **Inferring** the dynamics (does the model know the PDE?) | In most cases, no |

Probing for PDE coefficients: train a linear classifier to retrieve PDE
coefficients from the model's activations $\Rightarrow$ the model **cannot**
do it. Tested across different activation layers — doesn't work [^qu2026].

{{< sidenote >}}
Morel does not consider the chaoticity of the underlying system in this
analysis — an interesting open question for nonlinear regimes.
{{< /sidenote >}}

## How to encode the physics?

### Neural operators

Learn the operator $\mathcal{F}_\theta$ such that

$$\mathcal{F}_\theta(u_k) = u_{k+1}$$

from pairs $(u_k, u_{k+1})$ in the training data. **Problem**: the dynamics
change. An operator trained on one set of dynamics may not generalise to
new ones — neural operators learn just **one** set of dynamics.

### Transformers vs. neural operators

|  | Generalise to multiple dynamics | Encode the physics |
|---|---|---|
| **Transformers** | Yes | No |
| **Neural operators** | No | Yes |

## DISCO: best of both worlds

**DISCO** — *Learning to DISCover an Evolution Operator* [^morel2024]. Key
idea: the **transformer learns to output the weights** of the operator
network $\Rightarrow$ the transformer acts as a **hypernetwork**.

$$
\text{Transformer}(u_{t-T+1}, \ldots, u_t) \;\longrightarrow\; \theta^* \;\longrightarrow\; \mathcal{F}_{\theta^*}(u_t) = u_{t+1}
$$

Multiple-physics pretraining: transformer + operator networks. This opens
the door to:

- **Zero-shot** generalisation to unseen PDE coefficients
- **Out-of-range** extrapolation beyond training distribution

{{< sidenote >}}
**Q&A.** For biophysical models mixing biological laws (empirical) with
physical laws (known), how should one decide what to learn vs. prescribe?
Morel's answer: use Bayesian inference and set the prior on the known
physics, letting the model learn only the empirical part.
{{< /sidenote >}}

## References

[^qu2026]: Qu, J. et al. (2026). *Probing PDE coefficients in transformer
    activations*. Workshop paper at ICLR 2026. _(full title not noted at talk.)_

[^morel2024]: Morel, R. et al. (2024). *DISCO: Learning to DISCover an
    Evolution Operator*. Preprint. _(citation pending — to be filled in
    when paper is public.)_
