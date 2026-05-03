---
publish: true
title: NTU–Effectiveness Method
created: 2026-05-03T10:20:50.458+05:30
modified: 2026-05-03T10:45:59.884+05:30
tags:
  - heat-exchanger
  - MTE3252
  - NTU
  - effectiveness
  - Cmin
  - atomic
cssclasses: ""
---


# NTU–Effectiveness Method

**The NTU–effectiveness method solves heat exchanger rating problems without iteration by expressing performance as a dimensionless effectiveness $\varepsilon = Q_{actual}/Q_{max}$, where $Q_{max} = C_{min}(T_{h1}-T_{c1})$ is the thermodynamic upper limit on heat transfer.**

---

## Definition

The effectiveness $\varepsilon$ is a dimensionless measure of how much heat the exchanger actually transfers relative to the maximum possible heat transfer that would occur in an infinitely long counter-flow exchanger with the same inlet conditions.

$$\boxed{\varepsilon = \frac{Q_{actual}}{Q_{max}}} \qquad 0 \leq \varepsilon \leq 1$$

---

## Mechanism / How It Works

### Step 1 — Define Heat Capacity Rates

$$C_h = \dot{m}_h c_{ph} \quad \text{(W/K)}, \qquad C_c = \dot{m}_c c_{pc} \quad \text{(W/K)}$$

$$C_{min} = \min(C_h, C_c), \qquad C_{max} = \max(C_h, C_c)$$

### Step 2 — Define Maximum Possible Heat Transfer

The maximum heat transfer rate occurs when the fluid with the smaller heat capacity rate ($C_{min}$) undergoes the full inlet-to-inlet temperature change:

$$\boxed{Q_{max} = C_{min}(T_{h1} - T_{c1})}$$

**Why $C_{min}$?** The fluid with smaller $C$ undergoes a larger temperature change for a given $Q$. It reaches the maximum possible temperature first — either $T_{c,out} = T_{h,in}$ or $T_{h,out} = T_{c,in}$. At that point heat transfer must stop (zero driving force). This sets the thermodynamic ceiling.

> [!note] Why Not $C_{max}$?
> If we applied the full temperature difference to $C_{max}$, the other fluid would need to provide/absorb more heat than is thermodynamically possible given the inlet temperatures. Energy conservation would be violated.

### Step 3 — Compute NTU

$$\text{NTU} = \frac{UA}{C_{min}}$$

Where $U$ is the overall heat transfer coefficient and $A$ is the heat transfer area.

### Step 4 — Compute Capacity Ratio

$$C^* = \frac{C_{min}}{C_{max}}$$

### Step 5 — Find Effectiveness from NTU–ε Relation

The effectiveness depends on the flow configuration:

**Parallel Flow:**
$$\varepsilon = \frac{1 - \exp\left[-\text{NTU}(1+C^*)\right]}{1+C^*}$$

**Counter Flow:**
$$\varepsilon = \frac{1 - \exp\left[-\text{NTU}(1-C^*)\right]}{1 - C^* \exp\left[-\text{NTU}(1-C^*)\right]} \quad (C^* \neq 1)$$

**All configurations when $C^* = 0$ (one fluid undergoes phase change — see [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/05_HX_PhaseChange]]):**
$$\varepsilon = 1 - e^{-\text{NTU}}$$

> [!caution] Low Confidence
> The full NTU–ε analytical expressions for all configurations (cross-flow mixed/unmixed, multi-pass shell-and-tube) are not fully covered in the provided lecture slides. The equations above are well-established from standard heat transfer texts (Cengel & Ghajar Ch. 11, Kays & London 1955). Verify against your course textbook before using in exams.

### Step 6 — Find Actual Heat Transfer and Outlet Temperatures

$$Q_{actual} = \varepsilon \cdot Q_{max} = \varepsilon \cdot C_{min}(T_{h1}-T_{c1})$$

Outlet temperatures from energy balance:
$$T_{h2} = T_{h1} - \frac{Q_{actual}}{C_h}, \qquad T_{c2} = T_{c1} + \frac{Q_{actual}}{C_c}$$

