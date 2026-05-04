---
publish: true
title: Subcategories of Fluid Mechanics
created: 2026-05-02
modified: 2026-05-04T06:18:35.154+05:30
tags:
  - FluidMechanics
  - FluidFundamentals
  - atomic
  - taxonomy
cssclasses: ""
---


# Subcategories of Fluid Mechanics

**Fluid mechanics is divided into sub-disciplines based on fluid compressibility, flow geometry, and application domain — principally: hydrodynamics, hydraulics, gas dynamics, and aerodynamics.**

---

## Definition

Fluid mechanics is the parent science dealing with fluid behaviour both at rest and in motion.
It is itself divided into two broad branches:

- **Fluid statics**: the study of fluids at rest
- **Fluid dynamics** (fluid kinematics + fluid kinetics): the study of fluids in motion,
  considering both the geometry of motion and the forces causing it

Within fluid dynamics, four major sub-disciplines are defined by the nature of the fluid and
the flow context.

---

## The Four Sub-Disciplines

### 1. Hydrodynamics

The study of the motion of fluids that are **practically incompressible**, such as liquids
(especially water). Hydrodynamics provides the theoretical foundation for flow equations
assuming constant density.

- **Key assumption**: $\rho = \text{constant}$
- **Typical applications**: rivers, ocean currents, pump design, pipe networks
- **Governing equations**: incompressible Navier-Stokes, Bernoulli, continuity $A_1V_1 = A_2V_2$

### 2. Hydraulics

A **sub-category of hydrodynamics** focused specifically on engineering applications
involving liquid flows in **pipes and open channels**.

- **Scope**: pipe flow, channel flow, weirs, orifices, pumps, turbines
- **Character**: applied and empirical — relies heavily on experimental coefficients
- **Relation to this course**: MTE 3252 is essentially a hydraulics course

> [!note]
> Hydraulics is to hydrodynamics what electrical engineering is to physics —
> the applied engineering manifestation of the underlying science.

### 3. Gas Dynamics

Deals with the flow of fluids that undergo **significant density changes**, typically gases
flowing at high speeds through nozzles, turbines, or around projectiles.

- **Key condition**: compressibility cannot be ignored (Mach number > ~0.3)
- **Density**: $\rho \neq \text{constant}$ — must use full compressible continuity equation
  $\rho_1 A_1 V_1 = \rho_2 A_2 V_2$
- **Phenomena**: shock waves, choked flow, supersonic expansion
- **Typical applications**: jet engines, rocket nozzles, high-speed wind tunnels

### 4. Aerodynamics

Deals with the flow of **gases (especially air) over external bodies** such as aircraft,
rockets, and automobiles at high or low speeds.

- **Focus**: external flow, lift, drag, boundary layers on surfaces
- **Overlaps with**: gas dynamics (at high speed), hydrodynamics (at low speed)
- **Key tools**: potential flow theory, boundary layer theory (see [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/26_BoundaryLayer]]),
  wind tunnel experiments

---

## Comparison Table

| Sub-discipline | Fluid | Density | Flow context | Primary concern |
|---|---|---|---|---|
| Hydrodynamics | Liquid | Constant | General | Theory of incompressible flow |
| Hydraulics | Liquid | Constant | Pipes & channels | Engineering applications |
| Gas Dynamics | Gas | Variable | High-speed internal | Compressibility, shocks |
| Aerodynamics | Gas (air) | Variable/constant | External bodies | Lift, drag, boundary layers |

---

## When Does Compressibility Matter?

The Mach number $Ma = V/c$ (where $c$ is the speed of sound) is the criterion:

$$Ma < 0.3 \implies \text{treat as incompressible (< 5\% density change)}$$
$$Ma > 0.3 \implies \text{compressibility effects become significant}$$

For water flows in pipes (the focus of this course), the speed of sound is approximately
1480 m/s — pipe velocities are tiny by comparison, so the incompressible assumption is
always valid.

> [!tip]
> In this course, unless explicitly stated otherwise, **assume incompressible flow**.
> This means $\rho = \text{constant}$, which simplifies the continuity equation to
> $A_1 V_1 = A_2 V_2$ and is required for Bernoulli's equation to hold in its standard form.

---

## Why It Matters

Understanding which sub-discipline applies determines which equations are valid:

- If incompressible: use $A_1V_1 = A_2V_2$ and Bernoulli in standard form → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/16_BernoullisEquation]]
- If compressible: must use $\rho_1 A_1 V_1 = \rho_2 A_2 V_2$ → see [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/15_ContinuityEquation]]
- External flow over bodies: boundary layer analysis becomes essential → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/26_BoundaryLayer]]

---

## Connections to Other Notes

- The incompressibility assumption discussed here simplifies the continuity equation: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/15_ContinuityEquation]]
- Boundary layer theory belongs to the aerodynamics sub-discipline: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/26_BoundaryLayer]]
- The hydraulics sub-discipline is the context for all pipe flow calculations: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01c_PipeFlow_Hub]]

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01a_FluidFundamentals_Hub]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/02a_FluidFundamentals_MOC]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/03_WhatIsFluid]]
*Links to:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/15_ContinuityEquation]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/16_BernoullisEquation]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/26_BoundaryLayer]],
[[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01c_PipeFlow_Hub]]
