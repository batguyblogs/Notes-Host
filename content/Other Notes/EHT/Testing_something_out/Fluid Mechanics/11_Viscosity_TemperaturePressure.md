---
publish: true
title: Effect of Temperature and Pressure on Viscosity
created: 2026-05-02
modified: 2026-05-04T06:18:59.694+05:30
tags:
  - FluidMechanics
  - FluidProperties
  - atomic
  - viscosity
cssclasses: ""
---


# Effect of Temperature and Pressure on Viscosity

**Liquid viscosity decreases with increasing temperature (weakened cohesive forces); gas viscosity increases with increasing temperature (increased molecular collisions); both are largely independent of pressure at moderate conditions.**

---

## Definition

Viscosity is not a fixed constant — it depends on the thermodynamic state of the fluid,
principally its temperature. The direction and magnitude of this dependence differs
fundamentally between liquids and gases because the physical mechanisms causing viscosity
differ between the two phases.

---

## Temperature Dependence

### Liquids — Viscosity Decreases with Temperature

**Mechanism**: In a liquid, viscosity arises primarily from **cohesive intermolecular forces**.
Adjacent molecules must overcome these attractive forces to slide past one another. At higher
temperatures, molecules possess greater kinetic energy and can more readily overcome the
cohesive forces, reducing resistance to flow.

Result: $\mu_{\text{liquid}} \downarrow$ as $T \uparrow$

**Practical examples**:
- Honey flows readily when warm, barely at all when cold
- Engine oil viscosity grade (e.g., SAE 10W-40) encodes its viscosity-temperature behaviour
- Hot water flows more easily through pipes than cold water

### Gases — Viscosity Increases with Temperature

**Mechanism**: In a gas, viscosity arises primarily from **momentum exchange via molecular collisions** between faster and slower layers. At higher temperatures, molecules move faster and collide more frequently and energetically, increasing the rate of momentum transfer between layers.

Result: $\mu_{\text{gas}} \uparrow$ as $T \uparrow$

**Practical examples**:
- Air inside a hot engine is slightly more viscous than cool ambient air
- The effect is relatively modest compared to liquids — air viscosity changes by ~20% between 0°C and 100°C

### Comparison Table

| Property | Liquid (T↑) | Gas (T↑) |
|---|---|---|
| Dynamic viscosity μ | **Decreases** | **Increases** |
| Physical mechanism | Reduced cohesive forces | Increased molecular collisions |
| Magnitude of change | Large (orders of magnitude) | Moderate |
| Kinematic viscosity ν | Decreases | Increases (μ↑ and ρ↓ both increase ν) |

> [!note] Why Gases Behave Oppositely
> The key insight: liquid viscosity is dominated by *intermolecular attraction* (which
> thermal energy overcomes), while gas viscosity is dominated by *molecular momentum
> transfer* (which increases with thermal motion). These are opposite mechanisms, hence
> opposite temperature trends.

---

## Pressure Dependence

### Liquids

Dynamic viscosity of liquids is **practically independent of pressure** at normal engineering
pressures. Only at extremely high pressures (thousands of atmospheres) does liquid viscosity
change measurably. For all calculations in this course: $\mu_{\text{liquid}} \neq f(P)$.

### Gases — Dynamic Viscosity

At **low to moderate pressures**, gas dynamic viscosity is also essentially independent of
pressure. This is because viscosity depends on molecular collision frequency, which changes
little with moderate pressure changes.

At **very high pressures** (dense gas regime), μ begins to increase with pressure.

### Gases — Kinematic Viscosity

This is the important exception. For an ideal gas, density is proportional to pressure:

$$\rho = \frac{P}{RT} \implies \rho \propto P$$

Therefore, since $\nu = \mu/\rho$ and μ is roughly constant with P:

$$\nu_{\text{gas}} = \frac{\mu}{\rho} \propto \frac{1}{P}$$

**Kinematic viscosity of a gas decreases as pressure increases.** This affects the Reynolds
number in high-pressure gas pipelines.

---

## Engineering Implications

### Effect on Reynolds Number

$$Re = \frac{Vd}{\nu}$$

Since $\nu$ changes with temperature:

- **Heating a liquid**: ν decreases → Re increases → flow more likely to become turbulent
- **Cooling a liquid**: ν increases → Re decreases → flow more likely to be laminar
- **Heating a gas**: ν increases → Re decreases → flow more likely to stay laminar

> [!example] Effect on Pipe Flow
> Water at 20°C: $\nu \approx 1.0 \times 10^{-6}$ m²/s
> Water at 60°C: $\nu \approx 0.47 \times 10^{-6}$ m²/s
>
> For the same pipe and velocity, Re at 60°C is about twice that at 20°C.
> A flow that is laminar (Re = 1800) at 20°C might transition to turbulent at 60°C —
> changing the entire pressure drop calculation.

> [!caution] Time-Sensitive
> Specific viscosity-temperature data for common fluids (water, air, oils) may appear
> in updated engineering handbooks and standards. The qualitative trends stated here are
> well-established; numerical values should be verified against current tables for
> precision work.

---

## Why It Matters

Temperature effects on viscosity are critical in:

1. **Pump selection**: viscosity determines required pump power
2. **Pipe system design**: viscosity affects Re, friction factor, and head loss
3. **Process industries**: viscosity of oil, polymers, food products changes dramatically with process temperature
4. **Lubrication**: engine oil must maintain adequate viscosity across a wide temperature range

---

## Connections to Other Notes

- Dynamic viscosity definition and Newton's law: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/08_DynamicViscosity_NewtonsLaw]]
- Kinematic viscosity and its pressure dependence: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/10_KinematicViscosity]]
- Reynolds number sensitivity to viscosity changes: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/14_ReynoldsNumber]]
- Non-Newtonian fluids (where μ also varies with strain rate, not just temperature): [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/12_FluidTypes_Newtonian]]

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01b_FluidProperties_Hub]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/08_DynamicViscosity_NewtonsLaw]],
[[Other Notes/EHT/Testing_something_out/Fluid Mechanics/10_KinematicViscosity]]
*Links to:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/08_DynamicViscosity_NewtonsLaw]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/10_KinematicViscosity]],
[[Other Notes/EHT/Testing_something_out/Fluid Mechanics/12_FluidTypes_Newtonian]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/14_ReynoldsNumber]]
