---
publish: true
title: Specific Volume
created: 2026-05-02
modified: 2026-05-04T06:18:46.202+05:30
tags:
  - FluidMechanics
  - FluidProperties
  - atomic
  - density
cssclasses: ""
---


# Specific Volume

**Specific volume (v) is the volume occupied per unit mass of fluid — the reciprocal of density.**

---

## Definition

$$v = \frac{V}{m} = \frac{1}{\rho} \quad \left[\text{SI unit: } \frac{\text{m}^3}{\text{kg}}\right]$$

where $V$ = volume (m³), $m$ = mass (kg), $\rho$ = density (kg/m³).

For a differential fluid element:

$$v = \frac{\delta V}{\delta m} \implies \rho = \frac{\delta m}{\delta V}$$

These two are exact inverses:

$$v \cdot \rho = 1$$

---

## Mechanism — Physical Meaning

Specific volume answers the question: *how much space does 1 kg of this fluid occupy?*

- A **dense fluid** (high ρ) has a **small specific volume** — each kilogram is packed
  into a small space (e.g., mercury, $\rho \approx 13600$ kg/m³, $v \approx 7.35 \times 10^{-5}$ m³/kg)
- A **light fluid** (low ρ) has a **large specific volume** — each kilogram is spread over
  a large space (e.g., air at standard conditions, $\rho \approx 1.225$ kg/m³,
  $v \approx 0.816$ m³/kg)

---

## Key Details

### Position in the Density Family

| Property | Symbol | Definition | SI Unit |
|---|---|---|---|
| Density | ρ | $m/V$ | kg/m³ |
| Specific volume | v | $V/m = 1/\rho$ | m³/kg |
| Specific weight | γ | $W/V = \rho g$ | N/m³ |
| Specific gravity | SG | $\rho/\rho_{H_2O}$ | — |

All four properties express the same underlying information — the mass-volume relationship
of the fluid — but in different combinations suited to different calculations.

### Reference Values

| Fluid | ρ (kg/m³) | v (m³/kg) |
|---|---|---|
| Water at 4°C | 1000 | 0.001 |
| Water at 20°C | 998 | 0.001002 |
| Air at 15°C, 1 atm | 1.225 | 0.816 |
| Mercury | 13,600 | $7.35 \times 10^{-5}$ |

> [!example] Worked Example
> A fluid has a density of $\rho = 850 \text{ kg/m}^3$. Find its specific volume.
>
> $$v = \frac{1}{\rho} = \frac{1}{850} = 1.176 \times 10^{-3} \text{ m}^3/\text{kg}$$
>
> This means 1 kg of this fluid occupies approximately 1.176 litres.

### Connection to Thermodynamics

In thermodynamics, specific volume is a primary state variable — it appears in equations of
state for gases (e.g., ideal gas law: $Pv = RT$). For incompressible liquids, $v$ is
essentially constant with pressure and temperature, which is why incompressible flow
analysis is so much simpler than compressible flow.

> [!caution] Low Confidence
> The thermodynamic context (equation of state, ideal gas behaviour) goes beyond the
> provided source material. This is well-established general knowledge — verify against
> your thermodynamics notes if this topic appears in your assessment.

---

## Why It Matters

While specific volume appears less frequently than density in hydraulic calculations, it
is conceptually important because:

1. It makes explicit that density and volume-per-mass are inverse — knowing one immediately
   gives the other
2. In compressible flow (gas dynamics), specific volume changes with pressure and must be
   tracked through the continuity equation: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/15_ContinuityEquation]]
3. It is the natural variable in thermodynamic analyses of fluid systems (turbines, compressors)
4. It clarifies the continuum assumption: the differential form $\rho = \delta m / \delta V$
   requires $\delta V$ to be large enough to contain many molecules but small enough to be
   a "point" in the flow field

> [!note]
> For all incompressible flow problems in this course, specific volume is constant and
> you will rarely calculate it explicitly. Its main role is conceptual — reinforcing that
> $\rho$ and $v$ are two ways of expressing the same property.

---

## Connections to Other Notes

- Density (the reciprocal): [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/06_Density_SG_SpecificWeight]]
- Continuity equation where density changes with position in compressible flow: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/15_ContinuityEquation]]

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01b_FluidProperties_Hub]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/02b_FluidProperties_MOC]],
[[Other Notes/EHT/Testing_something_out/Fluid Mechanics/06_Density_SG_SpecificWeight]]
*Links to:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/06_Density_SG_SpecificWeight]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/15_ContinuityEquation]]
