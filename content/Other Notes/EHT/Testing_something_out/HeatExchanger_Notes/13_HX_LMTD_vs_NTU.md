---
publish: true
title: LMTD vs NTU Method — When to Use Which
created: 2026-05-03T10:20:50.458+05:30
modified: 2026-05-03T10:45:29.303+05:30
tags:
  - heat-exchanger
  - MTE3252
  - LMTD
  - NTU
  - design-methods
  - atomic
cssclasses: ""
---


# LMTD vs NTU Method — When to Use Which

**The LMTD method is ideal for sizing (finding area when all temperatures are known), while the NTU–effectiveness method is ideal for rating (finding outlet temperatures when area and inlet conditions are known); using LMTD for rating problems requires tedious iteration that the NTU method eliminates entirely.**

---

## Definition

Two complementary analytical methods exist for heat exchanger analysis. They give identical answers but suit different problem types. Choosing the wrong method does not give a wrong answer — it just creates unnecessary work.

---

## Mechanism / How It Works

### The Two Problem Types

**Type 1 — Sizing (Design) Problem**
> "I know what I want the exchanger to do. How big must it be?"

Given: all four temperatures ($T_{h1}, T_{h2}, T_{c1}, T_{c2}$), both mass flow rates, and $U$.
Find: required heat transfer area $A$.

→ **Use LMTD method**

**Type 2 — Rating (Performance) Problem**
> "I already have an exchanger of size $A$. What will it actually do?"

Given: both inlet temperatures ($T_{h1}, T_{c1}$), both mass flow rates, $U$, and area $A$.
Find: outlet temperatures ($T_{h2}$ and $T_{c2}$) and actual $Q$.

→ **Use NTU method**

---

## LMTD Method — Full Procedure

1. **Select** the heat exchanger type appropriate for the application
2. **Determine** any unknown inlet/outlet temperature using the energy balance:
   $$\dot{m}_h c_{ph}(T_{h1}-T_{h2}) = \dot{m}_c c_{pc}(T_{c2}-T_{c1})$$
3. **Calculate** the LMTD, $\Delta T_m$, using the correct parallel or counter-flow form (see [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/07_HX_LMTD]])
4. **Obtain** the overall heat transfer coefficient $U$ (from calculation or tables — see [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/11_HX_OverallHTC_Simplified]])
5. **Calculate** heat transfer surface area:
   $$A = \frac{Q}{U \cdot \Delta T_m}$$
6. **Select** a heat exchanger with area $\geq A_s$

> [!note] When LMTD Becomes Iterative
> In a rating problem, $T_{h2}$ and $T_{c2}$ are unknown. The LMTD depends on these unknown temperatures. So:
> 1. Guess $T_{h2}$
> 2. Find $T_{c2}$ from energy balance
> 3. Compute LMTD
> 4. Compute $Q = UA\Delta T_m$
> 5. Check if $Q$ matches $Q = \dot{m}_h c_{ph}(T_{h1}-T_{h2})$
> 6. Iterate until convergence
>
> This is tedious and unstable. The NTU method solves the same problem directly.

---

## Key Details

### Why NTU Was Developed

Kays and London (1955) recognised that the iteration problem for rating calculations was a significant practical obstacle. They reformulated heat exchanger analysis using dimensionless groups:

- **Effectiveness** $\varepsilon = Q_{actual}/Q_{max}$ — how well the exchanger uses its potential
- **NTU** (Number of Transfer Units) $= UA/C_{min}$ — dimensionless size of the exchanger
- **Capacity ratio** $C^* = C_{min}/C_{max}$ — ratio of the two fluid thermal capacities

For any given HX configuration, $\varepsilon$ is a function of NTU and $C^*$ only:
$$\varepsilon = f(\text{NTU}, C^*)$$

This function is tabulated or given as charts. Since NTU and $C^*$ are directly calculable from the known quantities (area, U, flow rates), $\varepsilon$ can be found directly — no iteration needed.

### Comparison Summary

| Aspect | LMTD Method | NTU Method |
|---|---|---|
| Best for | Sizing problems | Rating problems |
| What's given | All 4 temperatures + U | Inlets + A + U |
| What's found | Area A | Outlet temperatures |
| Iteration needed? | No (sizing), Yes (rating) | No |
| Key formula | $Q = UA\Delta T_m$ | $\varepsilon = Q/Q_{max}$; $Q_{max} = C_{min}(T_{h1}-T_{c1})$ |
| Requires | LMTD calculation | NTU–ε charts or equations |

> [!warning]
> Both methods are exact (for their stated assumptions). If you use LMTD for a rating problem and converge your iteration correctly, you get the same answer as NTU. The difference is efficiency, not accuracy.

---

## Why It Matters

Most textbook problems are sizing problems (LMTD is natural). But in engineering practice, performance testing and retrofit analysis involve rating — the exchanger exists and you want to know its output. The NTU method is essential for these real-world applications.

---

## Connections to Other Notes

The LMTD method is fully developed in [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/07_HX_LMTD]] and [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/08_HX_LMTD_WorkedExamples]]. The NTU method is developed in [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/14_HX_NTU_Effectiveness]]. Both build on the energy balance of [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/06_HX_EnergyBalance]] and require $U$ from [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/09_HX_OverallHTC_PlaneWall]] or [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/10_HX_OverallHTC_Cylindrical]].

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/00_HeatExchanger_Hub]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/01_HeatExchanger_MOC]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/07_HX_LMTD]]
*Links to:* [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/14_HX_NTU_Effectiveness]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/06_HX_EnergyBalance]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/08_HX_LMTD_WorkedExamples]]
