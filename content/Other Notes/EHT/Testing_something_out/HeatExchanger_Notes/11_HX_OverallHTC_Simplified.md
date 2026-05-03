---
publish: true
title: Overall Heat Transfer Coefficient — Simplified Form and Representative Values
created: 2026-05-03T10:20:50.458+05:30
modified: 2026-05-03T10:44:13.067+05:30
tags:
  - heat-exchanger
  - MTE3252
  - overall-HTC
  - simplified
  - atomic
cssclasses: ""
---


# Overall Heat Transfer Coefficient — Simplified Form and Representative Values

**When tube wall thickness is small and thermal conductivity is high, the conduction resistance can be neglected, reducing the overall heat transfer coefficient to $U = h_i h_o / (h_i + h_o)$; representative values of $U$ vary by three orders of magnitude depending on the fluid combination.**

---

## Definition

The simplified form of $U$ applies when: (a) the wall conduction resistance is negligible ($L/k \approx 0$ for plane wall, or $\ln(r_o/r_i)/2\pi kL \approx 0$ for cylindrical), and (b) inner and outer areas are approximately equal ($A_i \approx A_o \approx A$).

---

## Mechanism / How It Works

### Condition for Simplification

Starting from the full plane wall expression (see [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/09_HX_OverallHTC_PlaneWall]]):

$$U = \frac{1}{\dfrac{1}{h_i} + \dfrac{L}{k} + \dfrac{1}{h_o}}$$

When $L/k \to 0$ (thin, high-conductivity wall):

$$U \approx \frac{1}{\dfrac{1}{h_i} + \dfrac{1}{h_o}}$$

Simplifying algebraically:

$$\boxed{U = \frac{h_i h_o}{h_i + h_o}}$$

This is the harmonic mean of $h_i$ and $h_o$, not the arithmetic mean.

> [!note]
> This form is valid ONLY when:
> 1. Wall resistance is explicitly negligible (stated in the problem, or wall is thin metal)
> 2. There is no fouling (or fouling is separately added — see [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/12_HX_Fouling]])
> 3. $A_i \approx A_o$ (i.e., tube wall is thin, $r_i \approx r_o$)

---

## Key Details

### Physical Interpretation

The harmonic mean form shows why improving only the *higher* $h$ has diminishing returns:

If $h_i \gg h_o$: then $U \approx h_o$ (outer side dominates entirely)
If $h_i = h_o = h$: then $U = h/2$ (equal contributions, each adds the same resistance)

### Representative Values of U

> [!caution] Time-Sensitive
> These representative values are sourced from the lecture slides (attributed to Cengel & Ghajar). They represent typical engineering ranges, not precise design values. Actual $U$ depends on fluid properties, flow conditions, geometry, and fouling state. Verify against manufacturer data or current handbooks for professional work.

| Type of Heat Exchanger | U (W/m²·°C) |
|---|---|
| Water-to-water | 850 – 1700 |
| Water-to-oil | 100 – 350 |
| Water-to-gasoline or kerosene | 300 – 1000 |
| Feedwater heaters | 1000 – 8500 |
| Steam-to-light fuel oil | 200 – 400 |
| Steam-to-heavy fuel oil | 50 – 200 |
| Steam condenser | 1000 – 6000 |
| Freon condenser (water cooled) | 300 – 1000 |
| Ammonia condenser (water cooled) | 800 – 1400 |
| Alcohol condensers (water cooled) | 250 – 700 |
| Gas-to-gas | 10 – 40 |
| Water-to-air in finned tubes (based on water side) | 400 – 850 |
| Steam-to-air in finned tubes (based on steam side) | 400 – 4000 |

### Observations from the Table

1. **Gas-to-gas is worst** (~10–40 W/m²·°C) — gases have poor convective properties; this explains why compact heat exchangers (fins) are essential in gas applications
2. **Water-to-water is excellent** (~850–1700 W/m²·°C) — water's high thermal conductivity and specific heat make it an ideal heat transfer medium
3. **Phase-change is highest** — condensers and feedwater heaters have very high $U$ because condensation convection coefficients are extremely large
4. **Oil-side lowers U dramatically** — the viscosity of oil reduces turbulence and $h$; water-to-oil is 5× lower than water-to-water

> [!tip] Quick Estimation
> When $h_i$ and $h_o$ are very different (ratio > 5:1), $U$ is approximately equal to the smaller $h$ value. This is a useful sanity check: if $h_i = 5000$ and $h_o = 200$, then $U \approx 200$ W/m²·°C.

---

## Why It Matters

The simplified form is used in the majority of textbook problems where wall resistance is stated to be negligible. The representative values table is used for order-of-magnitude estimates when full fluid property data are unavailable, and as a sanity check for calculated $U$ values.

---

## Connections to Other Notes

This simplification follows from the full derivations in [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/09_HX_OverallHTC_PlaneWall]] and [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/10_HX_OverallHTC_Cylindrical]]. Adding fouling resistance to this simplified $U$ is covered in [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/12_HX_Fouling]]. The $U$ value feeds into the master design equation $Q = UA\Delta T_m$ used throughout [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/07_HX_LMTD]] and [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/08_HX_LMTD_WorkedExamples]].

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/00_HeatExchanger_Hub]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/01_HeatExchanger_MOC]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/09_HX_OverallHTC_PlaneWall]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/10_HX_OverallHTC_Cylindrical]]
*Links to:* [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/12_HX_Fouling]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/07_HX_LMTD]]
