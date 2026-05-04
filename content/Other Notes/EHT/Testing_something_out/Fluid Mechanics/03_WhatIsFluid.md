---
publish: true
title: What Is a Fluid
created: 2026-05-02
modified: 2026-05-04T06:18:31.778+05:30
tags:
  - FluidMechanics
  - FluidFundamentals
  - atomic
  - definition
cssclasses: ""
---


# What Is a Fluid

**A fluid is any substance that deforms continuously and without limit under the action of a shear (tangential) stress, no matter how small that stress may be, and cannot sustain a shear stress when at rest.**

---

## Definition

Matter exists in three primary phases: solid, liquid, and gas. A substance in the liquid or gas
phase is referred to as a **fluid**. The distinction between solids and fluids is not made on
the basis of hardness or rigidity in everyday terms, but on the basis of a specific mechanical
response to applied shear stress.

Two equivalent statements capture the definition completely:

1. *A fluid is a substance capable of flowing.*
2. *A fluid is a substance that deforms continuously under the application of a shear (tangential) stress, no matter how small the shear stress may be.*

The second statement is more physically precise. The word "continuously" is the critical term
— it means the deformation never stops while the stress is applied, which is fundamentally
different from a solid's bounded elastic deformation.

> [!note] The Two-Part Definition
> The full definition has both a positive and a negative component:
> - **Positive**: A fluid deforms *continuously* under shear stress (no matter how small)
> - **Negative**: A fluid *cannot sustain* shear stress when at rest
> Both parts are required. Together they uniquely distinguish fluids from all solid materials.

---

## Mechanism — How It Works

The key to understanding fluid behaviour lies in comparing the stress-deformation relationship
for solids and fluids:

| Property | Solid | Fluid |
|---|---|---|
| Response to shear | Deforms to a *fixed* strain angle | Deforms *continuously* (strain rate) |
| Stress proportional to | Strain $\alpha$ | Strain **rate** $du/dy$ |
| Behaviour after load removal | Returns to original shape (elastic) | Continues in deformed state |
| Shear stress at rest | Can sustain | Cannot sustain |

For a **solid**: $\tau \propto \alpha$ (shear stress is proportional to shear strain)

For a **fluid**: $\tau \propto \frac{du}{dy}$ (shear stress is proportional to the *rate* of shear strain)

This difference in constitutive behaviour is what separates the two categories at a
fundamental level. See [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/05_SolidVsFluid_ShearStress]] for the plate analogy that makes
this concrete.

---

## Key Details

### Why "no matter how small"?

This clause is essential. A very viscous fluid like honey might *seem* to resist flow, but
given *any* nonzero shear stress and sufficient time, it will deform continuously. The clause
distinguishes fluids from Bingham plastics (which require a minimum yield stress before
flowing) — though Bingham materials occupy a middle ground. For this course, all fluids are
assumed to flow under any shear stress.

### Liquids vs Gases

Both liquids and gases are fluids, but they differ in compressibility and intermolecular
spacing:

- **Liquids**: Nearly incompressible; definite volume; molecules closely packed with strong
  cohesive forces
- **Gases**: Highly compressible; no definite volume; molecules far apart with weak
  intermolecular forces

For this course, most flows are treated as **incompressible** — an assumption valid for
liquids and for gases at low speeds (Mach number < ~0.3).

> [!warning] Common Misconception
> A fluid at rest appears to "sustain" its shape in a container — this seems to contradict
> the definition. The resolution: a fluid at rest is in **hydrostatic equilibrium** under
> normal (compressive/tensile) stresses only. There is zero *shear* stress in a static
> fluid. The container walls provide the normal force; no shear is present.

---

## Why It Matters

This definition is not just academic — it sets the boundary of validity for every equation
in the course:

- The **continuity equation** assumes the material is a fluid (continuous deformation)
- **Newton's law of viscosity** $\tau = \mu \, du/dy$ applies only to Newtonian fluids
  (a subset of fluids) — see [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/08_DynamicViscosity_NewtonsLaw]]
- **Bernoulli's equation** is derived for ideal (inviscid) fluids — the definition tells us
  real fluids always have viscosity and will lose energy
- The **no-slip condition** at walls (u = 0) follows directly from the fact that a fluid
  cannot resist the shear imposed by a stationary wall

> [!tip] Exam Application
> When asked "define a fluid," give both parts: (1) continuous deformation under any shear
> stress, (2) cannot sustain shear at rest. One sentence is not enough — examiners look for
> both the positive and negative conditions.

---

## Connections to Other Notes

- The plate-rubber analogy that makes this definition tangible: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/05_SolidVsFluid_ShearStress]]
- The constitutive law that quantifies the shear stress–strain rate relationship: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/08_DynamicViscosity_NewtonsLaw]]
- The sub-disciplines built on this definition: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/04_FM_Subcategories]]
- The flow regime classification that begins the engineering application: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/13_LaminarVsTurbulent_Flow]]

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01a_FluidFundamentals_Hub]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/02a_FluidFundamentals_MOC]]
*Links to:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/05_SolidVsFluid_ShearStress]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/08_DynamicViscosity_NewtonsLaw]],
[[Other Notes/EHT/Testing_something_out/Fluid Mechanics/04_FM_Subcategories]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/13_LaminarVsTurbulent_Flow]]
