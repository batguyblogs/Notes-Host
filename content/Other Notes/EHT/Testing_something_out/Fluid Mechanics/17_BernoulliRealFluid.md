---
publish: true
title: Bernoulli's Equation for Real Fluids
created: 2026-05-02
modified: 2026-05-04T06:19:21.811+05:30
tags:
  - FluidMechanics
  - PipeFlow
  - atomic
  - Bernoulli
  - head-loss
cssclasses: ""
---


# Bernoulli's Equation for Real Fluids

**For real (viscous) fluids, Bernoulli's equation must include a head loss term hL representing viscous dissipation: P₁/ρ₁g + V₁²/2g + z₁ = P₂/ρ₂g + V₂²/2g + z₂ + hL.**

---

## Definition

The ideal Bernoulli equation assumes an **inviscid** (frictionless) fluid. Every real fluid
has viscosity, meaning it dissipates mechanical energy into heat as it flows. This energy
cannot be recovered — the total head *decreases* in the direction of flow.

The **modified Bernoulli equation** for real fluids:

$$\boxed{\frac{P_1}{\rho_1 g} + \frac{V_1^2}{2g} + z_1 = \frac{P_2}{\rho_2 g} + \frac{V_2^2}{2g} + z_2 + h_L}$$

where $h_L$ is the **total head loss** between points 1 and 2, measured in metres of fluid.

---

## Physical Meaning

### Why Real Fluids Always Lose Energy

All real fluids are viscous and hence offer resistance to flow. This resistance converts
mechanical energy (pressure energy + kinetic energy) into **thermal energy (heat)** through
viscous friction. This process is irreversible — the heat cannot spontaneously convert
back into mechanical energy.

The result: the total head at point 2 is always **less** than at point 1 (in the direction
of flow, in the absence of pumps):

$$\text{Total head at 1} = \text{Total head at 2} + h_L$$

$$\left(\frac{P_1}{\rho g} + \frac{V_1^2}{2g} + z_1\right) > \left(\frac{P_2}{\rho g} + \frac{V_2^2}{2g} + z_2\right)$$

The difference is $h_L > 0$ always (for flow between the two points with no pump).

---

## Components of Head Loss

The total head loss $h_L$ has two contributions:

$$h_L = h_f (\text{major losses}) + \sum h_m (\text{minor losses})$$

### Major Losses $h_f$

Due to **wall friction** over the pipe length. Calculated using Darcy-Weisbach:

$$h_f = \frac{4fLV^2}{d \times 2g}$$

See [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/20_MajorLosses_DarcyWeisbach]] for full derivation.

### Minor Losses $h_m$

Due to **local geometric disturbances**: pipe entrances, exits, bends, sudden enlargements,
sudden contractions, valves, fittings. Each expressed as:

$$h_m = k \frac{V^2}{2g}$$

See [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/21_MinorLosses]] for all seven types and their loss coefficients.

> [!note] "Minor" is Relative
> Minor losses are called "minor" because in long pipes they are small compared to major
> friction losses. In short pipes with many fittings, they can dominate. Always evaluate
> both and compare magnitudes before deciding to neglect either.

---

## Application Strategy

When applying the modified Bernoulli equation:

1. **Identify points 1 and 2** — typically at free surfaces (where P = $P_{atm}$ and V ≈ 0) or at known cross-sections
2. **Set the datum** — choose a convenient reference elevation (z = 0), typically at the lower point
3. **List all losses** — identify which major and minor losses occur between the two points
4. **Apply the equation** — substitute and solve for the unknown

> [!example] Worked Concept Example
> Water flows from a large reservoir (surface at height H = 10 m above pipe outlet)
> through a pipe of length L = 50 m, diameter d = 0.1 m, f = 0.005.
> Find the exit velocity (neglecting minor losses).
>
> **Point 1**: reservoir surface — $P_1 = P_{atm}$, $V_1 \approx 0$, $z_1 = H = 10$ m
> **Point 2**: pipe exit — $P_2 = P_{atm}$, $V_2 = V$ (unknown), $z_2 = 0$
>
> Bernoulli with major loss only:
> $0 + 0 + 10 = 0 + V^2/2g + 0 + 4fLV^2/(d \cdot 2g)$
> $10 = \frac{V^2}{2g}\left(1 + \frac{4fL}{d}\right) = \frac{V^2}{2 \times 9.81}\left(1 + \frac{4 \times 0.005 \times 50}{0.1}\right)$
> $10 = \frac{V^2}{19.62}(1 + 10) = \frac{11 V^2}{19.62}$
> $V^2 = \frac{10 \times 19.62}{11} = 17.84$, so $V = 4.22$ m/s

---

## With Pumps or Turbines

If a **pump** is present between points 1 and 2, it adds energy to the flow:

$$\frac{P_1}{\rho g} + \frac{V_1^2}{2g} + z_1 + h_p = \frac{P_2}{\rho g} + \frac{V_2^2}{2g} + z_2 + h_L$$

where $h_p$ = pump head (m). If a **turbine** extracts energy, replace $+h_p$ with $-h_t$.

> [!caution] Low Confidence
> The pump/turbine form of Bernoulli is well-established general knowledge but is not
> explicitly covered in the source material. The above is correct but verify against
> your course notes if this appears in assessments.

---

## Why It Matters

The modified Bernoulli equation is the workhorse of pipe system design:

- Every pipe flow calculation ultimately applies this equation
- The head loss $h_L$ is what the pump must overcome → determines pump power: $P = \rho g Q h_L$
- It connects Bernoulli's ideal framework to the reality of viscous losses
- It underpins the analysis of pipes in series [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/24_PipesInSeries]] and parallel [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/25_PipesInParallel]]

---

## Connections to Other Notes

- Ideal Bernoulli (the starting point): [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/16_BernoullisEquation]]
- Major head loss — Darcy-Weisbach: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/20_MajorLosses_DarcyWeisbach]]
- Minor head losses: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/21_MinorLosses]]
- Graphical view — TEL shows total head decreasing: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/23_HGL_TEL]]

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01c_PipeFlow_Hub]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/02c_PipeFlow_MOC]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/16_BernoullisEquation]]
*Links to:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/16_BernoullisEquation]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/20_MajorLosses_DarcyWeisbach]],
[[Other Notes/EHT/Testing_something_out/Fluid Mechanics/21_MinorLosses]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/23_HGL_TEL]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/24_PipesInSeries]]
