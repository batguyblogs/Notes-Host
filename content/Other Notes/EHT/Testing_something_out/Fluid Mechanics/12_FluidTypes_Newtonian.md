---
publish: true
title: Fluid Types — Newtonian and Non-Newtonian
created: 2026-05-02
modified: 2026-05-04T06:19:02.766+05:30
tags:
  - FluidMechanics
  - FluidProperties
  - atomic
  - rheology
  - needs-verification
cssclasses: ""
---


# Fluid Types — Newtonian and Non-Newtonian

**A Newtonian fluid obeys Newton's law of viscosity exactly — shear stress is linearly proportional to velocity gradient with a constant μ; non-Newtonian fluids deviate from this linear relationship in various characteristic ways.**

> [!caution] Low Confidence
> The source material (FM_Notes.pdf) contains a slide titled "Types of Fluids" but the actual
> rheological classification content is absent — the slide text is a repeat of viscosity content.
> The content below is drawn from well-established general fluid mechanics knowledge (consistent
> with Cengel & Cimbala, R.K. Bansal). Verify against your course textbook before using in
> assessment answers.

---

## Newtonian Fluids

A **Newtonian fluid** is one for which the shear stress–velocity gradient relationship is:
1. **Linear**: $\tau \propto du/dy$
2. **Passes through the origin**: zero stress at zero strain rate
3. **Constant slope**: the dynamic viscosity μ is independent of strain rate

$$\tau = \mu \frac{du}{dy} \quad \text{(μ = constant)}$$

On a $\tau$ vs $du/dy$ plot, a Newtonian fluid gives a **straight line through the origin**
with slope μ.

**Common Newtonian fluids**: water, air, most gases, light oils, petrol, alcohol, glycerin
(approximately), mercury.

For all derivations in this course — continuity, Bernoulli, Hagen-Poiseuille, Darcy-Weisbach
— the Newtonian assumption is explicitly or implicitly required.

---

## Non-Newtonian Fluids

Non-Newtonian fluids do not obey Newton's law in its simple form — μ is not constant but
instead depends on the strain rate $du/dy$, time, or the history of deformation.

### Classification by Shear Behaviour

#### 1. Pseudo-plastic (Shear-thinning)
- Apparent viscosity **decreases** as shear rate increases
- The faster you shear them, the more easily they flow
- **Examples**: blood, polymer solutions, paints, ketchup, nail polish, yoghurt
- **Model**: Power law with $n < 1$: $\tau = K (du/dy)^n$

#### 2. Dilatant (Shear-thickening)
- Apparent viscosity **increases** as shear rate increases
- The faster you shear them, the more they resist
- **Examples**: cornstarch in water (oobleck), wet sand, some concentrated suspensions
- **Model**: Power law with $n > 1$: $\tau = K (du/dy)^n$

#### 3. Bingham Plastic
- Behaves as a **rigid solid** below a yield stress $\tau_0$
- Above $\tau_0$, behaves as a Newtonian fluid
- **Examples**: toothpaste, mayonnaise, drilling mud, fresh concrete, some greases
- **Model**: $\tau = \tau_0 + \mu_B (du/dy)$ for $\tau > \tau_0$

#### 4. Thixotropic
- Viscosity **decreases with time** at constant shear rate (structure breaks down)
- **Examples**: certain gels, thixotropic paints
- Behaviour is time-dependent, not just rate-dependent

#### 5. Rheopectic
- Viscosity **increases with time** at constant shear rate (structure builds up)
- Rare in practice

---

## Graphical Comparison

On a $\tau$ vs $du/dy$ (shear stress vs strain rate) plot:

```
    τ
    │                        /  Dilatant (n>1)
    │                      /
    │                    /   ←  Newtonian (linear, slope = μ)
    │                  /  /
    │               / /
    │  Bingham  →  /    ← Pseudo-plastic (n<1)
    │         ___/
    │  ______/
    │ τ₀
    └─────────────────────────── du/dy
```

| Fluid type | $\tau$ vs $du/dy$ | μ_apparent |
|---|---|---|
| Newtonian | Straight line through origin | Constant |
| Pseudo-plastic | Curve, slope decreasing | Decreases with shear rate |
| Dilatant | Curve, slope increasing | Increases with shear rate |
| Bingham plastic | Straight line offset by $\tau_0$ | Constant above yield stress |

---

## Engineering Significance

The Newtonian assumption is built into every formula in this course. When a fluid is
non-Newtonian:

- The Hagen-Poiseuille equation **does not apply** without modification
- The friction factor in the Darcy-Weisbach equation must be recalculated using a
  generalised Reynolds number
- Pump sizing becomes more complex (especially for Bingham plastics)
- Pipeline design for food, pharmaceutical, and polymer industries frequently involves
  non-Newtonian fluids

> [!tip] For This Course
> Unless explicitly stated otherwise, **assume all fluids are Newtonian**. The exam
> will not ask you to solve non-Newtonian flow problems quantitatively, but may ask
> you to identify or describe the types.

---

## Connections to Other Notes

- Newton's law of viscosity (defines Newtonian behaviour): [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/08_DynamicViscosity_NewtonsLaw]]
- Temperature effects on apparent viscosity: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/11_Viscosity_TemperaturePressure]]
- Hagen-Poiseuille — derived assuming Newtonian fluid: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/18_LaminarFlow_HagenPoiseuille]]

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01b_FluidProperties_Hub]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/02b_FluidProperties_MOC]],
[[Other Notes/EHT/Testing_something_out/Fluid Mechanics/08_DynamicViscosity_NewtonsLaw]]
*Links to:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/08_DynamicViscosity_NewtonsLaw]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/11_Viscosity_TemperaturePressure]],
[[Other Notes/EHT/Testing_something_out/Fluid Mechanics/18_LaminarFlow_HagenPoiseuille]]
