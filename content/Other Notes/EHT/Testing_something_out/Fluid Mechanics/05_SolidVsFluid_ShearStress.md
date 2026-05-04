---
publish: true
title: Solid vs Fluid — Shear Stress and Deformation
created: 2026-05-02
modified: 2026-05-04T06:18:38.587+05:30
tags:
  - FluidMechanics
  - FluidFundamentals
  - atomic
  - shear-stress
cssclasses: ""
---


# Solid vs Fluid — Shear Stress and Deformation

**The fundamental mechanical distinction between a solid and a fluid is that a solid reaches a fixed shear strain under constant applied stress, while a fluid deforms continuously at a rate proportional to the applied stress — it never reaches an equilibrium strain.**

---

## Definition

Shear stress $\tau$ is a tangential force per unit area applied to a surface:

$$\tau = \frac{F}{A}$$

where $F$ is the tangential (shear) force and $A$ is the contact area over which it acts.
SI unit: N/m² = Pa.

The response of a material to this stress is what defines it as a solid or a fluid.

---

## Mechanism — The Plate Analogy

### Solid (Rubber Block) Case

Consider a rectangular rubber block sandwiched between two rigid plates:

```
  Force F →
 ┌──────────────────────────────┐  ← upper plate (moves)
 │░░░░░░░░░ rubber ░░░░░░░░░░░│  deforms by angle α
 └──────────────────────────────┘  ← lower plate (fixed)
          |← shear strain α →|
```

When force $F$ is applied to the upper plate:
- The rubber block deforms to angle $\alpha$ (shear strain)
- **Shear stress** at the interface: $\tau = F/A$
- **Shear strain** increases in proportion to $F$: $\tau \propto \alpha$
- When $F$ is removed, the rubber **springs back** to its original position

This is Hooke's Law for shear: $\tau = G \alpha$, where $G$ is the shear modulus.

**The key point**: the deformation angle $\alpha$ reaches a fixed value and holds there.
Stress is proportional to *strain*.

### Fluid Case

Now replace the rubber block with a fluid (e.g., water between two large parallel plates):

```
  Force F →                velocity = V (plate speed)
 ┌──────────────────────────────┐  ← upper plate (moves at V)
   u(y) increases linearly ↑
   velocity gradient du/dy
   u(0) = 0 at lower plate ↓
 └──────────────────────────────┘  ← lower plate (fixed, u = 0)
```

When force $F$ is applied:
- The fluid layer touching the upper plate moves at velocity $V$ (no-slip condition)
- The fluid layer touching the lower plate remains at rest ($u = 0$)
- Intermediate layers move at intermediate velocities — a **velocity gradient** develops
- The fluid **never stops deforming** — it keeps flowing as long as $F$ is applied
- When $F$ is removed, the fluid **does not return** — it stays in its deformed state

The velocity gradient $du/dy$ is the *rate* of shear strain. Stress is proportional to
*strain rate*, not strain.

---

## Key Details

### The Governing Relations

For a solid (elastic, within elastic range):

$$\tau = G \cdot \alpha$$

where $G$ = shear modulus (Pa), $\alpha$ = shear strain (dimensionless angle, radians)

For a Newtonian fluid (Newton's law of viscosity):

$$\tau = \mu \cdot \frac{du}{dy}$$

where $\mu$ = dynamic viscosity (Pa·s), $du/dy$ = velocity gradient (s⁻¹)

The velocity gradient $du/dy$ is also called the **rate of shear strain** or
**rate of shear deformation**. It has units of s⁻¹ (1/seconds).

### Force-Area Relationship

The shear force $F$ and shear stress $\tau$ are related by:

$$F = \tau \cdot A$$

where $A$ is the contact area between the fluid and the moving surface.

### Velocity Profile Between Plates

For steady laminar flow between parallel plates (Couette flow), the velocity varies linearly
with distance $y$ from the lower plate:

$$u(y) = V \cdot \frac{y}{h}$$

where $h$ is the gap between the plates and $V$ is the upper plate velocity. The velocity
gradient is therefore uniform:

$$\frac{du}{dy} = \frac{V}{h} = \text{constant}$$

The fluid velocity decreases with depth because of friction between adjacent fluid layers,
reaching zero at the stationary lower plate.

> [!warning] Exam Trap
> Students sometimes say "stress is proportional to strain" for fluids. This is wrong.
> **For fluids: stress is proportional to strain RATE** ($du/dy$). The strain itself grows
> without bound over time. Only the *rate* of strain is proportional to stress.

> [!example] Numerical Example
> Two large parallel plates are 10 mm apart. The upper plate moves at 0.5 m/s; the lower
> is fixed. The fluid between them has dynamic viscosity μ = 0.001 Pa·s (water at 20°C).
>
> Velocity gradient: $du/dy = V/h = 0.5/0.01 = 50 \text{ s}^{-1}$
>
> Shear stress: $\tau = \mu \cdot du/dy = 0.001 \times 50 = 0.05 \text{ Pa}$
>
> This is the shear stress acting on both plates and on every fluid layer between them.

---

## Summary Comparison

| Feature | Solid (elastic) | Fluid (Newtonian) |
|---|---|---|
| Response to shear | Fixed strain $\alpha$ | Continuous deformation |
| Constitutive law | $\tau = G\alpha$ | $\tau = \mu \, du/dy$ |
| Stress ∝ | Strain | Strain **rate** |
| Load removal | Returns to original shape | Remains deformed |
| Shear at rest | Can sustain | Cannot sustain |

---

## Why It Matters

This distinction is not just definitional — it has direct engineering consequences:

- It explains why fluids flow freely through pipes while solids must be machined
- It is the physical basis for Newton's law of viscosity → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/08_DynamicViscosity_NewtonsLaw]]
- The no-slip condition (u = 0 at wall) follows from continuous deformation — see [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/18_LaminarFlow_HagenPoiseuille]]
- The velocity gradient $du/dy$ is the quantity that appears in every viscosity calculation

---

## Connections to Other Notes

- The formal definition of fluid that this note makes concrete: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/03_WhatIsFluid]]
- Newton's law of viscosity — the quantitative extension: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/08_DynamicViscosity_NewtonsLaw]]
- The no-slip boundary condition in pipe flow derivation: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/18_LaminarFlow_HagenPoiseuille]]

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01a_FluidFundamentals_Hub]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/02a_FluidFundamentals_MOC]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/03_WhatIsFluid]]
*Links to:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/08_DynamicViscosity_NewtonsLaw]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/18_LaminarFlow_HagenPoiseuille]],
[[Other Notes/EHT/Testing_something_out/Fluid Mechanics/12_FluidTypes_Newtonian]]
