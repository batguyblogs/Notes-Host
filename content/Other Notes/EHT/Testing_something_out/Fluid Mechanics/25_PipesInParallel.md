---
publish: true
title: Flow Through Pipes in Parallel
created: 2026-05-02
modified: 2026-05-04T06:19:50.204+05:30
tags:
  - FluidMechanics
  - PipeFlow
  - atomic
  - pipe-networks
  - parallel
cssclasses: ""
---


# Flow Through Pipes in Parallel

**Pipes in parallel share the same head loss across each branch; the total flow rate is the sum of individual branch flows: Q = Q₁ + Q₂. Given total Q and pipe properties, the branch velocities are found using the equal head loss condition.**

---

## Definition

**Pipes in parallel** exist when a main pipe divides into two or more branches that
reconnect downstream. Each branch connects the same two junction nodes (A and B), so
they experience identical pressure conditions at both ends.

```
                        Pipe 1: D₁, L₁, f₁
               ╔══════════════════════════════════╗
               ║              Q₁ →                ║
Main → Q ═════╣ A                                B ╠═════ Q → Main
               ║              Q₂ →                ║
               ╚══════════════════════════════════╝
                        Pipe 2: D₂, L₂, f₂
```

---

## Governing Conditions

### Condition 1 — Equal Head Loss

Since both branches connect the same two nodes (A and B), the head loss in each
branch must be **identical**:

$$\boxed{h_{f_1} = h_{f_2}}$$

$$\frac{4f_1 L_1 V_1^2}{D_1 \cdot 2g} = \frac{4f_2 L_2 V_2^2}{D_2 \cdot 2g}$$

### Condition 2 — Total Flow (Continuity)

The total flow splits between the branches, so the sum of branch flows equals the
main flow:

$$\boxed{Q = Q_1 + Q_2}$$

$$A_1 V_1 + A_2 V_2 = Q$$

---

## Solution Strategy

**Given total Q (and pipe properties), find Q₁ and Q₂:**

1. From the equal head loss condition, express $V_1$ in terms of $V_2$ (or vice versa)
2. Express $Q_1$ and $Q_2$ in terms of the same unknown velocity
3. Apply the total flow condition $Q_1 + Q_2 = Q$
4. Solve for the unknown velocity, then find both Q values

**If $f_1 = f_2 = f$**, the equal head loss condition simplifies to:

$$\frac{L_1 V_1^2}{D_1} = \frac{L_2 V_2^2}{D_2}$$

$$V_1^2 = \frac{L_2 D_1}{L_1 D_2} V_2^2 \implies V_1 = V_2 \sqrt{\frac{L_2 D_1}{L_1 D_2}}$$

---

## Worked Example (Q11 from source)

> [!example]
> Pipe 1: D₁ = 1.0 m, L₁ = 2000 m
> Pipe 2: D₂ = 0.8 m, L₂ = 2000 m
> f₁ = f₂ = f = 0.005, Total Q = 3.0 m³/s
>
> **Step 1 — Equal head loss** (f₁ = f₂, L₁ = L₂ = 2000):
> $\frac{V_1^2}{D_1} = \frac{V_2^2}{D_2} \implies \frac{V_1^2}{1.0} = \frac{V_2^2}{0.8}$
> $V_1^2 = \frac{V_2^2}{0.8} \implies V_1 = \frac{V_2}{\sqrt{0.8}} = \frac{V_2}{0.894}$
>
> **Step 2 — Individual discharges:**
> $Q_1 = \frac{\pi}{4}(1.0)^2 V_1 = \frac{\pi V_2}{4 \times 0.894}$
> $Q_2 = \frac{\pi}{4}(0.8)^2 V_2 = \frac{\pi \times 0.64 V_2}{4}$
>
> **Step 3 — Apply Q₁ + Q₂ = 3.0:**
> $\frac{\pi V_2}{4}(1/0.894 + 0.64) = 3.0$
> $\frac{\pi V_2}{4}(1.118 + 0.64) = 3.0$
> $\frac{\pi V_2 \times 1.758}{4} = 3.0$
> $V_2 = \frac{3.0 \times 4}{\pi \times 1.758} = 2.17$ m/s
>
> **Step 4 — Find V₁ and Q values:**
> $V_1 = 2.17/0.894 = 2.427$ m/s
> $Q_1 = \frac{\pi}{4}(1.0)^2 \times 2.427 = \mathbf{1.906}$ **m³/s**
> $Q_2 = 3.0 - 1.906 = \mathbf{1.094}$ **m³/s**
>
> **Verification**: $h_{f_1} = 4 \times 0.005 \times 2000 \times 2.427^2/(1.0 \times 2 \times 9.81) = 12.01$ m
> $h_{f_2} = 4 \times 0.005 \times 2000 \times 2.17^2/(0.8 \times 2 \times 9.81) = 12.01$ m ✓

---

## Comparison: Series vs Parallel

| Feature | Pipes in Series | Pipes in Parallel |
|---|---|---|
| Governing condition | Same Q | Same $h_f$ |
| Head loss | Additive: $H = \Sigma h_f$ | Equal: $h_{f_1} = h_{f_2}$ |
| Flow rate | Single Q throughout | $Q = Q_1 + Q_2$ |
| Purpose | Increase pressure capacity | Increase flow capacity |
| Design use | Long-distance transmission | Flow augmentation |

> [!tip] Engineering Insight
> Connecting pipes in parallel **increases the flow capacity** of a system for the same
> head loss — the same reason electrical conductors in parallel have lower resistance.
> Pipes in series **increase the head loss** for the same flow rate — analogous to
> resistors in series.

---

## Why It Matters

Parallel pipe analysis is essential for:
- Distribution networks (water supply systems with multiple mains)
- Bypass systems (flow splits around a pump or piece of equipment)
- Ring mains in buildings and industrial facilities
- Increasing flow capacity of an existing system without replacing the main

---

## Connections to Other Notes

- Continuity equation (Q = Q₁ + Q₂): [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/15_ContinuityEquation]]
- Darcy-Weisbach (used to enforce equal head loss condition): [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/20_MajorLosses_DarcyWeisbach]]
- Series pipes (the contrasting case): [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/24_PipesInSeries]]

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01c_PipeFlow_Hub]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/02c_PipeFlow_MOC]]
*Links to:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/15_ContinuityEquation]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/20_MajorLosses_DarcyWeisbach]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/24_PipesInSeries]]
