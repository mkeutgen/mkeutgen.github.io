+++
title = "Neural ODEs for Inference and Optimisation"
kicker = "Seminar notes — Peter Melchior"
deck = "Latent ODEs as a structural prior for time-series — from supernova classification to scheduling the learning rate of gradient descent."
date = "2026-04-15"
tags = ["machine-learning", "neural-odes", "astronomy", "optimisation"]
author = "Maxime Keutgen De Greef"
toc = true
+++

## Motivation: time-domain astronomy

In time-domain astronomy, we observe sudden flux variations — e.g. a
supernova causing a brightness spike on a flux vs. MJD (time) plot. The
question: should we trigger follow-up observations with another telescope?

One can build time-series classifiers, but a supernova is a **physical
object** with inertia, conservation laws, etc. — even if the exact
governing equations are unknown. Can we exploit this structure?

## Neural ODEs

Standard governing equation:

$$
\partial_t \, \mathbf{x} = f(\mathbf{x}, t; \, \boldsymbol{\phi}), \quad \mathbf{x} \in \mathbb{R}^d
$$

Classical approach: fix $f$ and solve for $\mathbf{x}$. The Neural ODE
idea: **observe** $\mathbf{x}(t)$ and **learn** $f$ [^chen2018].
**Key caveat**: the choice of coordinates is critical.

## Latent ODEs

Instead of working in the original space, map to **latent coordinates**
$\mathbf{z} = \mathcal{E}(\mathbf{x}) \in \mathbb{R}^\ell$ such that
$f(\mathbf{z})$ is simple to learn $\Rightarrow$ **Latent ODE**.

Why? The ODE formulation provides an **inductive bias for continuity** —
mass is conserved, the system has memory, and erratic discontinuities are
ruled out. This follows from integrating $f$, which by construction
promotes smooth trajectories.

{{< sidenote >}}
This continuity guarantee holds because the integral of any locally
integrable function is absolutely continuous. This is weaker than requiring
$f$ to be Riemann-integrable — Lebesgue integrability suffices. In
practice the MLP parameterising $f$ is Lipschitz-continuous (bounded
weights + smooth activations), so existence and uniqueness of the ODE
solution is guaranteed by Picard–Lindelöf, and the resulting trajectories
are $C^1$.
{{< /sidenote >}}

## Training challenges

The architecture consists of **three networks**:

1. **Encoder** — maps the observed time series to a latent initial state
2. **MLP** $f(\mathbf{z}, t)$ — the learned dynamics in latent space
3. **Decoder** — maps latent trajectories back to observation space

**Problem**: even on simple benchmarks, this architecture is difficult to
train. The encoder sees the full time series and must learn not just the
system **state** but also implicit **parameters** of the dynamics — two
entangled objectives.

## Path-minimised latent trajectories

Proposed solution: assume the latent space is **time-independent** and use
a **conditional normalising flow** to structure it. **Loss function** —
this is *not* a VAE, but rather:

$$
\mathcal{L} = \mathcal{L}_{\text{reconstruction}} + \lambda \, \mathcal{S}_{\text{path length}}
$$

where $\mathcal{S}$ is a **path-length penalty** that regularises the
latent trajectories. The emphasis is on structuring the latent space
geometry, not on variational inference [^yan2025].

## Results

**Prediction quality** — validated on the **predator–prey**
(Lotka–Volterra) system. **Inference capabilities** — the model can
determine the number of underlying parameters from data.

### Application: ECG arrhythmia detection

Goal: long-term cardiac monitoring. Train the Latent ODE on heartbeat
data $\Rightarrow$ different arrhythmia types form **strongly separated
clusters** in the latent space, enabling robust classification.

### LODE as a learning-rate scheduler

Surprising application: use the Latent ODE framework to **dynamically
schedule the learning rate** during neural network training (LODE
scheduler).

**Key observation**: the LODE-scheduled learning rate is an **order of
magnitude higher** than what conventional convex optimisation theory
prescribes. In standard gradient descent, the learning rate should not
exceed the inverse curvature of the loss surface (**edge-of-stability**
regime). Yet the LODE scheduler operates well beyond this bound.

**Why it works** [^ly2025]: loss landscapes contain both **rough**
(narrow) and **smooth** (wide) basins. With a conventional small learning
rate, the optimiser falls into narrow minima and gets stuck. The LODE
scheduler's aggressive learning rate causes the optimiser to **skip narrow
minima** and settle only in wide, flat basins $\Rightarrow$ better
generalisation.

## Takeaway

Latent ODEs are effective **time-series summarisers** — they compress
temporal dynamics into structured latent representations useful for both
prediction and inference.

## References

[^chen2018]: Chen, R. T. Q., Rubanova, Y., Bettencourt, J., & Duvenaud, D.
    (2018). *Neural Ordinary Differential Equations*. NeurIPS.
    [arXiv:1806.07366](https://arxiv.org/abs/1806.07366)

[^yan2025]: Yan, Y., Simpson, G., & Melchior, P. (2025). *Path-minimised
    latent ODEs for time-series modelling*.
    [arXiv:2511.16933](https://arxiv.org/abs/2511.16933)

[^ly2025]: Ly, C., & Gong, B. (2025). *Latent-ODE learning-rate scheduling
    and the edge-of-stability regime*. Nature Communications. _(volume and
    DOI to be filled in.)_
