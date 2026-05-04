---
publish: true
title: Major Losses — Darcy-Weisbach Equation
created: 2026-05-02
modified: 2026-05-04T06:19:32.681+05:30
tags:
  - FluidMechanics
  - PipeFlow
  - atomic
  - head-loss
  - friction
  - Darcy-Weisbach
cssclasses: ""
---


# Major Losses — Darcy-Weisbach Equation

**Major head loss due to pipe wall friction is calculated using the Darcy-Weisbach equation: hf = 4fLV²/(d·2g), where f is the friction factor determined from the Reynolds number (laminar) or the Moody diagram (turbulent).**

---

## Definition

When a fluid flows through a pipe, viscous friction between the fluid and the pipe wall
continuously dissipates mechanical energy into heat. This energy loss is called the
**major loss** because it typically dominates over minor (local) losses in long pipes.

The **Darcy-Weisbach equation** quantifies this loss as a head (metres of fluid):

$$\boxed{h_f = \frac{4fLV^2}{d \times 2g}}$$

where:
- $h_f$ = head loss due to friction (m)
- $f$ = coefficient of friction (dimensionless) — function of Reynolds number
- $L$ = pipe length (m)
- $V$ = mean flow velocity (m/s)
- $d$ = pipe diameter (m)
- $g$ = gravitational acceleration = 9.81 m/s²

---

## The Friction Factor f

The friction factor $f$ used here is the **Fanning friction factor**. Its value depends
on the flow regime:

### Laminar Flow ($Re < 2000$) — Analytical Result

$$f = \frac{16}{Re}$$

This result is exact and derives directly from the Hagen-Poiseuille analysis.
See [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/18_LaminarFlow_HagenPoiseuille]] for the connection.

### Turbulent Flow ($4000 < Re < 10^6$) — Empirical

$$f = \frac{0.079}{Re^{1/4}}$$

This is the **Blasius correlation** for smooth pipes, valid for $4000 < Re < 10^6$.

> [!warning] Fanning vs Darcy Friction Factor
> The source uses the formula $h_f = 4fLV^2/(d \cdot 2g)$ with $f = 16/Re$ for laminar
> flow. The Moody diagram (p. 74 of the source) plots the **Darcy-Weisbach friction factor**
> $f_D = 64/Re$ for laminar flow using the formula $h_f = f_D LV^2/(d \cdot 2g)$ (no
> factor of 4).
>
> **These are equivalent**: $4 \times f_{Fanning} = f_{Darcy}$, i.e. $4 \times 16/Re = 64/Re$.
>
> The Moody diagram shows $f_D$ (Darcy). If reading $f$ from Moody, use:
> $$h_f = \frac{f_D L V^2}{d \times 2g} \quad \text{(Darcy form, no factor of 4)}$$
> If using $f = 16/Re$ or $f = 0.079/Re^{0.25}$, use:
> $$h_f = \frac{4f L V^2}{d \times 2g} \quad \text{(Fanning form, factor of 4 present)}$$

---

## Key Observations

### Dependence on Pipe Diameter

$$h_f \propto \frac{1}{d} \quad (\text{at constant } V)$$

Halving the diameter doubles the friction head loss. However, if Q (not V) is kept
constant, then $V \propto 1/d^2$, making $h_f \propto V^2/d \propto 1/d^5$ — a very
strong diameter dependence.

### Head Loss as Pressure Drop

$$\Delta p = \rho g h_f = \frac{4f \rho L V^2}{2d}$$

### Pumping Power

The power required to overcome friction losses:

$$P = \rho g Q h_f \quad [\text{W}]$$

or equivalently:

$$P = \frac{\rho g Q h_f}{1000} \quad [\text{kW}]$$

---

## Worked Examples

