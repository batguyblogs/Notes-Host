---
publish: true
title: Laminar Flow Through a Circular Annulus
created: 2026-05-02
modified: 2026-05-04T06:19:28.874+05:30
tags:
  - FluidMechanics
  - PipeFlow
  - atomic
  - laminar
  - annulus
cssclasses: ""
---


# Laminar Flow Through a Circular Annulus

**For laminar flow through the annular gap between two concentric cylinders of outer radius R₁ and inner radius R₂, the velocity profile is logarithmic (not parabolic), and the discharge and shear stress distributions are more complex than in a simple circular pipe.**

---

## Definition

An **annulus** is the region between two concentric cylindrical surfaces. Flow through
annular geometries occurs in heat exchangers (shell-and-tube), coaxial pipe systems,
journal bearings, and drilling operations (fluid between drill pipe and borehole wall).

The geometry:

```
    ←─────── R₁ (outer radius) ──────→
    ┌──────────────────────────────────┐
    │░░░░░░░░░ fluid annulus ░░░░░░░░░│
    │░░░░░  ┌──────────────┐  ░░░░░░░│
    │░░░░░  │  inner wall  │  ░░░░░░░│ ← R₂ (inner radius)
    │░░░░░  └──────────────┘  ░░░░░░░│
    │░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░│
    └──────────────────────────────────┘
```

**Boundary conditions**: $u = 0$ at $r = R_1$ (outer wall) and $u = 0$ at $r = R_2$ (inner wall).

---

## Governing Equation and Solution

Starting from the force balance on an annular fluid element (analogous to the pipe derivation
in [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/18_LaminarFlow_HagenPoiseuille]] but applied to a sleeve element):

$$\frac{\partial p}{\partial x} + \frac{\tau}{r} + \frac{\partial \tau}{\partial r} = 0$$

Substituting $\tau = -\mu \frac{du}{dr}$ and integrating twice, then applying both boundary
conditions ($u = 0$ at $r = R_1$ and $u = 0$ at $r = R_2$), the velocity distribution is:

$$\boxed{u = -\frac{1}{4\mu}\frac{\partial p}{\partial x}\left[R_1^2 - r^2 - \frac{R_1^2 - R_2^2}{\ln(R_1/R_2)}\ln\left(\frac{R_1}{r}\right)\right]}$$

> [!note] Logarithmic vs Parabolic Profile
> Unlike the simple pipe case (pure parabolic profile), the annular velocity distribution
> contains a **logarithmic term** $\ln(R_1/r)$. This arises because the boundary condition
> is applied at *two* radii rather than one, requiring two constants of integration. As
> $R_2 \to 0$, the annular solution reduces to the Hagen-Poiseuille result.

---

## Location of Maximum Velocity

The maximum velocity does not occur at the geometric midpoint — it is offset toward the
inner wall. Setting $du/dr = 0$:

$$r_{max} = \left[\frac{R_1^2 - R_2^2}{2\ln(R_1/R_2)}\right]^{1/2}$$

Substitute this $r_{max}$ back into the velocity equation to find $u_{max}$.

---

## Discharge Through the Annulus

Integrating the velocity profile over the annular cross-section:

$$Q = \int_{R_2}^{R_1} 2\pi r \cdot u \, dr = -\frac{\pi}{8\mu}\frac{\partial p}{\partial x}\left[R_1^4 - R_2^4 - \frac{(R_1^2 - R_2^2)^2}{\ln(R_1/R_2)}\right]$$

---

## Average Velocity

$$\bar{u} = \frac{Q}{\pi(R_1^2 - R_2^2)} = -\frac{1}{8\mu}\frac{\partial p}{\partial x}\left[(R_1^2 + R_2^2) - \frac{R_1^2 - R_2^2}{\ln(R_1/R_2)}\right]$$

---

## Shear Stress Distribution

The velocity gradient from the velocity equation:

$$\frac{du}{dr} = -\frac{1}{4\mu}\frac{\partial p}{\partial x}\left[-2r + \frac{1}{r}\cdot\frac{R_1^2 - R_2^2}{\ln(R_1/R_2)}\right]$$

Therefore the shear stress:

$$\tau = -\mu\frac{du}{dr} = \frac{1}{4}\left(-\frac{\partial p}{\partial x}\right)\left[2r - \frac{1}{r}\cdot\frac{R_1^2 - R_2^2}{\ln(R_1/R_2)}\right]$$

> [!note]
> Shear stress is zero at $r = r_{max}$ (the velocity maximum), positive on the outer
> side (outer wall slows fluid), and negative on the inner side (inner wall slows fluid).
> The shear stress changes sign somewhere within the annulus — unlike the simple pipe
> case where it is always zero at centre and maximum at the wall.

---

## Comparison with Simple Pipe Flow

| Feature | Circular pipe | Annulus |
|---|---|---|
| Boundary conditions | $u = 0$ at $r = R$ | $u = 0$ at $r = R_1$ AND $r = R_2$ |
| Velocity profile | Parabolic ($r^2$ only) | Logarithmic + parabolic |
| Max velocity location | Centreline ($r = 0$) | Between $R_2$ and $R_1$, offset toward $R_2$ |
| $u_{max}/\bar{u}$ | Exactly 2.0 | > 2.0, depends on $R_1/R_2$ |
| Shear stress sign | Always positive | Changes sign across annulus |

> [!tip]
> As $R_2 \to 0$ (inner cylinder shrinks to zero), the annulus formulas reduce exactly
> to the Hagen-Poiseuille results for a circular pipe. This is a useful consistency check.

---

## Why It Matters

Annular flow analysis is important in:
- **Heat exchangers**: annular space between inner tube and shell carries one fluid
- **Lubrication**: journal bearings have annular oil films
- **Drilling engineering**: drilling mud flows in the annulus between drill pipe and borehole
- **Coaxial cables**: viscous flow in cable manufacturing processes

---

## Connections to Other Notes

- The circular pipe derivation this extends: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/18_LaminarFlow_HagenPoiseuille]]
- Newton's law of viscosity used in both derivations: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/08_DynamicViscosity_NewtonsLaw]]

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01c_PipeFlow_Hub]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/02c_PipeFlow_MOC]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/18_LaminarFlow_HagenPoiseuille]]
*Links to:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/18_LaminarFlow_HagenPoiseuille]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/08_DynamicViscosity_NewtonsLaw]]
