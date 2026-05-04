---
publish: true
title: Viscosity Units and Conversions
created: 2026-05-02
modified: 2026-05-04T06:18:52.963+05:30
tags:
  - FluidMechanics
  - FluidProperties
  - atomic
  - viscosity
  - units
cssclasses: ""
---


# Viscosity Units and Conversions

**Dynamic viscosity μ is expressed in Pa·s (SI), kgf·s/m² (MKS), or Poise (CGS); 1 Poise = 0.1 Pa·s, so divide Poise by 10 to convert to SI.**

---

## Definition

The SI unit of dynamic viscosity follows directly from Newton's law $\tau = \mu \, du/dy$:

$$[\mu] = \frac{[\tau]}{[du/dy]} = \frac{\text{N/m}^2}{\text{m/s per m}} = \frac{\text{N·s}}{\text{m}^2} = \text{Pa·s}$$

Three unit systems are in common use. Understanding the conversion chain is essential because
viscosity data in engineering references is often given in CGS (Poise) or MKS units.

---

## The Three Unit Systems

| System | Force unit | Length unit | Viscosity unit |
|---|---|---|---|
| **SI** | Newton (N) | metre (m) | Pa·s = N·s/m² |
| **MKS** | kilogram-force (kgf) | metre (m) | kgf·s/m² |
| **CGS** | dyne (dyn) | centimetre (cm) | Poise (P) = dyn·s/cm² |

> [!note]
> In SI, the second is written **s** (not "sec"). This is a formal SI convention.

---

## Conversion Chain Derivation

### Step 1 — MKS to SI

$$1 \text{ kgf} = 9.81 \text{ N}$$

Therefore:

$$1 \frac{\text{kgf·s}}{\text{m}^2} = \frac{9.81 \text{ N·s}}{\text{m}^2} = 9.81 \text{ Pa·s}$$

### Step 2 — Define the Poise (CGS unit)

$$1 \text{ Poise} = 1 \frac{\text{dyn·s}}{\text{cm}^2}$$

### Step 3 — Convert 1 Newton to dynes

$$1 \text{ N} = 1 \text{ kg} \cdot \frac{\text{m}}{\text{s}^2} = 1000 \text{ g} \cdot \frac{100 \text{ cm}}{\text{s}^2} = 10^5 \frac{\text{g·cm}}{\text{s}^2} = 10^5 \text{ dyn}$$

### Step 4 — Convert 1 Pa·s to Poise

$$1 \text{ Pa·s} = 1 \frac{\text{N·s}}{\text{m}^2} = \frac{10^5 \text{ dyn·s}}{(100 \text{ cm})^2} = \frac{10^5 \text{ dyn·s}}{10^4 \text{ cm}^2} = 10 \frac{\text{dyn·s}}{\text{cm}^2} = 10 \text{ Poise}$$

Therefore:

$$\boxed{1 \text{ Pa·s} = 10 \text{ Poise}}$$

$$\boxed{1 \text{ Poise} = 0.1 \text{ Pa·s} = \frac{1}{10} \text{ Pa·s}}$$

### Step 5 — MKS to Poise

$$1 \frac{\text{kgf·s}}{\text{m}^2} = 9.81 \text{ Pa·s} = 9.81 \times 10 \text{ Poise} = 98.1 \text{ Poise}$$

So to convert from MKS to CGS, multiply by 98.1.
To convert from CGS to MKS, divide by 98.1.

---

## Centipoise (cP)

For practical engineering work with low-viscosity fluids (water, light oils), the Poise is
too large a unit. The **centipoise** is used:

$$1 \text{ cP} = \frac{1}{100} \text{ P} = 0.001 \text{ Pa·s} = 1 \text{ mPa·s}$$

**Reference value**: The viscosity of water at 20°C is **0.01 P = 1.0 cP = 0.001 Pa·s**.

This is a useful benchmark — any fluid with viscosity near 1 cP behaves roughly like water.

---

## Summary Conversion Table

| From | To SI (Pa·s) | Multiply by |
|---|---|---|
| Poise (P) | Pa·s | ÷ 10 = × 0.1 |
| Centipoise (cP) | Pa·s | ÷ 1000 = × 0.001 |
| kgf·s/m² | Pa·s | × 9.81 |
| Pa·s | Poise | × 10 |
| Pa·s | cP | × 1000 |

> [!warning] Exam Trap — The Factor of 10
> The most common error is forgetting to convert Poise to SI before substituting into
> formulae. **If viscosity is given in Poise, divide by 10 to get Pa·s (SI).**
> If given in centipoise, divide by 1000. Every formula in this course ($\tau = \mu \, du/dy$,
> Re, Hagen-Poiseuille, Darcy-Weisbach) requires μ in **Pa·s**.

> [!example] Worked Conversion
> Viscosity given as 0.97 Poise. Convert to SI and MKS.
>
> **To SI**: $\mu = 0.97 / 10 = 0.097 \text{ Pa·s} = 0.097 \text{ N·s/m}^2$
>
> **To MKS**: $\mu = 0.097 / 9.81 = 0.00989 \text{ kgf·s/m}^2$
>
> (This is from Q1 in the source — crude oil at 0.97 Poise.)

---

## Why It Matters

Unit conversion for viscosity is a mandatory first step in every numerical problem:

- All pipe flow formulae (Reynolds number, Hagen-Poiseuille, Darcy-Weisbach) require
  consistent SI units
- Industry data sheets frequently quote μ in cP — always convert before computing
- The conversion factor of 10 (Poise → Pa·s) is simple enough to memorise but frequently
  forgotten under exam pressure

---

## Connections to Other Notes

- The physical meaning of μ and Newton's law: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/08_DynamicViscosity_NewtonsLaw]]
- Kinematic viscosity units (Stoke, centistoke): [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/10_KinematicViscosity]]
- Reynolds number calculation using μ: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/14_ReynoldsNumber]]

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01b_FluidProperties_Hub]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/08_DynamicViscosity_NewtonsLaw]]
*Links to:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/08_DynamicViscosity_NewtonsLaw]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/10_KinematicViscosity]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/14_ReynoldsNumber]]
