---
publish: true
title: Dynamic Viscosity and Newton's Law of Viscosity
created: 2026-05-02
modified: 2026-05-04T06:18:49.096+05:30
tags:
  - FluidMechanics
  - FluidProperties
  - atomic
  - viscosity
cssclasses: ""
---


# Dynamic Viscosity and Newton's Law of Viscosity

**Dynamic viscosity (μ) is the fluid property that quantifies resistance to shear deformation; Newton's law of viscosity states that shear stress is proportional to the velocity gradient: $\tau = \mu \, du/dy$.**

---

## Definition

**Viscosity** is defined as the property of a fluid that offers resistance to the movement
of one layer of fluid over another adjacent layer. It is the fluid's internal frictional
resistance to flow.

**Dynamic viscosity** (also called *absolute viscosity* or simply *viscosity*) is the
constant of proportionality between shear stress and velocity gradient for a Newtonian fluid:

$$\tau = \mu \frac{du}{dy}$$

Rearranging:

$$\mu = \frac{\tau}{du/dy} = \frac{\text{shear stress}}{\text{velocity gradient}}$$

Viscosity is also interpretable as: *the shear stress required to produce unit rate of shear strain.*

Symbol: $\mu$ (Greek letter mu)

---

## Mechanism — Newton's Law of Viscosity

Consider two fluid layers separated by a distance $dy$, moving at velocities $u$ and
$u + du$ respectively:

```
        Upper layer →    velocity = u + du
    ─────────────────────────────────────────
                dy ↕          τ (shear stress)
    ─────────────────────────────────────────
        Lower layer →    velocity = u

                         Solid boundary (u = 0)
    ═════════════════════════════════════════
```

The velocity gradient (rate of shear strain) is:

$$\frac{du}{dy} \quad [\text{units: s}^{-1}]$$

Newton's Law of Viscosity states:

$$\boxed{\tau = \mu \frac{du}{dy}}$$

where:
- $\tau$ = shear stress (Pa = N/m²)
- $\mu$ = dynamic viscosity (Pa·s)
- $du/dy$ = velocity gradient / rate of shear strain (s⁻¹)

> [!note] Physical Interpretation
> $du/dy$ is the *rate* at which adjacent fluid layers slide past each other. A large
> velocity gradient means layers are moving very differently — requiring more shear stress
> to maintain the motion. A viscous fluid (high μ) requires more stress for the same
> velocity gradient. A low-viscosity fluid (small μ) flows with little resistance.

---

## Key Details

### The Velocity Gradient $du/dy$

The term $du/dy$ represents three equivalent things:
1. **Rate of shear strain** — how fast the fluid is being sheared
2. **Rate of shear deformation** — how fast the angle of deformation is changing
3. **Velocity gradient** — how rapidly velocity changes across the flow section

These three descriptions all refer to the same quantity.

### Viscosity as Shear Stress per Unit Strain Rate

From the definition:

$$\mu = \frac{\tau}{du/dy}$$

This means viscosity has dimensions of:

$$[\mu] = \frac{[\tau]}{[du/dy]} = \frac{\text{N/m}^2}{\text{m/s / m}} = \frac{\text{N/m}^2}{\text{s}^{-1}} = \text{N·s/m}^2 = \text{Pa·s}$$

### Graphical Interpretation

For a Newtonian fluid, a plot of $\tau$ (y-axis) vs $du/dy$ (x-axis) gives a **straight line
through the origin**. The slope of this line is the dynamic viscosity $\mu$. This linearity
is what defines a Newtonian fluid — see [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/12_FluidTypes_Newtonian]] for non-linear (non-Newtonian)
behaviour.

> [!example] Worked Example
> Two large parallel plates are 4 mm apart. The upper plate moves at 1.2 m/s; the lower
> is stationary. The fluid between them has μ = 0.048 Pa·s.
>
> **Velocity gradient**: $du/dy = 1.2/0.004 = 300 \text{ s}^{-1}$
>
> **Shear stress**: $\tau = \mu \cdot du/dy = 0.048 \times 300 = 14.4 \text{ Pa}$
>
> **Shear force** on the upper plate (area A = 0.5 m²):
> $F = \tau \cdot A = 14.4 \times 0.5 = 7.2 \text{ N}$

---

## Physical Cause of Viscosity

Viscosity arises from two distinct microscopic mechanisms depending on the fluid type:

| Fluid type | Physical mechanism |
|---|---|
| **Liquids** | Cohesive intermolecular forces between molecules. Molecules must overcome these forces to slide past each other. |
| **Gases** | Momentum exchange by molecular collisions between faster and slower layers. Molecules migrate between layers, transferring momentum. |

This distinction explains why viscosity behaves oppositely with temperature:

- **Liquids**: Higher temperature → molecules have more kinetic energy → can overcome
  cohesive forces more easily → **viscosity decreases** with temperature
- **Gases**: Higher temperature → more frequent and energetic molecular collisions →
  more momentum transfer between layers → **viscosity increases** with temperature

See [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/11_Viscosity_TemperaturePressure]] for a detailed treatment.

> [!warning] Common Misconception
> "Thick" (high-viscosity) fluids are not necessarily dense. Honey has high viscosity
> but its density is only ~1400 kg/m³ — comparable to many thin liquids. Viscosity and
> density are independent properties. The kinematic viscosity $\nu = \mu/\rho$ combines
> them — see [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/10_KinematicViscosity]].

---

## Why It Matters

Dynamic viscosity is the central material property of fluid mechanics:

- It appears directly in the shear stress formula for all laminar flow problems
- It is the key parameter in the **Hagen-Poiseuille equation**: $\Delta p = 32\mu\bar{u}L/D^2$ → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/18_LaminarFlow_HagenPoiseuille]]
- It determines the **Reynolds number** (with density): $Re = \rho V d / \mu$ → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/14_ReynoldsNumber]]
- The ratio $\mu/\rho$ defines the **kinematic viscosity** → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/10_KinematicViscosity]]
- It is the property that makes real fluids dissipate energy, requiring the modified Bernoulli equation → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/17_BernoulliRealFluid]]

---

## Connections to Other Notes

- Physical basis for why fluids shear continuously: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/05_SolidVsFluid_ShearStress]]
- Unit conversions for μ (Poise, Pa·s, kgf·s/m²): [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/09_ViscosityUnits_Conversions]]
- Kinematic viscosity ν = μ/ρ: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/10_KinematicViscosity]]
- Temperature dependence of μ: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/11_Viscosity_TemperaturePressure]]
- Newton's law used in the Hagen-Poiseuille derivation: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/18_LaminarFlow_HagenPoiseuille]]

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01b_FluidProperties_Hub]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/02b_FluidProperties_MOC]],
[[Other Notes/EHT/Testing_something_out/Fluid Mechanics/05_SolidVsFluid_ShearStress]]
*Links to:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/09_ViscosityUnits_Conversions]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/10_KinematicViscosity]],
[[Other Notes/EHT/Testing_something_out/Fluid Mechanics/11_Viscosity_TemperaturePressure]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/12_FluidTypes_Newtonian]],
[[Other Notes/EHT/Testing_something_out/Fluid Mechanics/14_ReynoldsNumber]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/18_LaminarFlow_HagenPoiseuille]]
