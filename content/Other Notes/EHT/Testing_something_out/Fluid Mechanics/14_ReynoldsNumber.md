---
publish: true
title: Reynolds Number
created: 2026-05-02
modified: 2026-05-04T06:19:10.076+05:30
tags:
  - FluidMechanics
  - PipeFlow
  - atomic
  - dimensionless
  - Reynolds
cssclasses: ""
---


# Reynolds Number

**The Reynolds number (Re) is a dimensionless ratio of inertial forces to viscous forces in a flow; Re = ρVd/μ = Vd/ν; it predicts flow regime: laminar (Re < 2000), transitional (2000–4000), or turbulent (Re > 4000).**

---

## Definition

$$\boxed{Re = \frac{\rho V d}{\mu} = \frac{V d}{\nu}}$$

where:
- $\rho$ = fluid density (kg/m³)
- $V$ = mean flow velocity (m/s)
- $d$ = pipe diameter (m)
- $\mu$ = dynamic viscosity (Pa·s = N·s/m²)
- $\nu$ = kinematic viscosity = $\mu/\rho$ (m²/s)

$Re$ is dimensionless — confirmed by checking units:

$$\left[\frac{\rho V d}{\mu}\right] = \frac{(\text{kg/m}^3)(\text{m/s})(\text{m})}{\text{kg/(m·s)}} = \frac{\text{kg/(m·s)}}{\text{kg/(m·s)}} = 1$$

---

## Physical Meaning

The Reynolds number represents the ratio of two competing forces in the flow:

$$Re = \frac{\text{Inertial forces}}{\text{Viscous forces}}$$

**Inertial forces** ($\propto \rho V^2$): Tend to perpetuate fluid motion, amplify disturbances,
and promote turbulence. A fast, dense flow carries a lot of momentum and any perturbation
tends to grow.

**Viscous forces** ($\propto \mu V/d$): Tend to damp out disturbances and restore orderly
laminar flow. A viscous fluid resists velocity differences between layers.

| Re value | Physical interpretation |
|---|---|
| Small Re | Viscous forces dominate → disturbances damped → laminar flow |
| Large Re | Inertial forces dominate → disturbances amplify → turbulent flow |

---

## Critical Values and Flow Regimes

| Re range | Flow regime | Notes |
|---|---|---|
| $Re < 2000$ | **Laminar** | Hagen-Poiseuille applies; $f = 16/Re$ |
| $2000 \leq Re \leq 4000$ | **Transitional** | Unstable; treat as turbulent for design |
| $Re > 4000$ | **Turbulent** | Use Moody diagram for friction factor |

> [!warning] The Transition Zone
> Between Re = 2000 and 4000, flow is unstable and sensitive to pipe roughness,
> upstream conditions, and vibration. Never design a system to operate in this range.
> If Re falls here, assume turbulent behaviour for conservative head loss estimates.

---

## Two Equivalent Forms

$$Re = \frac{\rho V d}{\mu} \quad \text{(uses μ and ρ separately)}$$

$$Re = \frac{V d}{\nu} \quad \text{(uses ν = μ/ρ directly)}$$

Use whichever form matches the given data. The second form is more common in practice
because ν is often tabulated directly.

> [!tip] Problem-Solving Strategy
> Always calculate Re as the **first step** in any pipe flow problem, even if not asked.
> Re determines:
> 1. Whether Hagen-Poiseuille or Darcy-Weisbach applies
> 2. The friction factor $f$ to use
> 3. Whether the given flow conditions are consistent with the assumed regime

---

## Worked Examples

> [!example] Example 1 — Using μ and ρ
> Crude oil: μ = 0.097 Pa·s, ρ = 900 kg/m³, d = 0.1 m, V = 0.471 m/s
>
> $$Re = \frac{\rho V d}{\mu} = \frac{900 \times 0.471 \times 0.1}{0.097} = \frac{42.39}{0.097} = 436.9$$
>
> Since Re = 437 < 2000, flow is **laminar**. Hagen-Poiseuille applies. ✓

> [!example] Example 2 — Using ν
> Water: ν = 0.01 stoke = 0.01 cm²/s = $0.01 \times 10^{-4}$ m²/s = $10^{-6}$ m²/s,
> d = 0.30 m, V = 3.0 m/s
>
> $$Re = \frac{V d}{\nu} = \frac{3.0 \times 0.30}{10^{-6}} = 9 \times 10^5$$
>
> Since Re = 900,000 >> 4000, flow is **turbulent**. Use Moody diagram for $f$.
> With $Re$ varying from 4000 to $10^6$: $f = 0.079/Re^{0.25}$

> [!example] Example 3 — Confirming Laminar Before Applying Hagen-Poiseuille
> Oil: μ = 0.1 Ns/m², ρ = 900 kg/m³, D = 0.05 m, $\bar{u}$ = 1.782 m/s
>
> $$Re = \frac{900 \times 1.782 \times 0.05}{0.1} = 801.9 < 2000 \quad \checkmark \text{ laminar}$$

---

## The Friction Factor Connection

For **laminar** flow, the friction factor (Fanning) is analytically exact:

$$f = \frac{16}{Re} \quad (Re < 2000)$$

For **turbulent** flow:

$$f = \frac{0.079}{Re^{0.25}} \quad (4000 < Re < 10^6)$$

These values feed directly into the Darcy-Weisbach head loss equation:
$h_f = 4fLV^2/(d \cdot 2g)$ — see [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/20_MajorLosses_DarcyWeisbach]].

---

## Why It Matters

Re is the single most important parameter in pipe flow engineering:

- It is computed before *every* other pipe flow calculation
- It determines whether Hagen-Poiseuille (laminar, exact) or Darcy-Weisbach (turbulent, empirical) governs
- It is the x-axis of the Moody diagram → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/22_MoodyDiagram]]
- It appears in the definition of the boundary layer transition → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/26_BoundaryLayer]]

---

## Connections to Other Notes

- Physical meaning of laminar vs turbulent: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/13_LaminarVsTurbulent_Flow]]
- Dynamic viscosity μ used in Re: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/08_DynamicViscosity_NewtonsLaw]]
- Kinematic viscosity ν used in Re: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/10_KinematicViscosity]]
- Density ρ used in Re: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/06_Density_SG_SpecificWeight]]
- Friction factor from Re: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/20_MajorLosses_DarcyWeisbach]]
- Moody diagram (Re on x-axis): [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/22_MoodyDiagram]]

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01c_PipeFlow_Hub]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/02c_PipeFlow_MOC]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/13_LaminarVsTurbulent_Flow]]
*Links to:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/08_DynamicViscosity_NewtonsLaw]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/10_KinematicViscosity]],
[[Other Notes/EHT/Testing_something_out/Fluid Mechanics/13_LaminarVsTurbulent_Flow]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/20_MajorLosses_DarcyWeisbach]],
[[Other Notes/EHT/Testing_something_out/Fluid Mechanics/22_MoodyDiagram]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/26_BoundaryLayer]]
