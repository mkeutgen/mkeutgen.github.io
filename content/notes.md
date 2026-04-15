+++
title = "Seminar Notes"
description = "Notes from talks on foundation models, neural ODEs, and dynamical systems."
date = "2026-04-15"
tags = ["machine-learning", "physics", "dynamical-systems", "foundation-models"]
author = "Maxime Keutgen"
+++

# Rudy Morel — Foundation Models for Physical Systems

## Motivation: Solar Physics

Hard to understand which active region is going to flare. The Sun is one of the rare objects where the surface is colder than the atmosphere (contrary to most planets) — order of $\sim 500$ times hotter corona. This is the **coronal heating puzzle**.

## Two Categories of Problems

1. **Prediction** — weather forecasting (what's going to happen?)
2. **Inference** — what drives the dynamics? (understanding the physics)

## Foundation Models for Physical Systems

How to tackle these problems across domains: biomedical imaging, gravitational physics, quantum chemistry, astrophysics, weather prediction $\Rightarrow$ **Foundation Models** — models built to learn joint representations of the same underlying objects.

Two key concepts:
- Model trained on a **broad** set of data
- If trained correctly, can be used for a number of downstream tasks: retrieving rare objects, classification, etc.

Central question (Morel): *"What constitutes broad data?"*

### Weather Prediction Example

For short-range forecasting ($\leq 6$ hours), **Earth2** (NVIDIA) is the first ML model that is SOTA, beating standard physics-based models.

Impressive — but what enables such predictive power?

## Probing for Physics in Spatio-Temporal Systems

Spatio-temporal systems with underlying PDEs — is the model aware that there are underlying PDEs? If so, can we extract them?

### Setup: A Simple PDE System

$$\partial_t \, u_t(x) = g\!\Big(u_t(x),\; \nabla_x u_t(x),\; \nabla_x^2 u_t(x),\; \ldots\Big)$$

Continuous dynamics. If we don't know the underlying PDE, we train on different datasets with variability in:

- **Initial condition** $u_0(x)$
- **PDE coefficients** (e.g. diffusion constant, advection speed)
- **PDE class** (e.g. heat equation vs. wave equation vs. Navier–Stokes)

### Task Formulation

Given a context of $T$ states $(u_{t-T+1}, \ldots, u_t)$, predict the next state $u_{t+1}$.

This is fundamentally an **in-context learning** task. SOTA architecture: **Vision Transformers** — compute interactions between patches in a sequence. The hope is that the transformer learns to condition on the context to adapt its prediction.

### Two Goals, Two Outcomes

| Goal | Achievable? |
|---|---|
| **Predicting** the dynamics | Yes |
| **Inferring** the dynamics (does the model know the PDE?) | In most cases, **no** |

Probing for PDE coefficients: train a linear classifier to retrieve PDE coefficients from the model's activations $\Rightarrow$ the model **cannot** do it. Tested across different activation layers — doesn't work.

> Ref: Qu et al., Workshop paper at **ICLR 2026** — finding PDE coefficients linearly in activations.

Morel does not consider the chaoticity of the system here.

## How to Encode the Physics?

### Neural Operators

Learn the operator $\mathcal{F}_\theta$ such that:

$$\mathcal{F}_\theta(u_k) = u_{k+1}$$

from pairs $(u_k, u_{k+1})$ in the training data.

**Problem**: the dynamics change. An operator trained on one set of dynamics may not generalise to new ones — neural operators learn just **one** set of dynamics.

### Transformers vs. Neural Operators

| | Generalise to multiple dynamics | Encode the physics |
|---|---|---|
| **Transformers** | Yes | No |
| **Neural Operators** | No | Yes |

## DISCO: Best of Both Worlds

**DISCO** — *Learning to DISCover an Evolution Operator* (Rudy Morel).

Key idea: the **transformer learns to output the weights** of the operator network $\Rightarrow$ the transformer acts as a **hypernetwork**.

$$\text{Transformer}(u_{t-T+1}, \ldots, u_t) \;\longrightarrow\; \theta^* \;\longrightarrow\; \mathcal{F}_{\theta^*}(u_t) = u_{t+1}$$

**Multiple-physics pretraining**: Transformer + Operator Networks.

This opens the door to:
- **Zero-shot** generalisation to unseen PDE coefficients
- **Out-of-range** extrapolation beyond training distribution

**Q&A** — For biophysical models mixing biological laws (empirical) with physical laws (known), how should one decide what to learn vs. prescribe? Morel's answer: use Bayesian inference and set your prior on the known physics, letting the model learn only the empirical part.

---

# Melchior Peter — Neural ODEs for Inference and Optimisation

## Motivation: Time-Domain Astronomy

In time-domain astronomy, we observe sudden flux variations — e.g. a supernova causing a brightness spike on a flux vs. MJD (time) plot. The question: should we trigger follow-up observations with another telescope?

One can build time-series classifiers, but a supernova is a **physical object** with inertia, conservation laws, etc. — even if the exact governing equations are unknown. Can we exploit this structure?

## Neural ODEs

Standard governing equation:

$$\partial_t \, \mathbf{x} = f(\mathbf{x}, t; \, \boldsymbol{\phi}), \quad \mathbf{x} \in \mathbb{R}^d$$

Classical approach: fix $f$ and solve for $\mathbf{x}$. The Neural ODE idea: **observe** $\mathbf{x}(t)$ and **learn** $f$ (Chen et al., 2018).

**Key caveat**: the choice of coordinates is critical.

## Latent ODEs

Instead of working in the original space, map to **latent coordinates** $\mathbf{z} = \mathcal{E}(\mathbf{x}) \in \mathbb{R}^\ell$ such that $f(\mathbf{z})$ is simple to learn $\Rightarrow$ **Latent ODE**.

Why? The ODE formulation provides an **inductive bias for continuity** — mass is conserved, the system has memory, and erratic discontinuities are ruled out. This follows from integrating $f$, which by construction promotes smooth trajectories.

> *Note (Maxime): this continuity guarantee holds because the integral of any locally integrable function is absolutely continuous. This is weaker than requiring $f$ to be Riemann-integrable — Lebesgue integrability suffices. In practice, the MLP parameterising $f$ is Lipschitz-continuous (bounded weights + smooth activations), so existence and uniqueness of the ODE solution is guaranteed by Picard–Lindelöf, and the resulting trajectories are $C^1$.*

## Training Challenges

The architecture consists of **three networks**:
1. **Encoder** — maps the observed time series to a latent initial state
2. **MLP** $f(\mathbf{z}, t)$ — the learned dynamics in latent space
3. **Decoder** — maps latent trajectories back to observation space

**Problem**: even on simple benchmarks, this architecture is difficult to train. The encoder sees the full time series and must learn not just the system **state** but also implicit **parameters** of the dynamics — two entangled objectives.

## Path-Minimised Latent Trajectories

Proposed solution: assume the latent space is **time-independent** and use a **conditional normalizing flow** to structure it.

**Loss function**: this is **not** a VAE. Instead:

$$\mathcal{L} = \mathcal{L}_{\text{reconstruction}} + \lambda \, \mathcal{S}_{\text{path length}}$$

where $\mathcal{S}$ is a **path length penalty** that regularises the latent trajectories. The emphasis is on structuring the latent space geometry, not on variational inference.

## Results

**Prediction quality**: validated on the **predator–prey** (Lotka–Volterra) system.

**Inference capabilities**: the model can determine the number of underlying parameters from data.

### Application: ECG Arrhythmia Detection

Goal: long-term cardiac monitoring. Train the Latent ODE on heartbeat data $\Rightarrow$ different arrhythmia types form **strongly separated clusters** in the latent space, enabling robust classification.

> Ref: Yan, Simpson & Melchior, [arXiv:2511.16933](https://arxiv.org/abs/2511.16933)

### LODE as a Learning Rate Scheduler

Surprising application: use the Latent ODE framework to **dynamically schedule the learning rate** during neural network training (LODE scheduler).

**Key observation**: the LODE-scheduled learning rate is an **order of magnitude higher** than what conventional convex optimisation theory prescribes. In standard gradient descent, the learning rate should not exceed the inverse curvature of the loss surface (**edge of stability** regime). Yet the LODE scheduler operates well beyond this bound.

**Why it works** (Ly & Gong, *Nature Communications*, 2025): loss landscapes contain both **rough** (narrow) and **smooth** (wide) basins. With a conventional small learning rate, the optimiser falls into narrow minima and gets stuck. The LODE scheduler's aggressive learning rate causes the optimiser to **skip narrow minima** and settle only in wide, flat basins $\Rightarrow$ better generalisation.

## Takeaway

Latent ODEs are effective **time-series summarisers** — they compress temporal dynamics into structured latent representations useful for both prediction and inference.

---

# Amir Al Ohmdi — Learning Dynamical Systems with Side Information

## Problem Setting

Goal: learn a dynamical system from data, but augmented with **side information** — qualitative knowledge about the system that does not come from observed trajectories.

Examples of side information:
- **Equilibrium points** and their stability
- **Invariance** of certain sets
- **Sign conditions** on derivatives of states
- **Decrease of energy functions** (Lyapunov-type conditions)
- **Monotonicity conditions**
- **Gradient or Hamiltonian structure**

The question: how can we impose these constraints on a learnable vector field in an efficient and computationally tractable way?

## Sum-of-Squares (SOS) Optimisation

The key tool: **SOS (sum-of-squares) optimisation** over polynomial vector fields.

Consider a polynomial with 7 coefficients and 3 unknowns. We want to find coefficients $c_1, c_2, c_3$ such that the polynomial is **non-negative** over some set — a basic **semialgebraic set**.

Core insight: if a polynomial can be rewritten as a **sum of squares**, then it is guaranteed non-negative.

**Key fact**: optimisation over sum-of-squares polynomials reduces to a **semidefinite program** (SDP), which can be solved efficiently.

**Theoretical foundation** — Putinar's Positivstellensatz (1993): a polynomial that is non-negative on a basic semialgebraic set $K$ can be certified as such via SOS polynomials (under mild conditions on $K$).

## Method

1. **Parametrise** a polynomial vector field $p : \mathbb{R}^n \to \mathbb{R}^n$
2. **Impose** side information as SOS constraints on $p$ (solved via SDP)
3. **Select** the $p$ that best explains the observed data

## Application: Epidemiology

Model from the epidemiology literature for the spread of gonorrhea in a heterosexual population.

Side information used: **directional monotonicity** — a higher proportion of infected females should increase the total number of infected individuals. Without this constraint, the learned model can violate basic epidemiological reasoning; with it, the dynamics remain physically plausible.

## Takeaway

Side information should be thought of as a **supplement to data** when learning dynamics, not a replacement. SOS/semidefinite optimisation is a powerful method for imposing such qualitative constraints on polynomial vector fields.

---

# Cyrill Bolsch — Physical Diffusion Models

Diffusion models for physics-informed generative modelling.
