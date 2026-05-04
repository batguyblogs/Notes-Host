---
publish: true
title: Heat Exchangers — Placeholder
created: 2026-05-02
modified: 2026-05-04T06:21:19.897+05:30
tags:
  - FluidMechanics
  - AdvancedTopics
  - atomic
  - heat-exchangers
  - needs-verification
cssclasses: ""
---


# Heat Exchangers — Placeholder

> [!warning] Content Gap — No Source Material Available
> Heat exchangers were specified as part of the MTE 3252 course topic but are **entirely
> absent** from the provided reference material (FM_Notes.pdf). This note is a structural
> scaffold only. **No content has been written** to avoid hallucination of specific
> formulae, effectiveness values, or design parameters.
>
> **Action required**: Populate this note from your own lecture notes, slides, or
> course textbook before using it for study or assessment preparation.

---

# [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/00_HeatExchanger_Hub\|Heat Exchangers]]

## Suggested Structure (Fill In From Your Notes)

### 1. Definition and Purpose
- What is a heat exchanger?
- Where are they used? (power plants, HVAC, chemical processing, refrigeration)
- What is the fundamental mechanism? (hot and cold fluid streams exchanging thermal energy
  across a separating wall without mixing)

### 2. Classification by Flow Arrangement
- **Parallel flow**: both fluids enter at the same end and flow in the same direction
- **Counter flow**: fluids enter from opposite ends and flow in opposite directions
- **Cross flow**: fluids flow perpendicular to each other
- Which arrangement is most thermally efficient and why?

### 3. Classification by Construction Type
- Shell-and-tube heat exchangers
- Plate heat exchangers
- Double-pipe (hairpin) heat exchangers
- Finned tube heat exchangers
- Other types covered in your course

### 4. Key Parameters
- Overall heat transfer coefficient $U$ (W/m²·K)
- Heat transfer area $A$ (m²)
- Log Mean Temperature Difference (LMTD) $\Delta T_{lm}$
- Heat duty $\dot{Q} = UA\Delta T_{lm}$ (W)

### 5. LMTD Method
$$\Delta T_{lm} = \frac{\Delta T_1 - \Delta T_2}{\ln(\Delta T_1 / \Delta T_2)}$$
- Define $\Delta T_1$ and $\Delta T_2$ for your flow arrangement
- Correction factor $F$ for multi-pass and cross-flow configurations

### 6. Effectiveness-NTU (ε-NTU) Method
- Effectiveness $\varepsilon$ = actual heat transfer / maximum possible heat transfer
- Number of Transfer Units $NTU = UA/C_{min}$
- When to use ε-NTU vs LMTD

### 7. Energy Balance
$$\dot{Q} = \dot{m}_h c_{p,h} (T_{h,in} - T_{h,out}) = \dot{m}_c c_{p,c} (T_{c,out} - T_{c,in})$$

### 8. Fouling and Pressure Drop
- Fouling resistance $R_f$
- Effect on $U$ over time
- Pressure drop considerations (connects back to [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/20_MajorLosses_DarcyWeisbach]])

### 9. Design and Sizing Procedure
- Step-by-step approach used in your course

### 10. Worked Examples
- Insert numerical examples from your lecture notes here

---

## Connections to Other Notes

- Thermal boundary layer (bridge from fluid mechanics to heat transfer): [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/26_BoundaryLayer]]
- Pressure drop on the shell/tube side uses Darcy-Weisbach: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/20_MajorLosses_DarcyWeisbach]]
- Flow in shell/tube passages is governed by Reynolds number: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/14_ReynoldsNumber]]
- Fluid properties (ρ, μ, ν) needed for Re calculations in HX design: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01b_FluidProperties_Hub]]

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01d_AdvancedTopics_Hub]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/02d_AdvancedTopics_MOC]]
*Links to:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/26_BoundaryLayer]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/20_MajorLosses_DarcyWeisbach]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/14_ReynoldsNumber]]
