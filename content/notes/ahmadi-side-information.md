+++
title = "Learning Dynamical Systems with Side Information"
kicker = "Seminar notes — Amir Ali Ahmadi"
deck = "Sum-of-squares optimisation as a tractable way to enforce qualitative knowledge — equilibria, monotonicity, energy decrease — on a learnt polynomial vector field."
date = "2026-04-15"
tags = ["machine-learning", "dynamical-systems", "optimisation", "control"]
author = "Maxime Keutgen"
toc = true
+++

## Problem setting

Goal: learn a dynamical system from data, but augmented with **side
information** — qualitative knowledge about the system that does not come
from observed trajectories.

Examples of side information:

- **Equilibrium points** and their stability
- **Invariance** of certain sets
- **Sign conditions** on derivatives of states
- **Decrease of energy functions** (Lyapunov-type conditions)
- **Monotonicity conditions**
- **Gradient or Hamiltonian structure**

The question: how can we impose these constraints on a learnable vector
field in an efficient and computationally tractable way?

## Sum-of-squares (SOS) optimisation

The key tool: **SOS (sum-of-squares) optimisation** over polynomial vector
fields. Consider a polynomial with 7 coefficients and 3 unknowns. We want
to find coefficients $c_1, c_2, c_3$ such that the polynomial is
**non-negative** over some set — a basic **semialgebraic set**.

Core insight: if a polynomial can be rewritten as a **sum of squares**,
then it is guaranteed non-negative.

**Key fact**: optimisation over sum-of-squares polynomials reduces to a
**semidefinite program** (SDP), which can be solved efficiently.

{{< sidenote >}}
**Theoretical foundation** — Putinar's *Positivstellensatz* [^putinar1993]:
a polynomial that is non-negative on a basic semialgebraic set $K$ can be
certified as such via SOS polynomials, under mild compactness conditions
on $K$ (the Archimedean condition).
{{< /sidenote >}}

## Method

1. **Parametrise** a polynomial vector field $p : \mathbb{R}^n \to \mathbb{R}^n$
2. **Impose** side information as SOS constraints on $p$ (solved via SDP)
3. **Select** the $p$ that best explains the observed data

## Application: epidemiology

Model from the epidemiology literature for the spread of gonorrhea in a
heterosexual population [^lajmanovich1976].

Side information used: **directional monotonicity** — a higher proportion
of infected females should increase the total number of infected
individuals. Without this constraint, the learned model can violate basic
epidemiological reasoning; with it, the dynamics remain physically
plausible.

## Takeaway

Side information should be thought of as a **supplement to data** when
learning dynamics, not a replacement. SOS / semidefinite optimisation is a
powerful method for imposing such qualitative constraints on polynomial
vector fields.

## References

[^putinar1993]: Putinar, M. (1993). *Positive polynomials on compact
    semi-algebraic sets*. Indiana University Mathematics Journal,
    42(3), 969–984.

[^lajmanovich1976]: Lajmanovich, A., & Yorke, J. A. (1976). *A
    deterministic model for gonorrhea in a nonhomogeneous population*.
    Mathematical Biosciences, 28(3–4), 221–236. _(reference cited at the
    talk; exact edition to verify.)_