---

## Key Details

### Limiting Cases

| Condition | Physical meaning | Result |
|---|---|---|
| NTU → 0 | Infinitely small exchanger | $\varepsilon \to 0$ |
| NTU → ∞ | Infinitely large exchanger | $\varepsilon \to \varepsilon_{max}$ |
| $C^* = 0$ | Phase change (one fluid isothermal) | $\varepsilon = 1 - e^{-\text{NTU}}$ (same for all configurations) |
| $C^* = 1$ | Equal capacity rates | Special counter-flow formula: $\varepsilon = \text{NTU}/(1+\text{NTU})$ |

### Maximum Effectiveness

For parallel flow, even with infinite area:
$$\varepsilon_{max,PF} = \frac{1}{1+C^*} < 1 \quad \text{(always)}$$

For counter flow, $\varepsilon \to 1$ as NTU $\to \infty$ (for $C^* < 1$). This confirms the superiority of counter flow over parallel flow established in [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/03_HX_FlowArrangements]].

---

## Worked Example

**Problem:** A double-pipe parallel-flow HX. Hot water: $\dot{m}_h = 5000$ kg/h, $T_{h1} = 95°C$, $T_{h2} = 65°C$. Cooling water: $\dot{m}_c = 50000$ kg/h, $T_{c1} = 30°C$. $U = 2270$ W/m²K, $c_p = 4.2$ kJ/kg·K for both. Find area and effectiveness.

**Capacity rates:**
$$C_h = \frac{5000}{3600} \times 4200 = 5833 \text{ W/K}$$
$$C_c = \frac{50000}{3600} \times 4200 = 58333 \text{ W/K}$$
$$C_{min} = C_h = 5833 \text{ W/K}, \quad C_{max} = C_c = 58333 \text{ W/K}$$

**Actual Q (from energy balance):**
$$Q = C_h(T_{h1}-T_{h2}) = 5833 \times (95-65) = 175{,}000 \text{ W}$$

**Cold outlet temperature:**
$$T_{c2} = 30 + \frac{175{,}000}{58333} = 30 + 3 = 33°C$$

**LMTD (parallel flow):** $\Delta T_1 = 95-30 = 65°C$, $\Delta T_2 = 65-33 = 32°C$
$$\Delta T_m = \frac{65-32}{\ln(65/32)} = \frac{33}{\ln(2.031)} = \frac{33}{0.708} = 46.6°C$$

**Area:**
$$A = \frac{Q}{U \cdot \Delta T_m} = \frac{175{,}000}{2270 \times 46.6} = \mathbf{1.655 \text{ m}^2}$$

**Effectiveness:**
$$Q_{max} = C_{min}(T_{h1}-T_{c1}) = 5833 \times (95-30) = 379{,}145 \text{ W}$$
$$\varepsilon = \frac{175{,}000}{379{,}145} = \mathbf{0.462} \quad (46.2\%)$$

> [!note]
> An effectiveness of 46% is typical for a parallel-flow exchanger. Counter flow would achieve higher effectiveness for the same area.

---

## Why It Matters

The NTU method eliminates iteration for rating problems and provides a clear physical picture of exchanger performance. The effectiveness is a compact performance metric — useful for comparing different exchanger configurations or assessing degradation due to fouling (which reduces NTU and hence $\varepsilon$).

---

## Connections to Other Notes

The $C_{min}$ concept builds directly on the capacity rates defined in [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/06_HX_EnergyBalance]]. The $C^* = 0$ special case connects to phase-change exchangers in [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/05_HX_PhaseChange]]. The comparison with LMTD is in [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/13_HX_LMTD_vs_NTU]].

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/00_HeatExchanger_Hub]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/01_HeatExchanger_MOC]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/13_HX_LMTD_vs_NTU]]
*Links to:* [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/05_HX_PhaseChange]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/06_HX_EnergyBalance]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/03_HX_FlowArrangements]]
