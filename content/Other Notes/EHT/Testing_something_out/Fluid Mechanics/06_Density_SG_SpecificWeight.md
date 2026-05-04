---
publish: true
title: Density, Specific Gravity, and Specific Weight
created: 2026-05-02
modified: 2026-05-04T06:18:42.803+05:30
tags:
  - FluidMechanics
  - FluidProperties
  - atomic
  - density
cssclasses: ""
---


# Density, Specific Gravity, and Specific Weight

**Density (ρ) is mass per unit volume; specific gravity (SG) is the dimensionless ratio of a fluid's density to that of water at 4°C; specific weight (γ) is weight per unit volume, equal to ρg.**

---

## Definitions and Formulae

### 1. Density (ρ)

$$\rho = \frac{m}{V} \quad \left[\text{SI unit: } \frac{\text{kg}}{\text{m}^3}\right]$$

where $m$ = mass (kg), $V$ = volume (m³).

For a differential fluid element of mass $\delta m$ and volume $\delta V$:

$$\rho = \lim_{\delta V \to 0} \frac{\delta m}{\delta V}$$

This limit ensures the continuum assumption holds — we are not averaging over individual
molecules but over a volume large enough to contain many molecules yet small compared to
the macroscopic flow scale.

**Reference values:**

| Fluid | Density (kg/m³) | Conditions |
|---|---|---|
| Water | 1000 | 4°C, 1 atm |
| Water | ~998 | 20°C, 1 atm |
| Air | ~1.225 | 15°C, 1 atm |
| Mercury | ~13,600 | 20°C |
| Crude oil | ~850–950 | varies |

---

### 2. Specific Gravity (SG) — also called Relative Density

$$SG = \frac{\rho_{\text{fluid}}}{\rho_{\text{standard fluid}}}$$

The standard fluid is **water at 4°C**, for which $\rho_{H_2O} = 1000 \text{ kg/m}^3$.

$$SG = \frac{\rho_{\text{fluid}}}{1000} \quad \text{(dimensionless)}$$

> [!warning] Symbol Conflict in Source
> The source PDF (p. 10) uses *γ* (gamma) as the symbol for specific gravity in the formula
> box, but γ is universally used for specific weight. These notes use *SG* for specific
> gravity throughout to avoid confusion. See also [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/02b_FluidProperties_MOC]].

**Key property**: SG is dimensionless. SG > 1 means the fluid is denser than water; SG < 1
means it floats on water.

**Examples:**
- Mercury: SG ≈ 13.6
- Seawater: SG ≈ 1.025
- Crude oil: SG ≈ 0.85–0.95
- Air: SG ≈ 0.00123 (essentially negligible vs water)

**Practical use**: If SG is given, convert to density immediately:

$$\rho_{\text{fluid}} = SG \times 1000 \text{ kg/m}^3$$

---

### 3. Specific Weight (γ) — also called Weight Density

$$\gamma_s = \frac{W}{V} = \frac{mg}{V} = \rho g \quad \left[\text{SI unit: } \frac{\text{N}}{\text{m}^3}\right]$$

where $W$ = weight (N), $g$ = acceleration due to gravity = 9.81 m/s².

For water at standard conditions:

$$\gamma_{water} = 1000 \times 9.81 = 9810 \text{ N/m}^3 \approx 9.81 \text{ kN/m}^3$$

> [!note] Specific Weight vs Density
> Density is a *mass* property (kg/m³); specific weight is a *force* property (N/m³).
> They are related by $\gamma = \rho g$. On Earth, $g = 9.81$ m/s².
> On the Moon ($g = 1.62$ m/s²), density is unchanged but specific weight is 6× smaller.

---

## The Relationship Chain

All four density-family properties are interrelated:

$$\rho \xrightarrow{\times g} \gamma \qquad \rho \xrightarrow{\div \rho_{H_2O}} SG \qquad \rho \xrightarrow{1/\rho} v$$

Full chain:

$$\rho = \frac{m}{V}, \quad SG = \frac{\rho}{1000}, \quad \gamma = \rho g, \quad v = \frac{1}{\rho}$$

> [!example] Worked Example
> A crude oil sample has SG = 0.9. Find its density, specific weight, and specific volume.
>
> **Density**: $\rho = 0.9 \times 1000 = 900 \text{ kg/m}^3$
>
> **Specific weight**: $\gamma = \rho g = 900 \times 9.81 = 8829 \text{ N/m}^3$
>
> **Specific volume**: $v = 1/\rho = 1/900 = 1.111 \times 10^{-3} \text{ m}^3/\text{kg}$

---

## Why It Matters

Density is not an abstract property — it appears directly in the most important formulae
of the course:

- **Reynolds number**: $Re = \rho V d / \mu$ → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/14_ReynoldsNumber]]
- **Bernoulli's equation**: pressure head is $P/\rho g$ → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/16_BernoullisEquation]]
- **Continuity (compressible)**: $\rho_1 A_1 V_1 = \rho_2 A_2 V_2$ → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/15_ContinuityEquation]]
- **Pumping power**: $P = \rho g Q h_f$ → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/20_MajorLosses_DarcyWeisbach]]
- **Hagen-Poiseuille**: density implicit in viscous force balance → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/18_LaminarFlow_HagenPoiseuille]]

In virtually every numerical pipe flow problem, the first step is to extract density from
the given SG using $\rho = SG \times 1000$.

> [!tip] Exam Pattern
> Problems almost always give SG rather than ρ directly. The instant you see SG, write:
> $\rho = SG \times 1000 \text{ kg/m}^3$. This single step unlocks Re, Bernoulli, and power.

---

## Connections to Other Notes

- Specific volume (the fourth density-family property): [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/07_SpecificVolume]]
- Reynolds number calculation using ρ: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/14_ReynoldsNumber]]
- Bernoulli's pressure head $P/\rho g$: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/16_BernoullisEquation]]
- Kinematic viscosity $\nu = \mu/\rho$ uses ρ as denominator: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/10_KinematicViscosity]]

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01b_FluidProperties_Hub]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/02b_FluidProperties_MOC]]
*Links to:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/07_SpecificVolume]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/10_KinematicViscosity]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/14_ReynoldsNumber]],
[[Other Notes/EHT/Testing_something_out/Fluid Mechanics/15_ContinuityEquation]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/16_BernoullisEquation]]
