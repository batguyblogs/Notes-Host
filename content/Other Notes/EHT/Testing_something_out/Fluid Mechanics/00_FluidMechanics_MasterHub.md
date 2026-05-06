---
publish: true
title: Fluid Mechanics MTE 3252 — Master Hub
created: 2026-05-02
modified: 2026-05-04T06:17:45.694+05:30
tags:
  - FluidMechanics
  - hub
  - master-hub
cssclasses: ""
---


# Fluid Mechanics MTE 3252 — Master Hub

Fluid mechanics is the branch of physics concerned with the behaviour of fluids — liquids and
gases — both at rest and in motion. It underpins the design of virtually every engineered system
that involves fluid transport, from municipal water networks and aircraft wings to internal
combustion engines and biomedical devices. This vault organises MTE 3252 into four
interconnected domains that progress logically from first principles to pipe system analysis
and advanced boundary phenomena.

---

## Visual Domain Map

```
FLUID MECHANICS MTE 3252
│
├── Domain A — FLUID FUNDAMENTALS
│     What is a fluid? How does it differ from a solid?
│     What are the sub-branches of FM?
│
├── Domain B — FLUID PROPERTIES
│     Density · Specific Gravity · Specific Weight
│     Dynamic Viscosity · Kinematic Viscosity
│     Fluid Classification (Newtonian / Non-Newtonian)
│
├── Domain C — PIPE FLOW AND ENERGY
│     Flow Classification (Laminar / Turbulent / Reynolds Number)
│     Continuity Equation · Bernoulli's Equation
│     Laminar Flow in Pipes (Hagen-Poiseuille)
│     Major Losses (Darcy-Weisbach) · Minor Losses
│     Moody Diagram · HGL & TEL
│     Pipes in Series and Parallel
│
└── Domain D — ADVANCED TOPICS
      Boundary Layer Theory
      [Heat Exchangers — Placeholder]
```

---

## Domain Hub Index

| Hub | Description |
|---|---|
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01a_FluidFundamentals_Hub]] | Foundational concepts: what fluids are, how they respond to stress, and the taxonomy of FM sub-disciplines |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01b_FluidProperties_Hub]] | Every measurable scalar property of a fluid: density family, viscosity family, and fluid type classification |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01c_PipeFlow_Hub]] | The core engineering domain: flow regimes, conservation laws, energy equations, and loss calculations for pipe systems |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01d_AdvancedTopics_Hub]] | Boundary layer theory and placeholder for heat exchangers |

---

## How the Domains Connect

Domain A establishes the ontological foundation — without a clear definition of what a fluid *is*
and how it responds to shear stress, the constitutive relation for viscosity (Domain B) has no
physical grounding. Domain B then provides the material parameters — especially dynamic and
kinematic viscosity, and density — that feed directly into the Reynolds number, which in turn
governs which equations in Domain C are applicable. Domain C is the engineering heart of the
course: the continuity equation, Bernoulli's equation, the Hagen-Poiseuille law, and the
Darcy-Weisbach equation form a tightly coupled chain in which each result presupposes the
previous. Domain D extends the analysis to flow near solid boundaries, where the assumptions
of ideal or fully-developed flow break down.

---

## Suggested Entry Points

| Use Case | Start Here |
|---|---|
| Complete first-time study | [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01a_FluidFundamentals_Hub]] → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01b_FluidProperties_Hub]] → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01c_PipeFlow_Hub]] |
| Revising viscosity and units for exam | [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/08_DynamicViscosity_NewtonsLaw]] → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/09_ViscosityUnits_Conversions]] → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/10_KinematicViscosity]] |
| Solving pipe flow problems | [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/14_ReynoldsNumber]] → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/15_ContinuityEquation]] → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/16_BernoullisEquation]] → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/20_MajorLosses_DarcyWeisbach]] |
| Understanding energy lines (HGL/TEL) | [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/16_BernoullisEquation]] → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/17_BernoulliRealFluid]] → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/23_HGL_TEL]] |
| Pipe network problems | [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/24_PipesInSeries]] → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/25_PipesInParallel]] |
| Boundary layer introduction | [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/26_BoundaryLayer]] |

---

## Source Notes

| Source | Type | Trust |
|---|---|---|
| FM_Notes.pdf (MTE 3252 lecture slides) | Secondary — unattributed course slides | Medium — consistent with standard FM textbooks but notation inconsistencies present (see individual notes) |

