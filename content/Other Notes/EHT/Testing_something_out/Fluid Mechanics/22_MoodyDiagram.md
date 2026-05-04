---
publish: true
title: The Moody Diagram
created: 2026-05-02
modified: 2026-05-04T06:19:39.066+05:30
tags:
  - FluidMechanics
  - PipeFlow
  - atomic
  - friction-factor
  - Moody
  - needs-verification
cssclasses: ""
---


# The Moody Diagram

**The Moody diagram is a log-log plot of the Darcy friction factor (fD) against Reynolds number (Re), parameterised by relative pipe roughness (ε/d); it is the standard tool for finding the friction factor in turbulent pipe flow.**

> [!caution] Low Confidence
> The source provides the Moody diagram image (p. 74) but minimal explanatory text.
> The interpretation and use of the Moody diagram described below is well-established
> general knowledge from standard fluid mechanics textbooks. Verify quantitative
> correlations against your course materials.

---

## Definition

The **Moody diagram** (developed by Lewis Moody in 1944) graphically presents the
relationship between the friction factor, Reynolds number, and pipe roughness for fully
developed flow in circular pipes. It consolidates experimental data from many sources
into a single chart that covers all flow regimes.

**Axes:**
- **x-axis**: Reynolds number $Re$ (log scale, from ~600 to 10⁸)
- **y-axis**: Darcy friction factor $f_D$ (log scale, from ~0.008 to 0.1)
- **Parameter lines**: Relative roughness $\varepsilon/d$ (right axis, from ~$10^{-6}$ to 0.05)

> [!warning] Friction Factor Convention
> The Moody diagram plots the **Darcy friction factor** $f_D$, where for laminar flow
> $f_D = 64/Re$. The source notes use the **Fanning friction factor** $f = 16/Re$ with
> the formula $h_f = 4fLV^2/(d \cdot 2g)$.
> **These give identical head losses**: $f_D \times 1 = 4f_{Fanning} \times 4$... wait:
> $h_f = f_D \frac{LV^2}{d \cdot 2g} = 4f \frac{LV^2}{d \cdot 2g}$ requires $f_D = 4f$.
> So $f_D = 4 \times f_{Fanning}$. If reading $f$ from Moody, use without the factor 4.

---

## Four Regions on the Moody Diagram

### Region 1 — Laminar Flow ($Re < 2000$)

A single straight line on the log-log plot with slope −1:

$$f_D = \frac{64}{Re}$$

This is exact — independent of pipe roughness (because the viscous sublayer completely
covers the roughness elements and they have no effect on friction).

### Region 2 — Critical / Transitional Zone ($2000 < Re < 4000$)

The shaded zone where no reliable prediction is possible. The Moody diagram shows a
gap here. Flow is unstable and friction factor is indeterminate. **Avoid designing
systems to operate here.**

### Region 3 — Turbulent Flow, Smooth Pipe ($Re > 4000$, $\varepsilon/d \to 0$)

The lowest curve on the diagram. For smooth pipes, roughness is irrelevant and the
friction factor depends only on Re. The Blasius correlation applies for $Re < 10^5$:

$$f_D = \frac{0.316}{Re^{0.25}}$$

(Note: this is the Darcy form — the source's Fanning form is $f = 0.079/Re^{0.25}$,
which is $f_D/4$.)

### Region 4 — Turbulent Flow, Rough Pipe (Complete Turbulence)

At high Re and significant roughness, the friction factor becomes independent of Re
and depends only on $\varepsilon/d$. The curves on the Moody diagram flatten out
(become horizontal). This is the **fully rough** or **complete turbulence** regime:

$$f_D = \frac{1}{\left[2\log_{10}\left(\frac{d}{\varepsilon}\right) + 1.14\right]^2}$$

(Nikuradse rough-pipe formula)

---

## Pipe Roughness Values

Absolute roughness $\varepsilon$ for common pipe materials (from Moody diagram legend):

| Material | $\varepsilon$ (mm) |
|---|---|
| Drawn tubing | 0.0025 |
| Commercial steel | 0.046 |
| Wrought iron | 0.046 |
| Asphalted cast iron | 0.12 |
| Galvanised iron | 0.15 |
| Cast iron | 0.26 |
| Concrete (smooth) | 0.3–3.0 |
| Sewers (old) | 3.0 |

Relative roughness: $\varepsilon/d$ — use this ratio on the Moody diagram.

---

## How to Use the Moody Diagram

**Given**: Re and $\varepsilon/d$ → **Find**: $f_D$

1. Calculate $Re = Vd/\nu$
2. Calculate $\varepsilon/d$ (look up $\varepsilon$ from table; divide by pipe diameter)
3. Enter the Moody diagram at the calculated Re on the x-axis
4. Move vertically until you intersect the curve for the appropriate $\varepsilon/d$ value
5. Read $f_D$ off the y-axis
6. Compute head loss: $h_f = f_D \cdot LV^2/(d \cdot 2g)$

> [!tip] Colebrook-White Equation (Implicit Alternative)
> The Colebrook-White equation is the mathematical representation of the Moody diagram:
> $$\frac{1}{\sqrt{f_D}} = -2\log_{10}\left(\frac{\varepsilon/d}{3.7} + \frac{2.51}{Re\sqrt{f_D}}\right)$$
> This is implicit in $f_D$ and requires iteration. The Swamee-Jain explicit approximation
> is often used in practice.

---

## Why It Matters

The Moody diagram is the indispensable reference for:
- Finding the turbulent friction factor for any Re and pipe material
- Confirming the laminar friction factor (left edge of diagram)
- Understanding how roughness affects friction at high Re
- Transitioning from smooth-pipe to fully-rough behaviour as velocity increases

---

## Connections to Other Notes

- Reynolds number (x-axis of Moody diagram): [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/14_ReynoldsNumber]]
- Darcy-Weisbach uses f from Moody diagram: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/20_MajorLosses_DarcyWeisbach]]
- Friction factor source for pipes in series/parallel: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/24_PipesInSeries]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/25_PipesInParallel]]

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01c_PipeFlow_Hub]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/02c_PipeFlow_MOC]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/20_MajorLosses_DarcyWeisbach]]
*Links to:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/14_ReynoldsNumber]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/20_MajorLosses_DarcyWeisbach]],
[[Other Notes/EHT/Testing_something_out/Fluid Mechanics/24_PipesInSeries]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/25_PipesInParallel]]
