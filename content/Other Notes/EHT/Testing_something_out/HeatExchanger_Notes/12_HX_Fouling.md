---
publish: true
title: Fouling and the Fouling Factor
created: 2026-05-03T10:20:50.458+05:30
modified: 2026-05-03T10:44:53.772+05:30
tags:
  - heat-exchanger
  - MTE3252
  - fouling
  - fouling-factor
  - atomic
cssclasses: ""
---


# Fouling and the Fouling Factor

**Fouling is the accumulation of unwanted deposits on heat exchanger surfaces over time — scales, sediments, or biological agents — which adds additional thermal resistance and degrades performance; this effect is quantified by the fouling factor $R_f$ (m²·K/W).**

---

## Definition

Fouling is an unavoidable operational reality for most heat exchangers. It occurs progressively after commissioning as deposits build up. The fouling factor $R_f$ represents the added thermal resistance per unit area due to these deposits.

---

## Mechanism / How It Works

### What Causes Fouling

After a period of operation, heat exchanger surfaces accumulate:
- **Scaling**: Precipitation of dissolved minerals (e.g., calcium carbonate from hard water)
- **Corrosion products**: Rust and oxide layers forming on metallic surfaces
- **Biological growth**: Algae, bacteria, mussels (in seawater systems)
- **Particulate deposition**: Sediment, suspended solids settling on surfaces
- **Chemical reaction products**: Polymerisation, coking (in petroleum processing)

### Effect on Heat Transfer

Each fouling layer adds a thermal resistance in series with the existing resistances. This:
1. Increases $R_{total}$
2. Decreases the effective $U$
3. Reduces the actual $Q$ for a given temperature difference

### Fouling Factor Definition

The fouling factor is measured experimentally by comparing the same exchanger in clean and fouled states:

$$\boxed{R_f = \frac{1}{U_{dirty}} - \frac{1}{U_{clean}} \quad \text{(m}^2\text{·K/W)}}$$

> [!note]
> $R_f = 0$ for a brand new heat exchanger (clean state). It increases with operating time until steady state (equilibrium between deposition and removal rates) or until cleaning is performed.

> [!warning]
> $R_f$ **cannot be calculated from first principles**. It must be determined experimentally by measuring $U$ for a clean and a fouled exchanger of identical design under identical operating conditions, or taken from standard reference tables (e.g., TEMA standards).

---

## Key Details

### Full $UA$ Expression with Fouling (Cylindrical Tube)

Adding inner ($R_{f,i}$) and outer ($R_{f,o}$) fouling resistances:

$$UA_{ref} = U_i A_i = U_o A_o = \frac{1}{\dfrac{1}{h_i A_i} + \dfrac{R_{f,i}}{A_i} + \dfrac{\ln(r_o/r_i)}{2\pi kL} + \dfrac{R_{f,o}}{A_o} + \dfrac{1}{h_o A_o}}$$

Each fouling resistance adds directly to the denominator, increasing $R_{total}$ and decreasing $U$.

### Representative Fouling Factors

> [!caution] Time-Sensitive
> These values are from the TEMA (Tubular Exchanger Manufacturers Association) standard, as cited in the lecture slides. Standards and recommended values can be updated. Verify against current TEMA or equivalent standards for professional design.

| Fluid | $R_f$ (m²·K/W) |
|---|---|
| Distilled water, sea water, river water (below 50°C) | 0.0001 |
| Distilled water, sea water, river water (above 50°C) | 0.0002 |
| Fuel oil | 0.0009 |
| Transformer / lubricating / hydraulic oil | 0.0002 |
| Quenching oil | 0.0007 |
| Vegetable oil | 0.0005 |
| Steam (oil-free) | 0.0001 |
| Steam (with oil traces) | 0.0002 |
| Organic solvent vapors, natural gas | 0.0002 |
| Engine exhaust and fuel gases | 0.0018 |
| Refrigerants (liquid) | 0.0002 |
| Refrigerants (vapour) | 0.0004 |
| Ethylene/methylene glycol (antifreeze) | 0.00035 |
| Alcohol vapours | 0.0001 |
| Air | 0.0004 |

### Observations

1. **Engine exhaust** has the highest $R_f$ (0.0018) — combustion gases carry soot and particulates that foul aggressively
2. **Fuel oil** is next (0.0009) — viscous oils deposit on cool surfaces
3. **Clean steam and distilled water** are lowest (0.0001) — clean fluids at low temperature barely foul
4. Higher temperatures generally increase fouling rates (higher reaction rates, more precipitation)

> [!tip] Design Practice
> Heat exchangers are deliberately over-sized at design time to account for expected fouling. The "clean" U gives the as-new performance; the designer must ensure the exchanger still meets duty requirements with fouled surfaces, using the "dirty" U in calculations.

---

## Why It Matters

Fouling is the reason heat exchangers require periodic cleaning and maintenance. Ignoring fouling in design leads to under-performing exchangers after only weeks or months of operation. The fouling allowance also affects the choice of tube-side vs shell-side assignment (see [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/04_HX_ShellAndTube]]) — the fluid with higher fouling potential is usually placed on the tube side for easier mechanical cleaning.

> [!example]
> A feedwater heater is designed with $U_{clean} = 6000$ W/m²·K. After 6 months of operation with river water (above 50°C), $R_f = 0.0002$ m²·K/W on both surfaces. The dirty U becomes approximately:
> $$\frac{1}{U_{dirty}} = \frac{1}{6000} + 0.0002 + 0.0002 = 0.000167 + 0.0004 = 0.000567$$
> $$U_{dirty} \approx 1765 \text{ W/m}^2\text{·K}$$
> A drop of ~70% — dramatic performance degradation justifying scheduled cleaning.

---

## Connections to Other Notes

The fouling factor adds terms to the U expressions derived in [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/10_HX_OverallHTC_Cylindrical]]. The clean U starting point is from [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/11_HX_OverallHTC_Simplified]]. The fouled U reduces effective $Q = UA\Delta T_m$, which connects back to [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/07_HX_LMTD]].

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/00_HeatExchanger_Hub]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/01_HeatExchanger_MOC]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/11_HX_OverallHTC_Simplified]]
*Links to:* [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/09_HX_OverallHTC_PlaneWall]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/10_HX_OverallHTC_Cylindrical]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/04_HX_ShellAndTube]]
