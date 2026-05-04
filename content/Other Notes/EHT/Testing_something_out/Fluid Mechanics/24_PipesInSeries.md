---
publish: true
title: Flow Through Pipes in Series (Compound Pipes)
created: 2026-05-02
modified: 2026-05-04T06:19:45.338+05:30
tags:
  - FluidMechanics
  - PipeFlow
  - atomic
  - pipe-networks
  - series
cssclasses: ""
---


# Flow Through Pipes in Series (Compound Pipes)

**Pipes in series carry the same flow rate throughout; the total head loss equals the sum of losses in all pipes and fittings: H = Σhf + Σhm. Given the head difference H between two reservoirs, the common flow rate Q can be found.**

---

## Definition

**Pipes in series** (also called **compound pipes**) are pipes of different diameters
and lengths connected end-to-end to form a single flow path between two points (typically
two reservoirs at different elevations).

```
Reservoir A                                              Reservoir B
──────────────────────────────────────────────────────────────────
   ╔══════╗  pipe 1   ╔══════╗  pipe 2   ╔══════╗  pipe 3
   ║      ╠──────────╢      ╠──────────╢      ╠──────────╢      ║
   ║  A   ║D₁,L₁,f₁  ║      ║D₂,L₂,f₂  ║      ║D₃,L₃,f₃  ║  B  ║
   ║      ╠──────────╢      ╠──────────╢      ╠──────────╢      ║
   ╚══════╝           ╚══════╝           ╚══════╝           ╚══════╝
          V₁                  V₂                  V₃
             H (difference in water level)
```

---

## Governing Conditions

### Condition 1 — Continuity (Same Q)

The volumetric flow rate is the same throughout all pipes in series:

$$\boxed{Q = A_1 V_1 = A_2 V_2 = A_3 V_3}$$

This means velocities differ between pipes:

$$V_2 = V_1 \frac{A_1}{A_2} = V_1 \left(\frac{D_1}{D_2}\right)^2, \quad V_3 = V_1 \left(\frac{D_1}{D_3}\right)^2$$

### Condition 2 — Head Loss (Additive)

The total head difference $H$ between the two reservoirs equals the sum of all losses:

$$\boxed{H = \sum h_f + \sum h_m}$$

---

## Full Head Loss Equation

Including all major and minor losses for a three-pipe system:

$$H = h_i + h_{f_1} + h_c + h_{f_2} + h_e + h_{f_3} + h_o$$

where:

| Term | Description | Formula |
|---|---|---|
| $h_i$ | Entrance loss | $0.5 V_1^2/2g$ |
| $h_{f_1}$ | Friction in pipe 1 | $4f_1 L_1 V_1^2/(D_1 \cdot 2g)$ |
| $h_c$ | Contraction (pipe 1→2, if D₂ < D₁) | $0.5 V_2^2/2g$ |
| $h_{f_2}$ | Friction in pipe 2 | $4f_2 L_2 V_2^2/(D_2 \cdot 2g)$ |
| $h_e$ | Enlargement (pipe 2→3, if D₃ > D₂) | $(V_2-V_3)^2/2g$ |
| $h_{f_3}$ | Friction in pipe 3 | $4f_3 L_3 V_3^2/(D_3 \cdot 2g)$ |
| $h_o$ | Exit loss | $V_3^2/2g$ |

**If minor losses are neglected** (common for long pipes):

$$H = \frac{4f_1 L_1 V_1^2}{D_1 \cdot 2g} + \frac{4f_2 L_2 V_2^2}{D_2 \cdot 2g} + \frac{4f_3 L_3 V_3^2}{D_3 \cdot 2g}$$

If $f_1 = f_2 = f_3 = f$:

$$H = \frac{4f}{2g}\left[\frac{L_1 V_1^2}{D_1} + \frac{L_2 V_2^2}{D_2} + \frac{L_3 V_3^2}{D_3}\right]$$

---

## Solution Strategy

**Given H (and pipe properties), find Q:**

1. Express all velocities in terms of $V_1$ using continuity:
   $V_2 = V_1(D_1/D_2)^2$, $V_3 = V_1(D_1/D_3)^2$
2. Substitute into the head loss equation — every term becomes a multiple of $V_1^2/2g$
3. Collect: $H = C \cdot V_1^2/2g$ → solve for $V_1$
4. Compute $Q = A_1 V_1 = (\pi D_1^2/4) V_1$

> [!example] Worked Example (Q9 from source, neglecting minor losses)
> Pipe 1: D₁ = 0.3 m, L₁ = 450 m, f₁ = 0.0075
> Pipe 2: D₂ = 0.2 m, L₂ = 255 m, f₂ = 0.0078
> Pipe 3: D₃ = 0.4 m, L₃ = 315 m, f₃ = 0.0072
> H = 18 m
>
> Express V₂ and V₃ in terms of V₁:
> $V_2 = V_1(0.3/0.2)^2 = 2.25 V_1$
> $V_3 = V_1(0.3/0.4)^2 = 0.5625 V_1$
>
> Head loss equation (neglecting minor losses):
> $18 = \frac{V_1^2}{2g}\left[\frac{4 \times 0.0075 \times 450}{0.3} + \frac{4 \times 0.0078 \times 255 \times 2.25^2}{0.2} + \frac{4 \times 0.0072 \times 315 \times 0.5625^2}{0.4}\right]$
> $18 = \frac{V_1^2}{2 \times 9.81}[45 + 201.4 + 7.18] = 253.6 \frac{V_1^2}{19.62}$
>
> $V_1 = \sqrt{18 \times 19.62 / 253.6} = 1.18$ m/s
>
> $Q = (\pi/4)(0.3)^2 \times 1.18 = \mathbf{0.0834}$ **m³/s**

---

## When to Include Minor Losses

Compare major to minor loss magnitudes. A rough check: if $\sum k_i < 0.1 \times (4fL/d)$
for any pipe, minor losses can be neglected. For the worked example above, the minor
losses (entrance + contraction + enlargement + exit) changed Q from 0.0834 to 0.0824 m³/s
— about 1.2% difference — demonstrating that they were genuinely minor for these long pipes.

> [!tip] Exam Procedure
> When asked to solve "with minor losses" and "without minor losses," solve the simpler
> case first (without). This gives you a good estimate of V₁, which you can then use
> to verify your more complex answer. The two answers should differ by less than ~5%.

---

## Connections to Other Notes

- Continuity equation (same Q condition): [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/15_ContinuityEquation]]
- Darcy-Weisbach (friction losses in each pipe): [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/20_MajorLosses_DarcyWeisbach]]
- Minor losses (local losses at junctions): [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/21_MinorLosses]]
- Parallel pipes (contrasting governing conditions): [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/25_PipesInParallel]]
- Modified Bernoulli (the overall energy equation): [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/17_BernoulliRealFluid]]

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01c_PipeFlow_Hub]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/02c_PipeFlow_MOC]]
*Links to:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/15_ContinuityEquation]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/17_BernoulliRealFluid]],
[[Other Notes/EHT/Testing_something_out/Fluid Mechanics/20_MajorLosses_DarcyWeisbach]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/21_MinorLosses]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/25_PipesInParallel]]
