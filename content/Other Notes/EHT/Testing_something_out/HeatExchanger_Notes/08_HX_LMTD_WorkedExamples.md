---
publish: true
title: LMTD Method — Worked Examples
created: 2026-05-03T10:20:50.458+05:30
modified: 2026-05-03T10:41:13.499+05:30
tags:
  - heat-exchanger
  - MTE3252
  - LMTD
  - worked-examples
  - atomic
cssclasses: ""
---


# LMTD Method — Worked Examples

**These worked examples demonstrate the complete LMTD method procedure: energy balance first to find all temperatures, then LMTD calculation, then U determination, then area or length solution.**

---

## Problem-Solving Procedure (LMTD Method)

Before attempting any problem, follow this sequence:

1. **Draw the configuration** — sketch the HX and label all known temperatures
2. **Energy balance** — find any unknown temperatures using $\dot{m}_h c_{ph}(T_{h1}-T_{h2}) = \dot{m}_c c_{pc}(T_{c2}-T_{c1})$
3. **Compute $\Delta T_1$ and $\Delta T_2$** — using parallel or counter-flow definitions from [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/07_HX_LMTD]]
4. **Compute LMTD** — $\Delta T_m = \dfrac{\Delta T_1 - \Delta T_2}{\ln(\Delta T_1/\Delta T_2)}$
5. **Determine U** — from [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/09_HX_OverallHTC_PlaneWall]] or [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/10_HX_OverallHTC_Cylindrical]]
6. **Apply** $Q = UA\Delta T_m$ — solve for $A$ (or rearrange for any unknown)

---

## Example 1 — Find the Heat Exchanger Area

**Problem:** Hot water (0.2 kg/s) enters a **parallel-flow** double-pipe HX at 75°C and exits at 45°C. Cold water (0.5 kg/s) enters at 20°C. Individual heat transfer coefficients on both sides are $h_i = h_o = 650$ W/m²·°C. Find the required heat transfer area.

### Step 1 — Energy Balance (find $T_{c2}$)

$$Q = \dot{m}_h c_{ph}(T_{h1} - T_{h2}) = 0.2 \times 4187 \times (75-45) = 25{,}122 \text{ W}$$

$$25{,}122 = 0.5 \times 4187 \times (T_{c2} - 20) \implies T_{c2} = 32°C$$

### Step 2 — LMTD (Parallel Flow)

$$\Delta T_1 = T_{h1} - T_{c1} = 75 - 20 = 55°C$$
$$\Delta T_2 = T_{h2} - T_{c2} = 45 - 32 = 13°C$$

$$\Delta T_m = \frac{55 - 13}{\ln(55/13)} = \frac{42}{\ln(4.23)} = \frac{42}{1.442} = 29.1°C$$

### Step 3 — Overall Heat Transfer Coefficient U

Since $h_i = h_o = 650$ W/m²·°C (neglecting wall resistance and assuming $A_i \approx A_o$):

$$U = \frac{h_i h_o}{h_i + h_o} = \frac{650 \times 650}{650 + 650} = 325 \text{ W/m}^2\text{°C}$$

### Step 4 — Solve for Area

$$A = \frac{Q}{U \cdot \Delta T_m} = \frac{25{,}122}{325 \times 29.1} = \mathbf{2.66 \text{ m}^2}$$

---

## Example 2 — Minimum Oil Cooling Temperature (Parallel Flow Limit)

**Problem:** In a parallel-flow double-pipe HX, water is heated from 20°C to 70°C. Oil is cooled from 200°C to 100°C. If the exchanger length is increased, what is the minimum temperature to which the oil can be cooled?

### Key Concept

In parallel flow, both fluids approach a **common equilibrium temperature** asymptotically as length increases. The minimum oil exit temperature occurs when the two streams reach thermal equilibrium — i.e., $T_{h,min} = T_{c,max} = T_{eq}$.

### Solution

From the energy balance at current conditions, find the capacity rate ratio:

