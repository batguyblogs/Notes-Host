---
publish: true
title: Domain Hub — Pipe Flow and Energy
created: 2026-05-02
modified: 2026-05-04T06:18:08.605+05:30
tags:
  - FluidMechanics
  - hub
  - domain-hub
  - PipeFlow
cssclasses: ""
---


# Domain Hub — Pipe Flow and Energy

This is the computational core of the course. Beginning with the classification of flow regimes
and the Reynolds number, it progresses through the two great conservation laws of fluid
mechanics (mass and energy), derives the velocity profile and pressure drop for laminar pipe
flow, and then develops a comprehensive framework for calculating energy losses — both
frictional (major) and geometric (minor) — in pipe systems of any configuration. This domain
directly answers the questions a practising engineer asks: *How much pressure does my pump
need to deliver? What diameter pipe is required? Where is the energy going?*

---

## Domain Map

```
PIPE FLOW AND ENERGY
│
├── Flow Classification
│     ├── Laminar flow (ordered layers)
│     ├── Turbulent flow (chaotic mixing)
│     └── Reynolds number Re = ρVd/μ = Vd/ν
│           Re < 2000 → laminar
│           Re > 4000 → turbulent
│           2000–4000 → transitional
│
├── Conservation Laws
│     ├── Continuity: ρ₁A₁V₁ = ρ₂A₂V₂
│     └── Bernoulli: P/ρg + V²/2g + z = const
│           (ideal fluid) → + hL for real fluid
│
├── Laminar Flow Analysis
│     ├── Hagen-Poiseuille: parabolic profile
│     │     umax/ū = 2;  Δp = 32μūL/D²
│     └── Annular geometry extension
│
├── Energy Losses
│     ├── Major: Darcy-Weisbach  hf = 4fLV²/(d·2g)
│     ├── Minor: enlargement, contraction, bends,
│     │          entrance, exit, fittings, obstruction
│     └── Moody Diagram (f vs Re vs ε/d)
│
├── Energy Visualisation
│     ├── Hydraulic Gradient Line (HGL)
│     └── Total Energy Line (TEL / EGL)
│
└── Pipe Networks
      ├── Series: same Q, additive hf
      └── Parallel: same hf, additive Q
```

---

## Note Index

| Note | Description |
|---|---|
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/13_LaminarVsTurbulent_Flow]] | Reynolds dye experiment; physical characteristics of laminar vs turbulent flow |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/14_ReynoldsNumber]] | Full derivation of Re; physical meaning as inertia/viscous ratio; critical values |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/15_ContinuityEquation]] | Conservation of mass; compressible and incompressible forms; mass flow rate |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/16_BernoullisEquation]] | Three-head form; energy interpretation; assumptions; two-point equation |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/17_BernoulliRealFluid]] | Modified Bernoulli with $h_L$; why real fluids always lose energy |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/18_LaminarFlow_HagenPoiseuille]] | Full derivation from force balance; parabolic velocity profile; Hagen-Poiseuille pressure drop |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/19_LaminarFlow_Annulus]] | Annular geometry; logarithmic velocity distribution; discharge and shear formulae |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/20_MajorLosses_DarcyWeisbach]] | Darcy-Weisbach equation; friction factor values; Fanning vs Darcy flag |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/21_MinorLosses]] | All seven minor losses with formulae; vena contracta; loss coefficients |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/22_MoodyDiagram]] | How to read it; laminar, transitional, turbulent, fully-rough regimes |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/23_HGL_TEL]] | Piezometric head; HGL; TEL/EGL; graphical interpretation of energy |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/24_PipesInSeries]] | Compound pipe analysis; same discharge condition; total head loss equation |
| [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/25_PipesInParallel]] | Parallel pipe analysis; same head loss condition; discharge splitting |

---

## MOC

[[Other Notes/EHT/Testing_something_out/Fluid Mechanics/02c_PipeFlow_MOC]]

---

## Key Questions

1. What physical ratio does the Reynolds number represent, and why does a large value favour turbulence? → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/14_ReynoldsNumber]]
2. Why is the velocity profile parabolic in laminar pipe flow, and what fixes the maximum velocity at the centreline? → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/18_LaminarFlow_HagenPoiseuille]]
3. What is the ratio of maximum to average velocity in fully developed laminar pipe flow, and why? → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/18_LaminarFlow_HagenPoiseuille]]
4. When can Bernoulli's equation be applied and what must be added for real fluids? → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/16_BernoullisEquation]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/17_BernoulliRealFluid]]
5. How does the Darcy-Weisbach friction factor differ from the Moody friction factor, and how do you find it? → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/20_MajorLosses_DarcyWeisbach]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/22_MoodyDiagram]]
6. What is the governing equation for pipes in parallel and how does it differ from pipes in series? → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/24_PipesInSeries]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/25_PipesInParallel]]

---

## Suggested Reading Order

1. [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/13_LaminarVsTurbulent_Flow]]
2. [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/14_ReynoldsNumber]]
3. [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/15_ContinuityEquation]]
4. [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/16_BernoullisEquation]]
5. [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/17_BernoulliRealFluid]]
6. [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/18_LaminarFlow_HagenPoiseuille]]
7. [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/19_LaminarFlow_Annulus]]
8. [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/20_MajorLosses_DarcyWeisbach]]
9. [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/21_MinorLosses]]
10. [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/22_MoodyDiagram]]
11. [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/23_HGL_TEL]]
12. [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/24_PipesInSeries]]
13. [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/25_PipesInParallel]]

---

## Links to Other Domains

- Re uses μ from [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/08_DynamicViscosity_NewtonsLaw]] and ρ from [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/06_Density_SG_SpecificWeight]]
- The no-slip condition in [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/18_LaminarFlow_HagenPoiseuille]] is the same mechanism that drives boundary layer growth in [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/26_BoundaryLayer]]
- Bernoulli's velocity head connects to kinetic energy concepts developed via the shear analogy in [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/05_SolidVsFluid_ShearStress]]

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/00_FluidMechanics_MasterHub]]
*Links to:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/02c_PipeFlow_MOC]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/13_LaminarVsTurbulent_Flow]] through [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/25_PipesInParallel]]
