---
publish: true
title: Heat Exchangers — Hub
created: 2025-05-03
modified: 2026-05-03T10:54:17.773+05:30
tags:
  - hub
  - heat-exchanger
  - MTE3252
  - thermal-engineering
cssclasses: ""
---


# Heat Exchangers — Hub
**Course: MTE 3252 | Credits: 3-1-0-4**

Heat exchangers are devices that transfer thermal energy between two fluids at different temperatures, separated by a solid wall, without the fluids mixing. They are foundational to power generation, chemical processing, HVAC, and waste heat recovery — almost every industrial thermal system contains at least one.

---

## Visual Topic Map

```
HEAT EXCHANGERS
│
├── TYPES & CONFIGURATIONS
│   ├── Classification (direct contact / regenerative / recuperative)
│   ├── Flow Arrangements (parallel / counter / cross-flow)
│   ├── Shell-and-Tube (passes, baffles)
│   └── Phase-Change (condensers, evaporators)
│
├── THERMAL ANALYSIS FOUNDATIONS
│   ├── Energy Balance (Q = mCpΔT)
│   ├── LMTD Method (ΔTm formula, parallel vs counter)
│   └── LMTD Worked Examples
│
├── OVERALL HEAT TRANSFER COEFFICIENT (U)
│   ├── Plane Wall Geometry
│   ├── Cylindrical Geometry (Ui vs Uo)
│   └── Simplified Form + Representative Values
│
└── DESIGN METHODS & DEGRADATION
    ├── Fouling and Fouling Factor (Rf)
    ├── LMTD vs NTU — When to Use Which
    └── NTU–Effectiveness Method
```


---

## File Index

| File                             | Type   | Description                                          |
| -------------------------------- | ------ | ---------------------------------------------------- |
| [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/01_HeatExchanger_MOC]]         | MOC    | Synthesis layer — all four clusters with cross-links |
| [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/02_HX_Classification]]         | Atomic | Direct contact, regenerative, recuperative types     |
| [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/03_HX_FlowArrangements]]       | Atomic | Parallel, counter, cross-flow; mixed vs unmixed      |
| [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/04_HX_ShellAndTube]]           | Atomic | Shell-and-tube design, baffles, pass configurations  |
| [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/05_HX_PhaseChange]]            | Atomic | Condensers and evaporators; C→∞ behaviour            |
| [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/06_HX_EnergyBalance]]          | Atomic | Energy balance: Q = mhcph(Th1−Th2) = mccpc(Tc2−Tc1)  |
| [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/07_HX_LMTD]]                   | Atomic | LMTD formula, parallel vs counter derivation         |
| [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/08_HX_LMTD_WorkedExamples]]    | Atomic | Two fully worked LMTD problems                       |
| [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/09_HX_OverallHTC_PlaneWall]]   | Atomic | U for plane wall; thermal resistance network         |
| [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/10_HX_OverallHTC_Cylindrical]] | Atomic | U for cylindrical tube; Ui vs Uo distinction         |
| [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/11_HX_OverallHTC_Simplified]]  | Atomic | Simplified U (thin wall); representative U table     |
| [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/12_HX_Fouling]]                | Atomic | Fouling, fouling factor Rf, effect on U              |
| [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/13_HX_LMTD_vs_NTU]]            | Atomic | Comparison of methods; LMTD procedure                |
| [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/14_HX_NTU_Effectiveness]]      | Atomic | ε–NTU method; Qmax, Cmin, effectiveness              |

---

## Key Questions

1. **Why does counter-flow always outperform parallel-flow?** → [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/07_HX_LMTD]]
2. **What is the physical meaning of the overall heat transfer coefficient U?** → [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/09_HX_OverallHTC_PlaneWall]]
3. **Why are Ui and Uo different for a cylindrical tube, and which should you use?** → [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/10_HX_OverallHTC_Cylindrical]]
4. **What happens to the temperature profiles when one fluid undergoes phase change?** → [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/05_HX_PhaseChange]]
5. **When does LMTD fail, and what replaces it?** → [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/13_HX_LMTD_vs_NTU]]
6. **How does fouling degrade heat exchanger performance over time?** → [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/12_HX_Fouling]]

---

## Suggested Reading Order

**For first-time study (build understanding bottom-up):**
1. [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/02_HX_Classification]] → [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/03_HX_FlowArrangements]] → [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/04_HX_ShellAndTube]] → [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/05_HX_PhaseChange]]
2. [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/06_HX_EnergyBalance]] → [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/09_HX_OverallHTC_PlaneWall]] → [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/10_HX_OverallHTC_Cylindrical]] → [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/11_HX_OverallHTC_Simplified]]
3. [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/07_HX_LMTD]] → [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/08_HX_LMTD_WorkedExamples]]
4. [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/12_HX_Fouling]] → [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/13_HX_LMTD_vs_NTU]] → [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/14_HX_NTU_Effectiveness]]

