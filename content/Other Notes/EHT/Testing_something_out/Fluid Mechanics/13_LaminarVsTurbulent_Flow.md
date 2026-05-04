---
publish: true
title: Laminar vs Turbulent Flow
created: 2026-05-02
modified: 2026-05-04T06:19:06.325+05:30
tags:
  - FluidMechanics
  - PipeFlow
  - atomic
  - flow-regimes
cssclasses: ""
---


# Laminar vs Turbulent Flow

**In laminar flow, fluid moves in smooth parallel layers with no mixing between them; in turbulent flow, motion is chaotic and irregular with intense cross-stream mixing — the Reynolds number predicts which regime occurs.**

---

## Definition

Two fundamentally different flow regimes exist in pipe flow:

**Laminar flow**: Flow in which fluid particles move in smooth, ordered, parallel paths
(streamlines). There is no lateral mixing between layers. The flow appears well-organised
and predictable.

**Turbulent flow**: Flow in which fluid particles follow irregular, random, three-dimensional
paths with intense mixing between layers. Velocity fluctuates in both magnitude and direction
at every point in the flow.

The transition between these regimes is governed by the Reynolds number — see [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/14_ReynoldsNumber]].

---

## Mechanism — The Reynolds Dye Experiment

Osborne Reynolds (1883) demonstrated flow regimes experimentally by injecting a thin filament
of dye into flow through a glass tube:

### Low velocity (Laminar):
```
Dye injection
      ↓
 ──────────────────────────────────────────
      ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ dye filament (straight line)
 ──────────────────────────────────────────
 V_avg →
```
- The dye filament remains as a **straight, unbroken line** parallel to the pipe axis
- Layers of fluid slide past each other without mixing
- The dye does not diffuse laterally into the surrounding water

### High velocity (Turbulent):
```
Dye injection
      ↓
 ──────────────────────────────────────────
      ━━━━∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿ dye filament breaks up and diffuses
 ──────────────────────────────────────────
 V_avg →
```
- The dye filament becomes **wavy, then breaks up completely** and diffuses through
  the cross-section
- Fluid particles move in random directions, continuously exchanging mass and momentum
  across the cross-section
- Mixing is intense and immediate

---

## Key Differences

| Feature | Laminar | Turbulent |
|---|---|---|
| Flow pattern | Smooth parallel layers | Chaotic, random, irregular |
| Velocity profile | Parabolic (varies smoothly) | Flatter profile (uniform core) |
| Mixing | None (no cross-stream exchange) | Intense (rapid mixing) |
| Shear stress | Due to viscosity only | Due to viscosity + turbulent momentum transfer |
| Energy loss | Lower (for same velocity) | Higher |
| Predictability | Fully analytical (Hagen-Poiseuille) | Requires empirical correlations |
| Re range | < 2000 | > 4000 |

---

## Flow Regime Criteria (Reynolds Number)

$$Re < 2000 \quad \Rightarrow \quad \text{Laminar flow}$$
$$Re > 4000 \quad \Rightarrow \quad \text{Turbulent flow}$$
$$2000 < Re < 4000 \quad \Rightarrow \quad \text{Transitional flow (unstable)}$$

In the **transitional zone** (2000–4000), the flow is sensitive to disturbances —
it may flip between laminar and turbulent unpredictably. In practice, pipe flow problems
treat the transition zone as turbulent for conservative (safe) design.

> [!note] Critical Reynolds Number
> The "critical" Re of 2300 is sometimes quoted as the single transition point, but in
> practice the transition occurs over the range 2000–4000. The source uses 2000 and 4000
> as the boundaries — use these values in this course.

---

## Velocity Profiles

### Laminar (Parabolic):
```
        u_max (at centreline)
           ↑
    ←──────┤──────→
    ←────  │  ────→
    ←──    │    ──→
    ←─     │     ─→
    ─────────────────  wall (u = 0)
```
Velocity varies as $u = u_{max}[1 - (r/R)^2]$ — a perfect paraboloid.
Average velocity $\bar{u} = u_{max}/2$.

### Turbulent (Flatter):
```
        ←─────────────→   (nearly uniform core)
        ←──────────────→
        ←─────────────→
        ←──────────────→
        ─────────────────  wall (thin viscous sublayer, then rapid rise)
```
Turbulent velocity profile is much flatter in the core with a steep gradient only in
a thin layer near the wall (viscous sublayer). Average velocity is a larger fraction
of centreline velocity compared to laminar flow.

> [!example] Practical Significance
> In a water supply pipe (D = 100 mm, V = 2 m/s, ν = 10⁻⁶ m²/s):
> $Re = Vd/\nu = 2 \times 0.1 / 10^{-6} = 200{,}000$
> This is well into the turbulent regime. Most engineering pipe flows are turbulent.
> Laminar flow in pipes typically occurs only with very viscous fluids or very small pipes.

---

## Why It Matters

The flow regime determines which equations apply:

- **Laminar**: Hagen-Poiseuille gives the exact velocity profile and pressure drop → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/18_LaminarFlow_HagenPoiseuille]]
- **Turbulent**: Must use Darcy-Weisbach with friction factor from Moody diagram → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/20_MajorLosses_DarcyWeisbach]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/22_MoodyDiagram]]
- **Laminar friction factor**: $f = 16/Re$ (exact, derived analytically)
- **Turbulent friction factor**: depends on Re and roughness (empirical, from Moody diagram)

Calculating Re is always the **first step** in any pipe flow problem.

---

## Connections to Other Notes

- Reynolds number calculation and critical values: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/14_ReynoldsNumber]]
- Analytical laminar flow solution: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/18_LaminarFlow_HagenPoiseuille]]
- Friction factor for both regimes: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/20_MajorLosses_DarcyWeisbach]]
- Boundary layer transition mirrors pipe flow transition: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/26_BoundaryLayer]]

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01c_PipeFlow_Hub]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/02c_PipeFlow_MOC]]
*Links to:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/14_ReynoldsNumber]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/18_LaminarFlow_HagenPoiseuille]],
[[Other Notes/EHT/Testing_something_out/Fluid Mechanics/20_MajorLosses_DarcyWeisbach]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/22_MoodyDiagram]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/26_BoundaryLayer]]
