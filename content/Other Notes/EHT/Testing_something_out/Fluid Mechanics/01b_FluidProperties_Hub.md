---
publish: true
title: Domain Hub — Fluid Properties
created: 2026-05-02
modified: 2026-05-04T06:18:05.524+05:30
tags:
  - FluidMechanics
  - hub
  - domain-hub
  - FluidProperties
cssclasses: ""
---


# Domain Hub — Fluid Properties

Fluid properties are the quantitative descriptors that characterise how a fluid behaves under
mechanical loads and how much mass it contains per unit volume. This domain covers the
complete family of density-related properties and both measures of viscosity. Together these
properties serve as the material inputs to every flow equation in the course — they are the
bridge between the conceptual world of Domain A and the computational world of Domain C.

---

## Domain Map

```
FLUID PROPERTIES
│
├── Density Family
│     ├── Density (ρ) — mass per unit volume
│     ├── Specific Gravity (SG) — dimensionless ratio to water
│     ├── Specific Weight (γ) — weight per unit volume
│     └── Specific Volume (v) — volume per unit mass
│
├── Viscosity Family
│     ├── Dynamic (absolute) viscosity (μ)
│     │     ├── Newton's Law of Viscosity: τ = μ(du/dy)
│     │     └── Units: Pa·s, Poise, kgf·s/m²
│     ├── Kinematic viscosity (ν = μ/ρ)
│     │     └── Units: m²/s, Stoke, Centistoke
│     └── Effect of temperature and pressure on μ and ν
│
└── Fluid Classification
      ├── Newtonian fluids (linear τ vs du/dy)
      └── Non-Newtonian fluids (pseudo-plastic, dilatant, Bingham)
```

---

## Note Index

| Note | Description |
|---|---|
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/06_Density_SG_SpecificWeight]] | ρ, SG, γ — all three density-family properties with formulae, units, and worked values |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/07_SpecificVolume]] | Specific volume $v = 1/\rho$; differential density; thermodynamic connection |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/08_DynamicViscosity_NewtonsLaw]] | Newton's law of viscosity; physical meaning of μ; velocity gradient; shear stress calculation |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/09_ViscosityUnits_Conversions]] | SI, MKS, CGS unit systems for μ; Poise; centipoise; conversion chain derivation |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/10_KinematicViscosity]] | $\nu = \mu/\rho$; Stoke; centistoke; unit derivation; SI vs CGS |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/11_Viscosity_TemperaturePressure]] | Why liquid viscosity decreases with T; why gas viscosity increases with T; pressure effects |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/12_FluidTypes_Newtonian]] | Newtonian vs Non-Newtonian fluids; rheological models; practical examples |

---

## MOC

[[Other Notes/EHT/Testing_something_out/Fluid Mechanics/02b_FluidProperties_MOC]]

---

## Key Questions

1. What is the physical meaning of dynamic viscosity and why is it sometimes called the coefficient of internal friction? → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/08_DynamicViscosity_NewtonsLaw]]
2. How do you convert a viscosity value given in poise to SI units, and why does the factor of 10 appear? → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/09_ViscosityUnits_Conversions]]
3. Why does the viscosity of water decrease with rising temperature while the viscosity of air increases? → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/11_Viscosity_TemperaturePressure]]
4. What makes a fluid "Newtonian" and what engineering consequences follow if it is not? → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/12_FluidTypes_Newtonian]]
5. How are density, specific gravity, and specific weight all interrelated through a single formula chain? → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/06_Density_SG_SpecificWeight]]

---

## Suggested Reading Order

1. [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/06_Density_SG_SpecificWeight]]
2. [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/07_SpecificVolume]]
3. [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/08_DynamicViscosity_NewtonsLaw]]
4. [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/09_ViscosityUnits_Conversions]]
5. [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/10_KinematicViscosity]]
6. [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/11_Viscosity_TemperaturePressure]]
7. [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/12_FluidTypes_Newtonian]]
8. Proceed to → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01c_PipeFlow_Hub]]

---

## Links to Other Domains

- ρ from [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/06_Density_SG_SpecificWeight]] feeds directly into the Reynolds number formula in [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/14_ReynoldsNumber]]
- μ from [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/08_DynamicViscosity_NewtonsLaw]] appears in the Hagen-Poiseuille derivation [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/18_LaminarFlow_HagenPoiseuille]] and the Darcy-Weisbach friction factor [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/20_MajorLosses_DarcyWeisbach]]
- ν from [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/10_KinematicViscosity]] is the preferred form of Reynolds number for pipe flow calculations

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/00_FluidMechanics_MasterHub]]
*Links to:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/02b_FluidProperties_MOC]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/06_Density_SG_SpecificWeight]],
[[Other Notes/EHT/Testing_something_out/Fluid Mechanics/07_SpecificVolume]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/08_DynamicViscosity_NewtonsLaw]],
[[Other Notes/EHT/Testing_something_out/Fluid Mechanics/09_ViscosityUnits_Conversions]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/10_KinematicViscosity]],
[[Other Notes/EHT/Testing_something_out/Fluid Mechanics/11_Viscosity_TemperaturePressure]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/12_FluidTypes_Newtonian]]
