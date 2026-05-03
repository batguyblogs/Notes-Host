---
publish: true
title: Overall Heat Transfer Coefficient — Plane Wall
created: 2026-05-03T10:20:50.458+05:30
modified: 2026-05-03T10:41:41.216+05:30
tags:
  - heat-exchanger
  - MTE3252
  - overall-HTC
  - thermal-resistance
  - atomic
cssclasses: ""
---


# Overall Heat Transfer Coefficient — Plane Wall

**The overall heat transfer coefficient $U$ (W/m²·°C) is a single parameter that lumps together all thermal resistances between the two fluid streams — inner convection, wall conduction, and outer convection — allowing the heat transfer rate to be written as $Q = UA\Delta T$.**

---

## Definition

In a heat exchanger, heat must travel through three resistances in series: from the hot fluid to the wall surface (convection), through the wall material (conduction), and from the wall surface to the cold fluid (convection again). The overall heat transfer coefficient $U$ is the reciprocal of the sum of these resistances per unit area.

---

## Mechanism / How It Works

### Thermal Resistance Network

For a plane wall separating two fluids:

```
T∞1 (hot fluid) ──[R_conv,i]──[R_wall]──[R_conv,o]── T∞2 (cold fluid)

R_conv,i = 1/(h_i·A)    R_wall = L/(k·A)    R_conv,o = 1/(h_o·A)
```

Total resistance:
$$R_{total} = R_{conv,i} + R_{wall} + R_{conv,o} = \frac{1}{h_i A} + \frac{L}{kA} + \frac{1}{h_o A}$$

Heat transfer rate:
$$Q = \frac{T_{\infty 1} - T_{\infty 2}}{R_{total}} = \frac{T_{\infty 1} - T_{\infty 2}}{\dfrac{1}{h_i A} + \dfrac{L}{kA} + \dfrac{1}{h_o A}}$$

### Factoring Out Area

Taking area $A$ outside the denominator:

$$Q = \frac{A(T_{\infty 1} - T_{\infty 2})}{\dfrac{1}{h_i} + \dfrac{L}{k} + \dfrac{1}{h_o}}$$

Comparing with $Q = UA(T_{\infty 1} - T_{\infty 2})$, the overall heat transfer coefficient is:

$$\boxed{U = \frac{1}{\dfrac{1}{h_i} + \dfrac{L}{k} + \dfrac{1}{h_o}}}$$

Where:
- $h_i$ = convection coefficient on the hot-fluid side (W/m²·°C)
- $h_o$ = convection coefficient on the cold-fluid side (W/m²·°C)
- $L$ = wall thickness (m)
- $k$ = thermal conductivity of the wall material (W/m·°C)

---

## Key Details

### The Series Resistance Analogy

The three resistances behave exactly like electrical resistors in series:

| Thermal Resistance | Expression | Controls when... |
|---|---|---|
| Inner convection | $1/h_i$ | Turbulence low on hot-fluid side |
| Wall conduction | $L/k$ | Wall is thick or has low conductivity |
| Outer convection | $1/h_o$ | Turbulence low on cold-fluid side |

> [!note] The Limiting Resistance
> Since resistances add in series, the *largest* resistance dominates $U$. A very small $h$ on one side (e.g., viscous oil, natural convection gas) will dominate the overall $U$ regardless of how high the other coefficients are. This has major design implications: improving the dominant resistance gives maximum benefit.

### Example: Resistances in Proportion

If $h_i = 1000$, $h_o = 50$, $L/k = 0.001$:
- $1/h_i = 0.001$
- $1/h_o = 0.020$ ← dominates
- $L/k = 0.001$

$$U = \frac{1}{0.001 + 0.001 + 0.020} = \frac{1}{0.022} \approx 45 \text{ W/m}^2\text{°C}$$

Doubling $h_i$ from 1000 to 2000 saves only 0.0005 in the denominator. Doubling $h_o$ saves 0.010 — 20× more impact.

> [!tip] Design Insight
> Always identify the controlling (dominant) resistance when improving a heat exchanger. Spending effort to increase $h$ on the side with already-high $h$ gives negligible return.

### Simplified Form (Negligible Wall Resistance)

When wall thickness is small and thermal conductivity is high (typical thin metal tubes), $L/k \approx 0$:

$$U \approx \frac{1}{\dfrac{1}{h_i} + \dfrac{1}{h_o}} = \frac{h_i h_o}{h_i + h_o}$$

This simplified form is used when wall resistance is explicitly stated to be negligible in a problem.

---

## Why It Matters

The master equation $Q = UA\Delta T_m$ links all three clusters of heat exchanger analysis:
- $Q$ comes from the energy balance ([[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/06_HX_EnergyBalance]])
- $\Delta T_m$ is the LMTD ([[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/07_HX_LMTD]])
- $U$ and $A$ are the unknowns that determine the required exchanger size

Without $U$, the design equation cannot be applied.

---

## Connections to Other Notes

The cylindrical geometry extension of this derivation is in [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/10_HX_OverallHTC_Cylindrical]], where the different inner and outer areas make the analysis more involved. The simplified form connects to [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/11_HX_OverallHTC_Simplified]]. Adding fouling resistance to this formula is covered in [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/12_HX_Fouling]].

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/00_HeatExchanger_Hub]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/01_HeatExchanger_MOC]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/07_HX_LMTD]]
*Links to:* [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/10_HX_OverallHTC_Cylindrical]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/11_HX_OverallHTC_Simplified]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/12_HX_Fouling]]
