---
publish: true
title: Heat Exchanger Energy Balance
created: 2026-05-03T10:20:50.457+05:30
modified: 2026-05-03T10:38:11.149+05:30
tags:
  - heat-exchanger
  - MTE3252
  - energy-balance
  - atomic
cssclasses: ""
---


# Heat Exchanger Energy Balance

**The energy balance for a heat exchanger states that, under adiabatic steady-state operation with negligible kinetic and potential energy changes, the heat lost by the hot fluid exactly equals the heat gained by the cold fluid.**

---

## Definition

The energy balance is the first equation applied to any heat exchanger problem. It relates inlet and outlet temperatures to mass flow rates and specific heats, allowing unknown temperatures to be found before any heat transfer coefficient or area calculation begins.

---

## Mechanism / How It Works

### Governing Assumptions

1. **Adiabatic operation**: No heat loss to surroundings (the exchanger is perfectly insulated externally)
2. **Steady state**: All conditions constant in time
3. **Negligible kinetic and potential energy changes**: Valid for most liquid/gas HX problems
4. **Constant specific heats**: $c_p$ evaluated at mean temperature

### The Core Equations

Heat lost by the hot fluid:
$$Q_h = \dot{m}_h c_{ph} \Delta T_h = \dot{m}_h c_{ph}(T_{h1} - T_{h2})$$

Heat gained by the cold fluid:
$$Q_c = \dot{m}_c c_{pc} \Delta T_c = \dot{m}_c c_{pc}(T_{c2} - T_{c1})$$

Setting $Q_h = Q_c$:

$$\boxed{\dot{m}_h c_{ph}(T_{h1} - T_{h2}) = \dot{m}_c c_{pc}(T_{c2} - T_{c1})}$$

Where:
- $\dot{m}_h, \dot{m}_c$ = mass flow rates of hot and cold fluids (kg/s)
- $c_{ph}, c_{pc}$ = specific heats at constant pressure (kJ/kg·°C)
- $T_{h1}, T_{h2}$ = hot fluid inlet and outlet temperatures (°C)
- $T_{c1}, T_{c2}$ = cold fluid inlet and outlet temperatures (°C)

### Notation Convention

> [!note] Subscript Convention
> Subscripts $h$ and $c$ refer to hot and cold fluids respectively. Subscripts 1 and 2 refer to **inlet** and **outlet** conditions respectively. This notation is used consistently throughout all heat exchanger notes.

### Heat Capacity Rate

It is convenient to define the **heat capacity rate**:

$$C_h = \dot{m}_h c_{ph} \quad \text{(W/K)} \qquad C_c = \dot{m}_c c_{pc} \quad \text{(W/K)}$$

The energy balance then reads: $Q = C_h(T_{h1} - T_{h2}) = C_c(T_{c2} - T_{c1})$

This notation is essential for the NTU method — see [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/14_HX_NTU_Effectiveness]].

---

## Key Details

### What the Energy Balance Tells You

With the four temperatures and two capacity rates, you have six quantities and one equation. In practice:

- If **3 temperatures and both capacity rates** are known → find the 4th temperature
- If **2 temperatures and both capacity rates** are known → find the other 2 temperatures (need another equation — LMTD or NTU)
- If **4 temperatures are known** → find the ratio $C_h / C_c$

### The Capacity Rate Ratio

$$\frac{\dot{m}_c c_{pc}}{\dot{m}_h c_{ph}} = \frac{T_{h1} - T_{h2}}{T_{c2} - T_{c1}}$$

This ratio of temperature changes is inversely proportional to the capacity rate ratio. The fluid with the **smaller** capacity rate undergoes the **larger** temperature change. This is the physical basis for $C_{min}$ in the NTU method.

---

## Worked Example

From the lecture slides: In a parallel flow HX, hot water (0.2 kg/s) enters at 75°C and leaves at 45°C. Cold water (0.5 kg/s) enters at 20°C. Find the cold water outlet temperature.

$$Q = \dot{m}_h c_{ph}(T_{h1} - T_{h2}) = 0.2 \times 4187 \times (75 - 45) = 25{,}122 \text{ W}$$

$$Q = \dot{m}_c c_{pc}(T_{c2} - T_{c1})$$
$$25{,}122 = 0.5 \times 4187 \times (T_{c2} - 20)$$
$$T_{c2} = 20 + \frac{25{,}122}{0.5 \times 4187} = \mathbf{32°C}$$

> [!note]
> The energy balance is solved *first*, independently of the heat transfer coefficient or area. Only once all four temperatures are known does the LMTD calculation (see [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/07_HX_LMTD]]) proceed.

---

## Why It Matters

Every heat exchanger problem — whether using the LMTD method or the NTU method — begins with the energy balance. It is the equation that connects thermodynamic quantities (temperatures, flow rates) to the heat duty $Q$. All subsequent calculation of LMTD, U, and area builds on it.

---

## Connections to Other Notes

The capacity rates $C_h$ and $C_c$ defined here directly feed into the NTU effectiveness method in [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/14_HX_NTU_Effectiveness]], where $C_{min}$ and $C_{max}$ determine $Q_{max}$. The temperatures found from the energy balance are used to compute LMTD in [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/07_HX_LMTD]].

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/00_HeatExchanger_Hub]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/01_HeatExchanger_MOC]]
*Links to:* [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/07_HX_LMTD]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/08_HX_LMTD_WorkedExamples]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/14_HX_NTU_Effectiveness]]