**For exam revision (topic-first):**
- Start at [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/01_HeatExchanger_MOC]] and follow cross-cluster links

---

## Source Notes

| Source                                                      | Classification              | Trust  |
| ----------------------------------------------------------- | --------------------------- | ------ |
| MTE 3252 Lecture Slides "HT-5 Heat Exchanger"               | Secondary (course notes)    | Medium |
| Cengel & Ghajar *Heat and Mass Transfer* (implied source)   | Primary (textbook)          | High   |
| Tubular Exchanger Manufacturers Association (fouling table) | Primary (industry standard) | High   |

---

## Dataview Queries

| File                                                                                                                                 | title                                                                         | type   | status    | confidence |
| ------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------- | ------ | --------- | ---------- |
| [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/14_HX_NTU_Effectiveness\|14_HX_NTU_Effectiveness]]           | NTU–Effectiveness Method                                                      | atomic | \-        | medium     |
| [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/13_HX_LMTD_vs_NTU\|13_HX_LMTD_vs_NTU]]                       | LMTD vs NTU Method — When to Use Which                                        | atomic | \-        | high       |
| [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/12_HX_Fouling\|12_HX_Fouling]]                               | Fouling and the Fouling Factor                                                | atomic | \-        | high       |
| [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/11_HX_OverallHTC_Simplified\|11_HX_OverallHTC_Simplified]]   | Overall Heat Transfer Coefficient — Simplified Form and Representative Values | atomic | \-        | high       |
| [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/10_HX_OverallHTC_Cylindrical\|10_HX_OverallHTC_Cylindrical]] | Overall Heat Transfer Coefficient — Cylindrical Geometry (Ui and Uo)          | atomic | \-        | high       |
| [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/09_HX_OverallHTC_PlaneWall\|09_HX_OverallHTC_PlaneWall]]     | Overall Heat Transfer Coefficient — Plane Wall                                | atomic | \-        | high       |
| [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/08_HX_LMTD_WorkedExamples\|08_HX_LMTD_WorkedExamples]]       | LMTD Method — Worked Examples                                                 | atomic | \-        | high       |
| [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/07_HX_LMTD\|07_HX_LMTD]]                                     | Logarithmic Mean Temperature Difference (LMTD)                                | atomic | \-        | high       |
| [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/06_HX_EnergyBalance\|06_HX_EnergyBalance]]                   | Heat Exchanger Energy Balance                                                 | atomic | \-        | high       |
| [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/05_HX_PhaseChange\|05_HX_PhaseChange]]                       | Phase-Change Heat Exchangers (Condensers and Evaporators)                     | atomic | \-        | high       |
| [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/03_HX_FlowArrangements\|03_HX_FlowArrangements]]             | Heat Exchanger Flow Arrangements                                              | atomic | \-        | high       |
| [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/04_HX_ShellAndTube\|04_HX_ShellAndTube]]                     | Shell-and-Tube Heat Exchanger                                                 | atomic | \-        | high       |
| [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/02_HX_Classification\|02_HX_Classification]]                 | Heat Exchanger Classification                                                 | atomic | \-        | high       |
| [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/00_HeatExchanger_Hub\|00_HeatExchanger_Hub]]                 | Heat Exchangers — Hub                                                         | hub    | evergreen | high       |
| [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/01_HeatExchanger_MOC\|01_HeatExchanger_MOC]]                 | Heat Exchangers — Map of Content                                              | MOC    | evergreen | high       |


| File                                                                                                                       | title                    | source                      |
| -------------------------------------------------------------------------------------------------------------------------- | ------------------------ | --------------------------- |
| [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/14_HX_NTU_Effectiveness\|14_HX_NTU_Effectiveness]] | NTU–Effectiveness Method | MTE3252 Lecture Slides HT-5 |


| File                                                                                                                               | title                                                                         |
| ---------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/12_HX_Fouling\|12_HX_Fouling]]                             | Fouling and the Fouling Factor                                                |
| [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/11_HX_OverallHTC_Simplified\|11_HX_OverallHTC_Simplified]] | Overall Heat Transfer Coefficient — Simplified Form and Representative Values |


---

## Backlink Summary
*This is the root hub. All notes link back here.*
*Links to:* [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/01_HeatExchanger_MOC]] and all atomic notes listed above.
