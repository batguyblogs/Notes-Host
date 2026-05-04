---
publish: true
title: Bernoulli's Equation
created: 2026-05-02
modified: 2026-05-04T06:19:18.331+05:30
tags:
  - FluidMechanics
  - PipeFlow
  - atomic
  - Bernoulli
  - energy
cssclasses: ""
---


# Bernoulli's Equation

**Bernoulli's equation states that for steady, incompressible, inviscid flow along a streamline, the sum of pressure head, velocity head, and elevation head is constant: P/ρg + V²/2g + z = constant.**

---

## Definition

Bernoulli's equation is the mechanical energy equation for an ideal fluid. It can be viewed
as an expression of **mechanical energy balance** — the total mechanical energy per unit
weight of fluid is conserved along a streamline.

For incompressible flow ($\rho$ = constant):

$$\boxed{\frac{P}{\rho g} + \frac{V^2}{2g} + z = \text{constant}}$$

Written between any two points on the same streamline:

$$\boxed{\frac{P_1}{\rho_1 g} + \frac{V_1^2}{2g} + z_1 = \frac{P_2}{\rho_2 g} + \frac{V_2^2}{2g} + z_2}$$

---

## The Three Heads

Each term has dimensions of length [m] and represents **energy per unit weight** of fluid:

| Term | Name | Physical meaning |
|---|---|---|
| $P/\rho g$ | **Pressure head** | Energy stored as fluid pressure |
| $V^2/2g$ | **Velocity head** (kinetic head) | Kinetic energy of the flowing fluid |
| $z$ | **Elevation head** (potential head) | Gravitational potential energy |

**Total head** = pressure head + velocity head + elevation head = constant along a streamline.

The sum $(P/\rho g + z)$ is called the **piezometric head**.

---

## Derivation Basis

Bernoulli's equation is derived from Newton's second law applied to a fluid element moving
along a streamline, or equivalently by integrating Euler's equation of motion along a
streamline. The derivation requires all four assumptions below.

### Energy Interpretation

Multiplying through by $\rho g$ gives energy per unit volume (Pa):

$$P + \frac{1}{2}\rho V^2 + \rho g z = \text{constant}$$

Or multiplying by $g$ gives energy per unit mass (J/kg):

$$\frac{P}{\rho} + \frac{V^2}{2} + gz = \text{constant}$$

---

## Assumptions

> [!warning] Four Critical Assumptions
> Bernoulli's equation is valid ONLY when ALL four conditions are satisfied:
> 1. **Ideal fluid** — viscosity is zero (inviscid, frictionless)
> 2. **Steady flow** — flow conditions do not change with time at any point
> 3. **Incompressible flow** — density is constant ($\rho$ = const)
> 4. **Along a streamline** — applied only between two points on the same streamline
>
> Violating any of these requires modification. Real fluids violate condition 1,
> requiring the modified form with head loss — see [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/17_BernoulliRealFluid]].

---

## Key Details

### Pressure-Velocity Trade-off

For horizontal flow ($z_1 = z_2$), Bernoulli becomes:

$$\frac{P_1}{\rho g} + \frac{V_1^2}{2g} = \frac{P_2}{\rho g} + \frac{V_2^2}{2g}$$

If the pipe narrows (by continuity, $V_2 > V_1$), then $P_2 < P_1$: **velocity increases
while pressure decreases**. This counter-intuitive result is the basis for the Venturi meter,
Pitot tube, and many other flow measurement devices.

### Bernoulli + Continuity Together

These two equations are almost always applied together in pipe flow problems:
- Continuity gives the relationship between velocities: $A_1V_1 = A_2V_2$
- Bernoulli gives the relationship between pressures and velocities

With two equations and (typically) two unknowns ($P_2$ and $V_2$), the system is solvable.

> [!example] Worked Concept Example
> Water flows horizontally through a pipe that narrows from d₁ = 0.2 m to d₂ = 0.1 m.
> At section 1, V₁ = 1 m/s, P₁ = 200 kPa.
>
> **Step 1 — Continuity**: $A_1V_1 = A_2V_2$
> $\pi(0.2)^2/4 \times 1 = \pi(0.1)^2/4 \times V_2$
> $V_2 = V_1 (d_1/d_2)^2 = 1 \times 4 = 4$ m/s
>
> **Step 2 — Bernoulli** (horizontal, $z_1 = z_2$, $\rho = 1000$ kg/m³):
> $P_2 = P_1 + \frac{1}{2}\rho(V_1^2 - V_2^2)$
> $P_2 = 200000 + \frac{1}{2}(1000)(1 - 16) = 200000 - 7500 = 192{,}500$ Pa
>
> Pressure drops from 200 kPa to 192.5 kPa as velocity increases fourfold.

---

## Limitations Leading to Real-Fluid Bernoulli

For real fluids:
- Viscosity causes friction → energy is dissipated as heat
- This means the total head *decreases* in the direction of flow
- A head loss term $h_L$ must be added → see [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/17_BernoulliRealFluid]]

The statement of Bernoulli's equation in words:

> *"The sum of the kinetic, potential, and flow energies of a fluid particle is constant along a streamline during steady flow when compressibility and frictional effects are negligible."*

---

## Why It Matters

Bernoulli's equation is the foundation for:
- **Venturi meters and orifice plates** — flow rate measurement using pressure difference
- **Pitot tubes** — velocity measurement
- **Pump and turbine analysis** — energy added or removed from the flow
- **Pipe system design** — every pressure drop calculation uses the modified form
- **HGL and TEL** — graphical representation of the three Bernoulli heads → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/23_HGL_TEL]]

---

## Connections to Other Notes

- Continuity equation (provides velocities for Bernoulli): [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/15_ContinuityEquation]]
- Real fluid Bernoulli (adds head loss term): [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/17_BernoulliRealFluid]]
- Graphical representation of Bernoulli heads: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/23_HGL_TEL]]
- The head loss $h_L$ quantified by Darcy-Weisbach: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/20_MajorLosses_DarcyWeisbach]]

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01c_PipeFlow_Hub]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/02c_PipeFlow_MOC]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/15_ContinuityEquation]]
*Links to:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/15_ContinuityEquation]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/17_BernoulliRealFluid]],
[[Other Notes/EHT/Testing_something_out/Fluid Mechanics/20_MajorLosses_DarcyWeisbach]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/23_HGL_TEL]]
