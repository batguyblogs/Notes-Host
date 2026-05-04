---
publish: true
title: MOC — Fluid Fundamentals
created: 2026-05-02
modified: 2026-05-04T06:18:16.043+05:30
tags:
  - FluidMechanics
  - MOC
  - FluidFundamentals
cssclasses: ""
---


# Map of Content — Fluid Fundamentals

---

## Cluster 1 — Defining the Fluid

The definition of a fluid is more precise than everyday language suggests. A fluid is not simply
"something that flows" — that framing is circular and fails to distinguish a fluid from a
slow-moving solid under creep. The mechanically rigorous definition centres on the response to
shear stress: a fluid is a substance that *deforms continuously and without limit* under any
shear stress, no matter how small, as long as that stress is maintained. The corollary is equally
important — a fluid cannot sustain a shear stress when at rest. This single criterion separates
fluids from all elastic and plastic solids and provides the physical basis for Newton's law of
viscosity.

> [!info] Notes in this cluster
> - [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/03_WhatIsFluid]] — the complete two-part definition and its consequences
> - [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/05_SolidVsFluid_ShearStress]] — the mechanical contrast between solids and fluids

---

## Cluster 2 — The Mechanics of Shear Deformation

The plate-rubber analogy is the pedagogical key to understanding shear in both solids and
fluids. When a tangential force $F$ is applied to the upper surface of a rubber block (area $A$),
the block deforms to a fixed shear strain angle $\alpha$ — and holds that angle as long as $F$
persists. Remove $F$, and the block springs back. Replace rubber with a fluid and the story
changes entirely: the fluid layer adjacent to the moving plate moves with it at the plate
velocity, while the layer at the fixed lower surface remains stationary. Every intermediate
layer moves at an intermediate velocity — a velocity gradient develops — and crucially, the
fluid *never stops deforming* as long as any force is applied. The shear stress is
$\tau = F/A$, and the rate of deformation (velocity gradient $du/dy$) replaces strain as the
relevant kinematic quantity. This shift — from stress ∝ strain (solids) to stress ∝ strain
*rate* (fluids) — is the conceptual foundation of the entire viscosity framework.

> [!info] Notes in this cluster
> - [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/05_SolidVsFluid_ShearStress]] — plate analogy, velocity gradient, $\tau = F/A$
> - [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/08_DynamicViscosity_NewtonsLaw]] (Domain B) — extends this to $\tau = \mu \, du/dy$

---

## Cluster 3 — The Taxonomy of Fluid Mechanics

Fluid mechanics is not monolithic. Its sub-disciplines are delineated by the compressibility of
the fluid and the geometry and speed of the flow. Hydrodynamics treats practically incompressible
flows (primarily liquids) in a general theoretical sense; hydraulics is the applied engineering
branch dealing with liquid flows in pipes and channels. Gas dynamics applies when density changes
are significant — as in high-speed nozzle flows — and aerodynamics focuses on gas flow
(especially air) around bodies. The course MTE 3252 sits primarily in the hydraulics and
hydrodynamics tradition, with incompressible flow as the default assumption throughout.

> [!info] Notes in this cluster
> - [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/04_FM_Subcategories]] — scope and distinctions of each sub-discipline

---

## Cross-Cluster Connections

- [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/03_WhatIsFluid]] ↔ [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/05_SolidVsFluid_ShearStress]]: The abstract definition of a fluid (Cluster 1) is concretised by the plate analogy (Cluster 2)
- [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/05_SolidVsFluid_ShearStress]] ↔ [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/08_DynamicViscosity_NewtonsLaw]]: The velocity gradient concept from the plate analogy is the same $du/dy$ that appears in Newton's law of viscosity
- [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/04_FM_Subcategories]] ↔ [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/15_ContinuityEquation]]: The incompressible assumption that defines hydraulics is the same assumption that simplifies the continuity equation to $A_1 V_1 = A_2 V_2$

---

## Open Problems / Gaps

1. **Plasma as a fourth state**: The source defines fluids as liquids and gases. How does plasma fit? It behaves as a fluid but is electromagnetically active.
2. **Non-Newtonian shear**: The notes do not analyse what happens when stress is *not* proportional to strain rate — see [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/12_FluidTypes_Newtonian]] for partial coverage.
3. **Granular materials**: Dry sand flows but is not a fluid by this definition — the boundary is philosophically interesting.
4. **Viscoelastic materials**: Substances like silly putty exhibit both solid and fluid behaviour depending on the timescale of loading.

---

## Links to Other Domains

- Shear stress defined here → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/08_DynamicViscosity_NewtonsLaw]] ([[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01b_FluidProperties_Hub]])
- Incompressible assumption → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/15_ContinuityEquation]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/16_BernoullisEquation]] ([[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01c_PipeFlow_Hub]])

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01a_FluidFundamentals_Hub]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/00_FluidMechanics_MasterHub]]
*Links to:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/03_WhatIsFluid]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/04_FM_Subcategories]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/05_SolidVsFluid_ShearStress]]