> [!warning] Friction Factor Notation
> The source uses the **Fanning friction factor** ($f = 16/Re$) inside the formula $h_f = 4fLV^2/(d \cdot 2g)$. The Moody diagram in the same source plots the **Darcy friction factor** ($f_D = 64/Re$). Both are equivalent. See [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/20_MajorLosses_DarcyWeisbach]] for full discussion.

> [!warning] Symbol Conflict — SG vs γ
> In the source, specific gravity is labelled both *SG* and *γ*. These notes use *SG* for specific gravity and *γ* exclusively for specific weight. See [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/06_Density_SG_SpecificWeight]].

---

## Exam / Assessment Map

| Topic Area | Key Notes |
|---|---|
| Definitions and properties | [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/03_WhatIsFluid]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/06_Density_SG_SpecificWeight]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/08_DynamicViscosity_NewtonsLaw]] |
| Unit conversions (likely short answer) | [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/09_ViscosityUnits_Conversions]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/10_KinematicViscosity]] |
| Reynolds number and flow type | [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/14_ReynoldsNumber]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/13_LaminarVsTurbulent_Flow]] |
| Hagen-Poiseuille derivation | [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/18_LaminarFlow_HagenPoiseuille]] |
| Darcy-Weisbach and pipe losses | [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/20_MajorLosses_DarcyWeisbach]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/21_MinorLosses]] |
| Pipe networks (series/parallel) | [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/24_PipesInSeries]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/25_PipesInParallel]] |
| Energy lines | [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/23_HGL_TEL]] |

---

## Dataview Queries

