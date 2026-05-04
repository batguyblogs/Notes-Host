---
publish: true
title: Kinematic Viscosity
created: 2026-05-02
modified: 2026-05-04T06:18:56.434+05:30
tags:
  - FluidMechanics
  - FluidProperties
  - atomic
  - viscosity
cssclasses: ""
---


# Kinematic Viscosity

**Kinematic viscosity (ν) is the ratio of dynamic viscosity to fluid density: ν = μ/ρ; it represents the diffusion of momentum through a fluid and appears naturally in the Reynolds number.**

---

## Definition

$$\nu = \frac{\mu}{\rho} \quad \left[\text{SI unit: } \frac{\text{m}^2}{\text{s}}\right]$$

where $\mu$ = dynamic viscosity (Pa·s), $\rho$ = density (kg/m³).

Symbol: $\nu$ (Greek letter nu).

The name "kinematic" reflects that it involves only kinematic quantities (length and time) —
the force dimension of dynamic viscosity cancels with density, leaving dimensions of
$\text{length}^2/\text{time}$.

---

## Unit Derivation

$$[\nu] = \frac{[\mu]}{[\rho]} = \frac{\text{N·s/m}^2}{\text{kg/m}^3} = \frac{\text{kg·m/s}^2 \cdot \text{s/m}^2}{\text{kg/m}^3} = \frac{\text{kg/(m·s)}}{\text{kg/m}^3} = \frac{\text{m}^2}{\text{s}}$$

---

## The Stoke (CGS Unit)

In the CGS system, kinematic viscosity is measured in **Stokes (St)**:

$$1 \text{ St} = 1 \frac{\text{cm}^2}{\text{s}} = \left(\frac{1}{100}\right)^2 \frac{\text{m}^2}{\text{s}} = 10^{-4} \frac{\text{m}^2}{\text{s}}$$

The **centistoke (cSt)** is used for practical engineering:

$$1 \text{ cSt} = \frac{1}{100} \text{ St} = 10^{-6} \frac{\text{m}^2}{\text{s}}$$

### Conversion Table

| Unit | Equivalent in m²/s |
|---|---|
| 1 Stoke (St) | $1 \times 10^{-4}$ m²/s |
| 1 centistoke (cSt) | $1 \times 10^{-6}$ m²/s |
| 1 m²/s | $10^4$ St = $10^6$ cSt |

> [!warning] Exam Trap — Stoke Conversion
> Like Poise for dynamic viscosity, the Stoke must be converted before use in SI formulae.
> If kinematic viscosity is given in Stokes: multiply by $10^{-4}$ to get m²/s.
> If given in centistokes: multiply by $10^{-6}$ to get m²/s.

---

## Key Details

### Why ν Appears Naturally in the Reynolds Number

The Reynolds number can be written two equivalent ways:

$$Re = \frac{\rho V d}{\mu} = \frac{V d}{\nu}$$

The second form is preferred in practice because:
1. It requires only one fluid property (ν) instead of two (μ and ρ separately)
2. Kinematic viscosity is frequently tabulated directly in engineering references
3. It makes the dimensionless character of Re more transparent ($[Vd/\nu] = [\text{m/s} \cdot \text{m} / (\text{m}^2/\text{s})] = $ dimensionless)

### Pressure Dependence

Kinematic viscosity behaves differently from dynamic viscosity under pressure changes:

- For **liquids**: both μ and ρ are nearly independent of pressure at moderate pressures,
  so ν ≈ constant with pressure
- For **gases**: μ is nearly independent of pressure (at low to moderate pressures), BUT
  ρ is proportional to pressure (ideal gas law: $\rho = P/RT$). Therefore:

$$\nu_{\text{gas}} = \frac{\mu}{\rho} \propto \frac{\mu}{P} \quad \text{— decreases as pressure increases}$$

This is important in high-pressure gas systems where the Reynolds number will be higher
than expected from the dynamic viscosity alone.

### Reference Values

| Fluid | T (°C) | ν (m²/s) |
|---|---|---|
| Water | 20 | $1.004 \times 10^{-6}$ (≈ 1 cSt) |
| Water | 60 | $0.474 \times 10^{-6}$ |
| Air | 20 | $15.1 \times 10^{-6}$ |
| Engine oil (SAE 30) | 40 | ~100 × 10⁻⁶ |
| Honey | 20 | ~10,000 × 10⁻⁶ |

> [!note]
> Note that air has a *kinematic* viscosity about 15× that of water at 20°C, even though
> its dynamic viscosity is ~55× *smaller*. This is because air's density is ~800× smaller
> than water's. In the Reynolds number, air and water flows at similar velocities and
> length scales will therefore have comparable Re values.

> [!example] Worked Example
> A fluid has μ = 0.097 Pa·s and SG = 0.9. Find ν in m²/s and in Stokes.
>
> $\rho = 0.9 \times 1000 = 900 \text{ kg/m}^3$
>
> $\nu = \mu/\rho = 0.097/900 = 1.078 \times 10^{-4} \text{ m}^2/\text{s}$
>
> In Stokes: $\nu = 1.078 \times 10^{-4} / 10^{-4} = 1.078 \text{ St}$

---

## Why It Matters

Kinematic viscosity is the single most-used viscosity parameter in pipe flow calculations:

- **Reynolds number**: $Re = Vd/\nu$ — determines laminar vs turbulent regime → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/14_ReynoldsNumber]]
- **Moody diagram**: both axes depend on Re which uses ν → [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/22_MoodyDiagram]]
- Pipe flow problems almost always give ν (often in Stokes) rather than μ and ρ separately

---

## Connections to Other Notes

- Dynamic viscosity μ (the numerator): [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/08_DynamicViscosity_NewtonsLaw]]
- Density ρ (the denominator): [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/06_Density_SG_SpecificWeight]]
- Unit conversions for μ (Poise): [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/09_ViscosityUnits_Conversions]]
- Reynolds number using ν: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/14_ReynoldsNumber]]
- Pressure dependence of ν for gases: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/11_Viscosity_TemperaturePressure]]

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01b_FluidProperties_Hub]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/08_DynamicViscosity_NewtonsLaw]],
[[Other Notes/EHT/Testing_something_out/Fluid Mechanics/09_ViscosityUnits_Conversions]]
*Links to:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/06_Density_SG_SpecificWeight]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/11_Viscosity_TemperaturePressure]],
[[Other Notes/EHT/Testing_something_out/Fluid Mechanics/14_ReynoldsNumber]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/22_MoodyDiagram]]
