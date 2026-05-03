---
publish: true
title: Phase-Change Heat Exchangers (Condensers and Evaporators)
created: 2026-05-03T10:20:50.458+05:30
modified: 2026-05-03T10:36:37.962+05:30
tags:
  - heat-exchanger
  - MTE3252
  - condenser
  - evaporator
  - phase-change
  - atomic
cssclasses: ""
---


# Phase-Change Heat Exchangers (Condensers and Evaporators)

**In a phase-change heat exchanger, one of the fluids undergoes a change of physical state — condensation or evaporation — during the heat exchange process, causing its temperature to remain effectively constant throughout the exchanger regardless of flow arrangement.**

---

## Definition

Phase-change heat exchangers are a special sub-category of recuperators where one fluid releases or absorbs latent heat at a constant saturation temperature, rather than sensible heat over a temperature range.

---

## Mechanism / How It Works

### Condenser

The hot fluid **condenses**: it enters as a vapour (or wet vapour/superheated steam) and exits as a liquid. During condensation, the temperature of the condensing fluid remains at the saturation temperature $T_{sat}$ — a flat horizontal line on the T-position graph.

$$C_h = \dot{m}_h c_{ph} \to \infty \quad \text{(apparent heat capacity rate during phase change)}$$

The cold fluid receives this heat and its temperature rises continuously.

```
T
│   T_sat ────────────────── Condensing fluid (constant T)
│         ↓↓↓ Q̇ ↓↓↓
│                    ╱ Cold fluid rising
│                   ╱
│──────────────────────────► Position along HX
   Inlet                   Outlet
```

### Evaporator (Boiler)

The cold fluid **evaporates**: it enters as a liquid and exits as vapour, absorbing heat at constant saturation temperature.

$$C_c = \dot{m}_c c_{pc} \to \infty$$

The hot fluid cools continuously while the boiling fluid remains at constant temperature.

---

## Key Details

### The $C \to \infty$ Limit

Heat capacity rate is defined as $C = \dot{m} c_p$ (W/K). For a fluid undergoing phase change, the temperature does not change despite heat being added/removed — mathematically, this is equivalent to $c_p \to \infty$, so $C \to \infty$.

This has important consequences for the NTU method (see [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/14_HX_NTU_Effectiveness]]):

$$C^* = \frac{C_{min}}{C_{max}} = \frac{C_{min}}{\infty} = 0$$

When $C^* = 0$, the effectiveness–NTU relations simplify to:

$$\varepsilon = 1 - e^{-NTU}$$

for **all** flow configurations — parallel flow, counter flow, and cross flow all give the same result. This means the flow arrangement is irrelevant for condensers and evaporators.

> [!note] Why Flow Direction Doesn't Matter Here
> When one fluid is isothermal, the temperature *difference* driving heat transfer has the same form regardless of which direction the other fluid flows. The shape of the driving force profile changes, but the LMTD remains the same — parallel and counter flow give identical results.

### LMTD for Phase-Change Exchangers

For a condenser, with $T_h$ = constant = $T_{sat}$:

$$\Delta T_1 = T_{sat} - T_{c1}, \quad \Delta T_2 = T_{sat} - T_{c2}$$

$$\Delta T_m = \frac{(T_{sat} - T_{c1}) - (T_{sat} - T_{c2})}{\ln\left(\frac{T_{sat} - T_{c1}}{T_{sat} - T_{c2}}\right)} = \frac{T_{c2} - T_{c1}}{\ln\left(\frac{T_{sat} - T_{c1}}{T_{sat} - T_{c2}}\right)}$$

This is the same formula as standard LMTD — the phase-change simply sets one temperature to a constant value.

> [!warning] Exam Trap
> Do not try to use $Q = \dot{m}c_p\Delta T$ for the phase-change fluid using $c_p$ for the liquid or vapour. Instead, use latent heat: $Q = \dot{m} h_{fg}$, where $h_{fg}$ is the enthalpy of vaporisation.

---

## Why It Matters

Condensers and evaporators appear in essentially every power cycle (steam Rankine cycle) and refrigeration system. Recognising the $C \to \infty$ simplification allows much simpler analysis — you only need to track the single-phase fluid's temperature rise/drop.

> [!example]
> In a steam power plant condenser, steam enters at ~40°C (saturation) and exits as liquid water at ~40°C. Cooling water enters at 20°C and leaves at ~30°C. Despite the parallel/counter-flow distinction being irrelevant thermally, engineers still choose counter-flow layouts for structural and flow distribution reasons.

---

## Connections to Other Notes

The $C \to \infty$ condition directly simplifies the NTU–effectiveness equations in [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/14_HX_NTU_Effectiveness]]. The LMTD calculation approach is covered in [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/07_HX_LMTD]]. The flow arrangement discussion in [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/03_HX_FlowArrangements]] applies in modified form here.

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/00_HeatExchanger_Hub]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/01_HeatExchanger_MOC]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/03_HX_FlowArrangements]]
*Links to:* [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/07_HX_LMTD]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/14_HX_NTU_Effectiveness]]
