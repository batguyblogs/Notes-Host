---
publish: true
title: MOC — Fluid Properties
created: 2026-05-02
modified: 2026-05-04T06:18:20.003+05:30
tags:
  - FluidMechanics
  - MOC
  - FluidProperties
cssclasses: ""
---


# Map of Content — Fluid Properties

---

## Cluster 1 — The Density Family

Density, specific gravity, specific weight, and specific volume are not four independent
properties — they are four different ways of expressing the same underlying quantity: how much
mass (or weight, or volume) a fluid packs into a given space. Their relationships form a
compact algebra: $\rho = m/V$, $SG = \rho / \rho_{H_2O}$, $\gamma = \rho g$, $v = 1/\rho$.
Water at 4 °C with $\rho = 1000 \, \text{kg/m}^3$ serves as the universal reference point.
Understanding this cluster is prerequisite to any numerical pipe flow calculation, because
density appears in the Reynolds number, the continuity equation, Bernoulli's equation, and
the power formula $P = \rho g Q h_f$.

> [!info] Notes in this cluster
> - [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/06_Density_SG_SpecificWeight]] — ρ, SG, γ with full formulae
> - [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/07_SpecificVolume]] — $v = 1/\rho$; differential form; thermodynamic context

---

## Cluster 2 — The Viscosity Family

Viscosity is the fluid property that quantifies internal resistance to shear deformation. It
comes in two flavours that serve different purposes. **Dynamic (absolute) viscosity** μ appears
in constitutive relations — it directly links shear stress to velocity gradient via Newton's
law $\tau = \mu \, du/dy$. **Kinematic viscosity** $\nu = \mu/\rho$ is the form that appears
naturally in dimensionless groups (Reynolds number), because it combines the resistance to
shear (μ) with the inertia of the fluid (ρ). The unit systems for viscosity are historically
fragmented — SI gives Pa·s, CGS gives Poise, and the conversion chain is a common exam trap.
The key conversion: 1 Poise = 0.1 Pa·s (divide by 10 to convert Poise → SI).

> [!info] Notes in this cluster
> - [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/08_DynamicViscosity_NewtonsLaw]] — μ; Newton's law; physical meaning
> - [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/09_ViscosityUnits_Conversions]] — full unit conversion chain
> - [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/10_KinematicViscosity]] — ν; Stoke; centistoke; unit derivation
> - [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/11_Viscosity_TemperaturePressure]] — temperature and pressure dependence

---

## Cluster 3 — Fluid Classification by Rheology

A Newtonian fluid obeys Newton's law of viscosity exactly: the shear stress–strain rate
relationship is linear through the origin, and μ is a constant independent of strain rate.
Water and air are Newtonian to excellent approximation under normal conditions. Many
industrially important fluids are not — paints, polymers, blood, and cement slurries all
deviate in ways that matter enormously for their processing and pumping. Non-Newtonian
behaviour is not treated quantitatively in this course, but understanding the concept clarifies
the domain of validity of every formula derived under the Newtonian assumption.

> [!info] Notes in this cluster
> - [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/12_FluidTypes_Newtonian]] — Newtonian definition; non-Newtonian types; examples

---

## Cross-Cluster Connections

- [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/06_Density_SG_SpecificWeight]] ↔ [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/10_KinematicViscosity]]: ρ from the density family is the denominator in $\nu = \mu/\rho$
- [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/08_DynamicViscosity_NewtonsLaw]] ↔ [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/12_FluidTypes_Newtonian]]: Newton's law defines what Newtonian *means* — non-Newtonian fluids violate it
- [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/11_Viscosity_TemperaturePressure]] ↔ [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/14_ReynoldsNumber]]: Temperature changes alter μ, which shifts Re and can change the flow regime
- [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/06_Density_SG_SpecificWeight]] ↔ [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/15_ContinuityEquation]]: In incompressible flow, ρ = constant allows mass continuity to reduce to $A_1 V_1 = A_2 V_2$

---

## Open Problems / Gaps

1. **Surface tension**: Not covered in the source but a key fluid property, especially for microfluidics and free-surface flows.
2. **Bulk modulus / compressibility**: Relevant whenever pressure waves or water hammer is a concern.
3. **Non-Newtonian modelling**: The Ostwald–de Waele power law and Bingham plastic model are standard but absent from the source.
4. **Viscosity measurement methods**: Rotational viscometers, capillary viscometers — practical laboratory knowledge not in the notes.

---

## Links to Other Domains

- ρ and μ from this domain → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/14_ReynoldsNumber]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/18_LaminarFlow_HagenPoiseuille]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/20_MajorLosses_DarcyWeisbach]] (Domain C)
- The Newtonian assumption from [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/12_FluidTypes_Newtonian]] is a stated prerequisite of the Hagen-Poiseuille derivation [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/18_LaminarFlow_HagenPoiseuille]]

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01b_FluidProperties_Hub]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/00_FluidMechanics_MasterHub]]
*Links to:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/06_Density_SG_SpecificWeight]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/07_SpecificVolume]],
[[Other Notes/EHT/Testing_something_out/Fluid Mechanics/08_DynamicViscosity_NewtonsLaw]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/09_ViscosityUnits_Conversions]],
[[Other Notes/EHT/Testing_something_out/Fluid Mechanics/10_KinematicViscosity]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/11_Viscosity_TemperaturePressure]],
[[Other Notes/EHT/Testing_something_out/Fluid Mechanics/12_FluidTypes_Newtonian]]