| File                                                                                                                                     | title                                                  | type       | status     | confidence |
| ---------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------ | ---------- | ---------- | ---------- |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/27_HeatExchangers_Placeholder\|27_HeatExchangers_Placeholder]]       | Heat Exchangers — Placeholder                          | atomic     | incomplete | low        |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/26_BoundaryLayer\|26_BoundaryLayer]]                                 | Boundary Layer and Boundary Layer Thickness            | atomic     | evergreen  | medium     |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/25_PipesInParallel\|25_PipesInParallel]]                             | Flow Through Pipes in Parallel                         | atomic     | evergreen  | high       |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/24_PipesInSeries\|24_PipesInSeries]]                                 | Flow Through Pipes in Series (Compound Pipes)          | atomic     | evergreen  | high       |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/23_HGL_TEL\|23_HGL_TEL]]                                             | Hydraulic Gradient Line and Total Energy Line          | atomic     | evergreen  | high       |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/22_MoodyDiagram\|22_MoodyDiagram]]                                   | The Moody Diagram                                      | atomic     | evergreen  | medium     |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/21_MinorLosses\|21_MinorLosses]]                                     | Minor Energy Losses in Pipes                           | atomic     | evergreen  | high       |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/20_MajorLosses_DarcyWeisbach\|20_MajorLosses_DarcyWeisbach]]         | Major Losses — Darcy-Weisbach Equation                 | atomic     | evergreen  | high       |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/19_LaminarFlow_Annulus\|19_LaminarFlow_Annulus]]                     | Laminar Flow Through a Circular Annulus                | atomic     | evergreen  | high       |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/18_LaminarFlow_HagenPoiseuille\|18_LaminarFlow_HagenPoiseuille]]     | Laminar Flow Through Circular Pipes — Hagen-Poiseuille | atomic     | evergreen  | high       |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/17_BernoulliRealFluid\|17_BernoulliRealFluid]]                       | Bernoulli's Equation for Real Fluids                   | atomic     | evergreen  | high       |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/16_BernoullisEquation\|16_BernoullisEquation]]                       | Bernoulli's Equation                                   | atomic     | evergreen  | high       |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/15_ContinuityEquation\|15_ContinuityEquation]]                       | Continuity Equation                                    | atomic     | evergreen  | high       |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/14_ReynoldsNumber\|14_ReynoldsNumber]]                               | Reynolds Number                                        | atomic     | evergreen  | high       |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/13_LaminarVsTurbulent_Flow\|13_LaminarVsTurbulent_Flow]]             | Laminar vs Turbulent Flow                              | atomic     | evergreen  | high       |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/12_FluidTypes_Newtonian\|12_FluidTypes_Newtonian]]                   | Fluid Types — Newtonian and Non-Newtonian              | atomic     | evergreen  | medium     |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/11_Viscosity_TemperaturePressure\|11_Viscosity_TemperaturePressure]] | Effect of Temperature and Pressure on Viscosity        | atomic     | evergreen  | high       |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/10_KinematicViscosity\|10_KinematicViscosity]]                       | Kinematic Viscosity                                    | atomic     | evergreen  | high       |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/09_ViscosityUnits_Conversions\|09_ViscosityUnits_Conversions]]       | Viscosity Units and Conversions                        | atomic     | evergreen  | high       |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/08_DynamicViscosity_NewtonsLaw\|08_DynamicViscosity_NewtonsLaw]]     | Dynamic Viscosity and Newton's Law of Viscosity        | atomic     | evergreen  | high       |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/07_SpecificVolume\|07_SpecificVolume]]                               | Specific Volume                                        | atomic     | evergreen  | high       |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/06_Density_SG_SpecificWeight\|06_Density_SG_SpecificWeight]]         | Density, Specific Gravity, and Specific Weight         | atomic     | evergreen  | high       |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/05_SolidVsFluid_ShearStress\|05_SolidVsFluid_ShearStress]]           | Solid vs Fluid — Shear Stress and Deformation          | atomic     | evergreen  | high       |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/04_FM_Subcategories\|04_FM_Subcategories]]                           | Subcategories of Fluid Mechanics                       | atomic     | evergreen  | high       |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/03_WhatIsFluid\|03_WhatIsFluid]]                                     | What Is a Fluid                                        | atomic     | evergreen  | high       |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01d_AdvancedTopics_Hub\|01d_AdvancedTopics_Hub]]                     | Domain Hub — Advanced Topics                           | domain-hub | evergreen  | medium     |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01c_PipeFlow_Hub\|01c_PipeFlow_Hub]]                                 | Domain Hub — Pipe Flow and Energy                      | domain-hub | evergreen  | high       |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01b_FluidProperties_Hub\|01b_FluidProperties_Hub]]                   | Domain Hub — Fluid Properties                          | domain-hub | evergreen  | high       |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01a_FluidFundamentals_Hub\|01a_FluidFundamentals_Hub]]               | Domain Hub — Fluid Fundamentals                        | domain-hub | evergreen  | high       |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/00_FluidMechanics_MasterHub\|00_FluidMechanics_MasterHub]]           | Fluid Mechanics MTE 3252 — Master Hub                  | master-hub | evergreen  | high       |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/02d_AdvancedTopics_MOC\|02d_AdvancedTopics_MOC]]                     | MOC — Advanced Topics                                  | MOC        | evergreen  | medium     |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/02c_PipeFlow_MOC\|02c_PipeFlow_MOC]]                                 | MOC — Pipe Flow and Energy                             | MOC        | evergreen  | high       |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/02b_FluidProperties_MOC\|02b_FluidProperties_MOC]]                   | MOC — Fluid Properties                                 | MOC        | evergreen  | high       |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/02a_FluidFundamentals_MOC\|02a_FluidFundamentals_MOC]]               | MOC — Fluid Fundamentals                               | MOC        | evergreen  | high       |


| File                                                                                                                               | title                                       | source                 |
| ---------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- | ---------------------- |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/27_HeatExchangers_Placeholder\|27_HeatExchangers_Placeholder]] | Heat Exchangers — Placeholder               | NOT IN SOURCE MATERIAL |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/26_BoundaryLayer\|26_BoundaryLayer]]                           | Boundary Layer and Boundary Layer Thickness | FM_Notes.pdf           |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/22_MoodyDiagram\|22_MoodyDiagram]]                             | The Moody Diagram                           | FM_Notes.pdf           |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/12_FluidTypes_Newtonian\|12_FluidTypes_Newtonian]]             | Fluid Types — Newtonian and Non-Newtonian   | FM_Notes.pdf           |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/02d_AdvancedTopics_MOC\|02d_AdvancedTopics_MOC]]               | MOC — Advanced Topics                       | FM_Notes.pdf           |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01d_AdvancedTopics_Hub\|01d_AdvancedTopics_Hub]]               | Domain Hub — Advanced Topics                | FM_Notes.pdf           |


| File | title |
| ---- | ----- |


---

## Backlink Summary
*Links to:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01a_FluidFundamentals_Hub]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01b_FluidProperties_Hub]],
[[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01c_PipeFlow_Hub]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01d_AdvancedTopics_Hub]]
