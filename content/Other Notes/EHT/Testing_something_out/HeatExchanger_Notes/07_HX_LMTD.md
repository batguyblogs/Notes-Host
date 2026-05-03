---
publish: true
title: Logarithmic Mean Temperature Difference (LMTD)
created: 2026-05-03T10:20:50.458+05:30
modified: 2026-05-03T10:39:09.677+05:30
tags:
  - heat-exchanger
  - MTE3252
  - LMTD
  - atomic
cssclasses: ""
---


# Logarithmic Mean Temperature Difference (LMTD)

**The LMTD is the appropriate average temperature difference between the hot and cold fluids to use in the heat exchanger design equation $Q = UA\Delta T_m$, accounting for the fact that the local temperature difference varies continuously along the exchanger length.**

---

## Definition

In a heat exchanger, the temperature difference between hot and cold fluids is not constant — it varies from one end to the other. Using a simple arithmetic average of the two endpoint differences would overestimate the true driving force. The correct average is the logarithmic mean:

$$\boxed{\Delta T_m = \frac{\Delta T_1 - \Delta T_2}{\ln\left(\dfrac{\Delta T_1}{\Delta T_2}\right)}}$$

Where $\Delta T_1$ and $\Delta T_2$ are the temperature differences at the **two ends** of the exchanger (defined differently for parallel and counter flow — see below).

---

## Mechanism / How It Works

### Master Heat Transfer Equation

$$Q = UA\Delta T_m$$

Where:
- $Q$ = total heat transfer rate (W)
- $U$ = overall heat transfer coefficient (W/m²·°C) — see [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/09_HX_OverallHTC_PlaneWall]]
- $A$ = effective heat transfer area (m²)
- $\Delta T_m$ = LMTD (°C)

### Why Not Arithmetic Mean?

The local heat flux $dQ = U \cdot dA \cdot (T_h - T_c)$ varies along the length because $T_h$ and $T_c$ both change. Integrating this over the full area (which requires differential analysis) yields the logarithmic mean — not the arithmetic mean. The arithmetic mean overestimates the true driving force, leading to under-sized exchangers.

> [!caution] Low Confidence
> The full differential derivation of the LMTD formula from first principles (integrating over a differential element $dA$) is not provided in the lecture slides. The result is presented here. If the derivation is examinable, consult Cengel & Ghajar Chapter 11 or equivalent primary textbook.

---

## Key Details

### Parallel Flow — Definition of $\Delta T_1$ and $\Delta T_2$

Both fluids enter at the same end:

$$\Delta T_1 = T_{h1} - T_{c1} \quad \text{(inlet end — both fluids enter here)}$$
$$\Delta T_2 = T_{h2} - T_{c2} \quad \text{(outlet end — both fluids exit here)}$$

```
Th1 ─────────────────────────► Th2
     ΔT₁↑                   ↑ΔT₂
Tc1 ─────────────────────────► Tc2
```

### Counter Flow — Definition of $\Delta T_1$ and $\Delta T_2$

Fluids enter at opposite ends:

$$\Delta T_1 = T_{h1} - T_{c2} \quad \text{(hot-inlet / cold-outlet end)}$$
$$\Delta T_2 = T_{h2} - T_{c1} \quad \text{(hot-outlet / cold-inlet end)}$$

```
Th1 ─────────────────────────► Th2
     ΔT₁↑                   ↑ΔT₂
Tc2 ◄───────────────────────── Tc1
```

> [!warning] Critical Exam Point
> This is the most common source of error. In **parallel flow**, $\Delta T_1 = T_{h1}-T_{c1}$ (both subscripts 1). In **counter flow**, $\Delta T_1 = T_{h1}-T_{c2}$ (subscripts cross). Always draw the configuration before writing these down.

### Special Case: $\Delta T_1 = \Delta T_2$

If both endpoint differences are equal, the formula gives $0/0$ (indeterminate). In this case, $\Delta T_m = \Delta T_1 = \Delta T_2$ (the arithmetic mean equals the log mean when differences are equal).

### Counter Flow Always Gives Larger LMTD

For the same four terminal temperatures, counter-flow always produces a larger $\Delta T_m$ than parallel flow. This means for the same $Q$ and $U$, a counter-flow exchanger needs **less area** — it is always the more thermally efficient choice.

---

## Why It Matters

The LMTD is the essential link between the energy balance (which gives $Q$ and temperatures) and the design equation (which determines area $A$). It cannot be skipped or approximated as arithmetic mean without introducing significant error.

> [!example] Quick Numerical Check
> Suppose $\Delta T_1 = 60°C$ and $\Delta T_2 = 20°C$.
> - Arithmetic mean: $(60+20)/2 = 40°C$
> - LMTD: $(60-20)/\ln(60/20) = 40/\ln(3) = 40/1.099 = \mathbf{36.4°C}$
> The arithmetic mean overestimates by ~10% here. For larger ratios the error grows further.

---

## Connections to Other Notes

The flow arrangement (parallel vs counter) from [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/03_HX_FlowArrangements]] determines which form of $\Delta T_1$ and $\Delta T_2$ to use. The full worked procedure applying LMTD is shown in [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/08_HX_LMTD_WorkedExamples]]. The overall heat transfer coefficient $U$ needed in $Q = UA\Delta T_m$ is derived in [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/09_HX_OverallHTC_PlaneWall]] and [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/10_HX_OverallHTC_Cylindrical]]. When LMTD becomes iterative (outlet temperatures unknown), the NTU method in [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/14_HX_NTU_Effectiveness]] is used instead.

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/00_HeatExchanger_Hub]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/01_HeatExchanger_MOC]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/06_HX_EnergyBalance]]
*Links to:* [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/03_HX_FlowArrangements]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/08_HX_LMTD_WorkedExamples]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/09_HX_OverallHTC_PlaneWall]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/13_HX_LMTD_vs_NTU]]
