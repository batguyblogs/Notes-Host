---
publish: true
title: MOC — Pipe Flow and Energy
created: 2026-05-02
modified: 2026-05-04T06:18:23.163+05:30
tags:
  - FluidMechanics
  - MOC
  - PipeFlow
cssclasses: ""
---


# Map of Content — Pipe Flow and Energy

---

## Cluster 1 — Flow Classification and the Reynolds Number

Before any flow equation can be applied, the engineer must establish which *regime* the flow
occupies. Laminar flow is highly ordered — fluid moves in parallel layers (laminae) with no
cross-stream mixing. Turbulent flow is chaotic — velocity fluctuates randomly in all directions
and mixing is intense. The Reynolds number $Re = \rho V d / \mu = Vd/\nu$ is the single
dimensionless parameter that predicts the regime. Physically, Re represents the ratio of
inertial forces (which tend to destabilise flow into turbulence) to viscous forces (which tend
to damp out disturbances and preserve order). The critical values — Re < 2000 for laminar,
Re > 4000 for turbulent — are empirically established and are the first calculation performed
in any pipe flow problem.

> [!info] Notes in this cluster
> - [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/13_LaminarVsTurbulent_Flow]] — physical description; dye experiment; observable features
> - [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/14_ReynoldsNumber]] — formula; physical meaning; critical values; calculation

---

## Cluster 2 — Conservation Laws: Mass and Energy

Two conservation principles underpin all pipe flow analysis. The **continuity equation**
($\rho_1 A_1 V_1 = \rho_2 A_2 V_2$, or $A_1 V_1 = A_2 V_2$ for incompressible flow) states
that mass is neither created nor destroyed. **Bernoulli's equation**
($P/\rho g + V^2/2g + z = \text{const}$) is the mechanical energy equation along a streamline
for an ideal fluid. Bernoulli rests on four assumptions — ideal (inviscid) fluid, steady flow,
incompressible flow, and flow along a streamline. Real fluids violate the first assumption,
which means a head loss term $h_L$ must be added to account for viscous dissipation.

> [!info] Notes in this cluster
> - [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/15_ContinuityEquation]] — derivation; compressible and incompressible forms
> - [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/16_BernoullisEquation]] — full derivation basis; three heads; two-point form
> - [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/17_BernoulliRealFluid]] — modified Bernoulli; physical meaning of $h_L$

---

## Cluster 3 — Laminar Flow Analysis (Hagen-Poiseuille)

For flow at Re < 2000 in circular pipes, the complete velocity field can be derived
analytically from first principles. The derivation proceeds by isolating a cylindrical fluid
element, writing a force balance, applying Newton's law of viscosity, and integrating subject
to the no-slip boundary condition ($u = 0$ at $r = R$). The result is a parabolic velocity
profile where the centreline velocity is exactly twice the cross-sectional average:
$u_{max}/\bar{u} = 2$. The Hagen-Poiseuille pressure drop formula
$\Delta p = 32 \mu \bar{u} L / D^2$ shows that pressure drop scales as $D^{-2}$ — a fourfold
increase in diameter reduces friction pressure drop by a factor of sixteen.

> [!info] Notes in this cluster
> - [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/18_LaminarFlow_HagenPoiseuille]] — full derivation; parabolic profile; Δp formula
> - [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/19_LaminarFlow_Annulus]] — extension to annular geometry

---

## Cluster 4 — Energy Losses and the Darcy-Weisbach Framework

In real piping systems, energy is dissipated by two mechanisms. **Major losses** arise from
wall friction acting over pipe length — quantified by the Darcy-Weisbach equation
$h_f = 4fLV^2/(d \cdot 2g)$. The friction factor $f$ is a function of Re (and pipe roughness
for turbulent flow), readable from the **Moody diagram**. **Minor losses** arise from local
geometric disturbances — sudden enlargements, contractions, bends, valves, entrance and exit
conditions — each characterised by a loss coefficient $k$ multiplied by the velocity head
$V^2/2g$. The Hydraulic Gradient Line (HGL) and Total Energy Line (TEL) provide a graphical
tool for visualising where energy is gained (pumps), maintained, or dissipated along the system.

> [!info] Notes in this cluster
> - [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/20_MajorLosses_DarcyWeisbach]] — Darcy-Weisbach; friction factor; Fanning vs Darcy flag
> - [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/21_MinorLosses]] — all seven types with formulae and coefficients
> - [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/22_MoodyDiagram]] — how to read it; regimes; roughness effects
> - [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/23_HGL_TEL]] — graphical energy representation

---

## Cluster 5 — Pipe Networks

When pipes are connected **in series**, the discharge is common to all pipes but head losses
add: $H = \sum h_f$. When pipes are connected **in parallel**, the head loss across each
branch is equal but discharges add: $Q = \sum Q_i$ with $h_{f1} = h_{f2}$. These two
governing conditions, combined with the Darcy-Weisbach equation and the continuity equation,
form a system of simultaneous equations solvable for the unknown velocities and flows.

> [!info] Notes in this cluster
> - [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/24_PipesInSeries]] — governing conditions; full head loss equation; worked approach
> - [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/25_PipesInParallel]] — equal head loss condition; discharge distribution; worked approach

---

## Cross-Cluster Connections

- [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/14_ReynoldsNumber]] ↔ [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/20_MajorLosses_DarcyWeisbach]]: Re determines friction factor $f$
- [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/16_BernoullisEquation]] ↔ [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/23_HGL_TEL]]: Each Bernoulli term is one component of the TEL
- [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/17_BernoulliRealFluid]] ↔ [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/20_MajorLosses_DarcyWeisbach]]: $h_L$ in modified Bernoulli is quantified using Darcy-Weisbach
- [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/18_LaminarFlow_HagenPoiseuille]] ↔ [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/20_MajorLosses_DarcyWeisbach]]: For laminar flow $f = 16/Re$ — both approaches give identical Δp
- [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/15_ContinuityEquation]] ↔ [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/24_PipesInSeries]]: Continuity enforces $Q_1 = Q_2 = Q_3$ in series
- [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/21_MinorLosses]] ↔ [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/24_PipesInSeries]]: Entrance, contraction, enlargement, exit losses all feed into the series total head equation

---

## Open Problems / Gaps

1. **Turbulent velocity profiles**: The course derives the laminar (parabolic) profile but not the turbulent log-law or power-law profiles.
2. **Hardy-Cross method**: Iterative pipe network analysis for complex looped systems is not covered.
3. **Water hammer**: Transient pressure waves from sudden valve closure — a critical real-world concern.
4. **Pump and turbine integration**: Bernoulli with pump/turbine head terms is the natural next step but only hinted at.
5. **Non-circular cross-sections**: The hydraulic diameter concept is implied but not derived.

---

## Links to Other Domains

- μ and ρ from [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01b_FluidProperties_Hub]] → all Re and Darcy-Weisbach calculations here
- No-slip condition used in [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/18_LaminarFlow_HagenPoiseuille]] → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/26_BoundaryLayer]] ([[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01d_AdvancedTopics_Hub]])

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01c_PipeFlow_Hub]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/00_FluidMechanics_MasterHub]]
*Links to:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/13_LaminarVsTurbulent_Flow]] through [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/25_PipesInParallel]]
