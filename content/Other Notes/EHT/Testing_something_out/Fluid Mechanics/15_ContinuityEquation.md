---
publish: true
title: Continuity Equation
created: 2026-05-02
modified: 2026-05-04T06:19:13.766+05:30
tags:
  - FluidMechanics
  - PipeFlow
  - atomic
  - conservation-mass
cssclasses: ""
---


# Continuity Equation

**The continuity equation expresses conservation of mass for fluid flow: ρ₁A₁V₁ = ρ₂A₂V₂; for incompressible flow this simplifies to A₁V₁ = A₂V₂, meaning the volumetric flow rate Q is constant throughout the pipe.**

---

## Definition

The continuity equation is based on the **principle of conservation of mass**: for steady
flow through a pipe, mass can neither be created nor destroyed. Whatever mass enters a
control volume per unit time must leave it.

For a fluid flowing through a pipe, for all cross-sections, the quantity of fluid per
second is constant.

---

## Derivation

Consider two cross-sections 1-1 and 2-2 of a pipe:

```
        section 1-1           section 2-2
             │                     │
   ──────────┼─────────────────────┼──────────
   ρ₁,A₁,V₁ │  →  flow direction  │ ρ₂,A₂,V₂
   ──────────┼─────────────────────┼──────────
             │                     │
```

Let:
- $V_1$, $\rho_1$, $A_1$ = velocity, density, area at section 1-1
- $V_2$, $\rho_2$, $A_2$ = velocity, density, area at section 2-2

**Mass flow rate at section 1-1**:

$$\dot{m}_1 = \rho_1 A_1 V_1 \quad [\text{kg/s}]$$

**Mass flow rate at section 2-2**:

$$\dot{m}_2 = \rho_2 A_2 V_2 \quad [\text{kg/s}]$$

By conservation of mass: $\dot{m}_1 = \dot{m}_2$

$$\boxed{\rho_1 A_1 V_1 = \rho_2 A_2 V_2}$$

This is the **general continuity equation** — valid for both compressible and
incompressible fluids.

---

## Incompressible Form

For an **incompressible fluid** (liquid, or gas at low Mach number):

$$\rho_1 = \rho_2 = \rho = \text{constant}$$

The density cancels:

$$\boxed{A_1 V_1 = A_2 V_2}$$

Defining the **volumetric flow rate** (discharge) $Q$ (m³/s):

$$Q = A \cdot V$$

The incompressible continuity equation becomes:

$$Q_1 = Q_2 \quad \text{i.e.,} \quad A_1 V_1 = A_2 V_2$$

> [!note] Physical Interpretation
> For an incompressible fluid, if the pipe narrows (A₂ < A₁), the velocity must
> increase (V₂ > V₁) to pass the same volumetric flow rate through the smaller
> cross-section. This is why water speeds up as it passes through a nozzle or
> constriction.

---

## Key Details

### Mass Flow Rate vs Volumetric Flow Rate

| Quantity | Symbol | Formula | Unit |
|---|---|---|---|
| Volumetric flow rate (discharge) | Q | $A \times V$ | m³/s or litres/s |
| Mass flow rate | $\dot{m}$ | $\rho \times A \times V = \rho Q$ | kg/s |

Conversion: $\dot{m} = \rho Q$

### Velocity from Flow Rate

Given $Q$ and pipe diameter $d$:

$$V = \frac{Q}{A} = \frac{Q}{\pi d^2 / 4} = \frac{4Q}{\pi d^2}$$

This is the mean cross-sectional velocity — the average velocity used in all pipe flow
calculations.

> [!example] Worked Example
> A pipe of diameter 100 mm carries crude oil (ρ = 900 kg/m³). 100 kg of oil is
> collected in 30 seconds.
>
> Mass flow rate: $\dot{m} = 100/30 = 3.333$ kg/s
>
> Volumetric flow rate: $Q = \dot{m}/\rho = 3.333/900 = 3.704 \times 10^{-3}$ m³/s
>
> Cross-sectional area: $A = \pi(0.1)^2/4 = 7.854 \times 10^{-3}$ m²
>
> Mean velocity: $\bar{u} = Q/A = 3.704 \times 10^{-3} / 7.854 \times 10^{-3} = 0.472$ m/s

### Pipes in Series — Continuity

For pipes in series (see [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/24_PipesInSeries]]):

$$Q = A_1 V_1 = A_2 V_2 = A_3 V_3$$

All pipes carry the same volumetric flow rate. Knowing Q and each diameter, all
velocities can be found.

### Units of Q

| Unit | Equivalent |
|---|---|
| m³/s | SI standard |
| litres/s (l/s or lps) | 1 l/s = 10⁻³ m³/s |
| m³/hr | 1 m³/hr = 1/3600 m³/s |

> [!warning] Unit Conversion — Litres
> Problems often give Q in litres per second. Always convert:
> $Q [\text{m}^3/\text{s}] = Q [\text{l/s}] \times 10^{-3}$
> Forgetting this conversion is among the most common errors in numerical problems.

---

## Why It Matters

The continuity equation is the foundation of all pipe flow analysis:

1. It links velocities at different pipe sections → required for Bernoulli's equation
2. It provides the velocity $V$ needed for the Reynolds number → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/14_ReynoldsNumber]]
3. For series pipes: continuity gives all velocities from one flow rate
4. For parallel pipes: continuity splits the total flow → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/25_PipesInParallel]]
5. It appears in the derivation of every pipe network problem

---

## Connections to Other Notes

- Bernoulli's equation — uses velocities from continuity: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/16_BernoullisEquation]]
- Reynolds number calculation using V from continuity: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/14_ReynoldsNumber]]
- Pipes in series — same Q throughout: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/24_PipesInSeries]]
- Pipes in parallel — Q splits: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/25_PipesInParallel]]

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01c_PipeFlow_Hub]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/02c_PipeFlow_MOC]]
*Links to:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/14_ReynoldsNumber]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/16_BernoullisEquation]],
[[Other Notes/EHT/Testing_something_out/Fluid Mechanics/24_PipesInSeries]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/25_PipesInParallel]]