> [!example] Example 1 — Laminar Flow (Q1 from source)
> Crude oil: μ = 0.097 Pa·s, ρ = 900 kg/m³, D = 0.1 m, L = 10 m, $\bar{u}$ = 0.471 m/s
>
> Step 1 — Reynolds number: $Re = 900 \times 0.471 \times 0.1 / 0.097 = 436.9$
>
> Step 2 — Friction factor: $f = 16/Re = 16/436.9 = 0.0366$
>
> Step 3 — Head loss:
> $h_f = \frac{4 \times 0.0366 \times 10 \times 0.471^2}{0.1 \times 2 \times 9.81} = \frac{0.325}{1.962} = 0.166$ m
>
> Cross-check with Hagen-Poiseuille: $\Delta p = 32 \times 0.097 \times 0.471 \times 10 / 0.1^2 = 1462$ Pa
> $h_f = \Delta p / (\rho g) = 1462/(900 \times 9.81) = 0.166$ m ✓ (both give the same answer)

> [!example] Example 2 — Turbulent Flow (Q4 from source)
> Water: ν = 0.01 stoke = $10^{-6}$ m²/s, D = 0.3 m, L = 50 m, V = 3 m/s
>
> Step 1 — Reynolds number: $Re = 3 \times 0.3 / 10^{-6} = 9 \times 10^5$
>
> Step 2 — Friction factor (turbulent): $f = 0.079 / Re^{0.25} = 0.079 / (9 \times 10^5)^{0.25} = 0.00256$
>
> Step 3 — Head loss:
> $h_f = \frac{4 \times 0.00256 \times 50 \times 9}{0.3 \times 19.62} = \frac{4.608}{5.886} = 0.783$ m

> [!example] Example 3 — Power Required (Q6 from source)
> Oil: SG = 0.7, ν = 0.29 stoke, D = 0.3 m, Q = 0.5 m³/s, L = 1000 m
>
> $V = Q/A = 0.5/(\pi \times 0.09/4) = 7.07$ m/s
> $Re = 7.07 \times 0.3/(0.29 \times 10^{-4}) = 7.32 \times 10^4$, turbulent
> $f = 0.079/(7.32 \times 10^4)^{0.25} = 0.0048$
> $h_f = 4 \times 0.0048 \times 1000 \times 7.07^2 / (0.3 \times 19.62) = 163.2$ m
> $P = \rho g Q h_f = 700 \times 9.81 \times 0.5 \times 163.2 / 1000 = 560.3$ kW

---

## Problem-Solving Procedure

1. **Convert units**: μ (Poise → Pa·s ÷10), Q (l/s → m³/s ×10⁻³), d (mm → m ÷1000)
2. **Find velocity**: $V = Q/A = 4Q/(\pi d^2)$
3. **Calculate Re**: $Re = \rho V d/\mu$ or $Vd/\nu$
4. **Determine f**: $f = 16/Re$ (laminar) or $f = 0.079/Re^{0.25}$ (turbulent)
5. **Apply Darcy-Weisbach**: $h_f = 4fLV^2/(d \cdot 2g)$
6. **Power if required**: $P = \rho g Q h_f$

---

## Connections to Other Notes

- Reynolds number used to find f: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/14_ReynoldsNumber]]
- Hagen-Poiseuille is equivalent for laminar flow: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/18_LaminarFlow_HagenPoiseuille]]
- Moody diagram for turbulent and rough-pipe f: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/22_MoodyDiagram]]
- hf is the hL term in modified Bernoulli: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/17_BernoulliRealFluid]]
- Used in series and parallel pipe calculations: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/24_PipesInSeries]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/25_PipesInParallel]]

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01c_PipeFlow_Hub]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/02c_PipeFlow_MOC]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/17_BernoulliRealFluid]]
*Links to:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/14_ReynoldsNumber]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/18_LaminarFlow_HagenPoiseuille]],
[[Other Notes/EHT/Testing_something_out/Fluid Mechanics/22_MoodyDiagram]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/24_PipesInSeries]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/25_PipesInParallel]]