$$\dot{m}_h c_{ph}(200-100) = \dot{m}_c c_{pc}(70-20)$$
$$\frac{\dot{m}_c c_{pc}}{\dot{m}_h c_{ph}} = \frac{100}{50} = 2$$

Let $T_{min}$ = lowest possible oil temperature = equilibrium temperature of both streams.

At equilibrium, energy balance from initial state to equilibrium:
$$\dot{m}_h c_{ph}(200 - T_{min}) = \dot{m}_c c_{pc}(T_{min} - 20)$$
$$1 \times (200 - T_{min}) = 2 \times (T_{min} - 20)$$
$$200 - T_{min} = 2T_{min} - 40$$
$$240 = 3T_{min}$$

$$\boxed{T_{min} = 80°C}$$

> [!note] Physical Interpretation
> The oil can never be cooled below 80°C in this parallel-flow configuration, no matter how long the exchanger is. In a counter-flow arrangement, the oil *could* be cooled further (potentially below 70°C) because the cold water inlet is at the same end as the hot oil outlet.

> [!warning] Exam Trap
> Do not confuse the "minimum temperature in parallel flow" concept with counter-flow analysis. In counter flow, no such equilibrium temperature limit exists — the cold fluid outlet can theoretically reach $T_{h1}$ if the exchanger is infinitely long.

---

## Example 3 — Find Length Given Tube Dimensions (Parallel Flow, Cylindrical)

**Problem:** Air is heated by hot exhaust gases in a parallel-flow HX. Given: $Q = 155{,}450$ kJ/h, $h_i = 120$ W/m²·°C, $h_o = 195$ W/m²·°C, $T_{h1} = 450°C$, $T_{h2} = 250°C$, $T_{c1} = 60°C$, $T_{c2} = 120°C$, $D_i = 50$ mm, $D_o = 60$ mm. Neglect tube wall resistance. Find the tube length.

### LMTD (Parallel Flow)

$$\Delta T_1 = T_{h1} - T_{c1} = 450 - 60 = 390°C$$
$$\Delta T_2 = T_{h2} - T_{c2} = 250 - 120 = 130°C$$

$$\Delta T_m = \frac{390-130}{\ln(390/130)} = \frac{260}{\ln(3)} = \frac{260}{1.099} = 236.6°C$$

### Overall HTC Based on Inner Surface ($U_i$)

Using the cylindrical formula from [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/10_HX_OverallHTC_Cylindrical]] (wall resistance neglected):

$$U_i = \frac{1}{\dfrac{1}{h_i} + \dfrac{1}{h_o}\cdot\dfrac{r_i}{r_o}} = \frac{1}{\dfrac{1}{120} + \dfrac{1}{195}\cdot\dfrac{0.025}{0.03}}$$

$$U_i = \frac{1}{0.00833 + 0.004274} = \frac{1}{0.01261} = 79.32 \text{ W/m}^2\text{°C}$$

### Solve for Length

$$Q = U_i A_i \Delta T_m = U_i (2\pi r_i L) \Delta T_m$$

$$L = \frac{Q}{U_i (2\pi r_i) \Delta T_m} = \frac{155{,}450 \times \frac{1000}{3600}}{79.32 \times (2\pi \times 0.025) \times 236.6}$$

$$L = \frac{43{,}180}{79.32 \times 0.1571 \times 236.6} = \frac{43{,}180}{2{,}949} = \boxed{14.64 \text{ m}}$$

---

## Connections to Other Notes

The LMTD formula used here is derived in [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/07_HX_LMTD]]. The cylindrical U formula is from [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/10_HX_OverallHTC_Cylindrical]]. The energy balance steps follow [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/06_HX_EnergyBalance]].

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/00_HeatExchanger_Hub]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/01_HeatExchanger_MOC]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/07_HX_LMTD]]
*Links to:* [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/06_HX_EnergyBalance]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/09_HX_OverallHTC_PlaneWall]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/10_HX_OverallHTC_Cylindrical]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/13_HX_LMTD_vs_NTU]]
