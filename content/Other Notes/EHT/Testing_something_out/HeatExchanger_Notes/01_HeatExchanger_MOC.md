---
publish: true
title: Heat Exchangers — Map of Content
created: 2025-05-03
modified: 2026-05-03T10:29:38.151+05:30
tags:
  - MOC
  - heat-exchanger
  - MTE3252
  - thermal-engineering
cssclasses: ""
---


# Heat Exchangers — Map of Content

This MOC synthesises the four major conceptual clusters in heat exchanger theory. Use it as a navigation layer — each cluster paragraph explains *how* the ideas connect, not just what they are.

---

## Cluster A: Types and Configurations

The classification of heat exchangers is not merely a taxonomy exercise — the physical configuration directly determines what analysis method applies. The most fundamental split is between **direct-contact** exchangers (fluids mix, thermodynamically simple but requiring identical fluid types) and **indirect** exchangers, which dominate industry. Among indirect types, **recuperators** — where hot and cold fluids flow simultaneously separated by a wall — are the standard modern form, and all quantitative analysis in this course applies to them. Within recuperators, the **flow arrangement** (parallel, counter, cross-flow) is the single most important design choice: it governs the temperature profiles and thus the driving force for heat transfer. The **shell-and-tube** exchanger is the dominant industrial recuperator, and its pass configuration (1-shell/1-tube, 1-shell/2-tube, etc.) is a practical realisation of these flow arrangements. Finally, **phase-change** exchangers (condensers and evaporators) are a special limiting case where one fluid's heat capacity rate becomes effectively infinite — a fact that profoundly simplifies both analysis and the temperature profile shape.

> [!info] Notes in this cluster
> [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/02_HX_Classification]] | [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/03_HX_FlowArrangements]] | [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/04_HX_ShellAndTube]] | [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/05_HX_PhaseChange]]

---

## Cluster B: Thermal Analysis Foundations

Before any design formula can be applied, you must establish the **energy balance** — the statement that heat lost by the hot fluid equals heat gained by the cold fluid (assuming adiabatic operation and negligible kinetic/potential energy changes). This gives the fundamental relation $\dot{m}_h c_{ph}(T_{h1}-T_{h2}) = \dot{m}_c c_{pc}(T_{c2}-T_{c1})$, which lets you find any unknown temperature if three are known. The challenge is then to connect this bulk energy exchange to the *local* heat transfer driving force. Since temperature difference varies along the exchanger length, a simple arithmetic mean is incorrect — the correct mean is the **Logarithmic Mean Temperature Difference (LMTD)**. The LMTD formula takes a different form for parallel and counter-flow because the terminal temperature differences $\Delta T_1$ and $\Delta T_2$ are defined differently: in parallel flow both endpoint differences are on the same side, while in counter-flow they cross. This is why counter-flow always produces a larger LMTD for the same inlet/outlet temperatures — it maintains a more uniform driving force along the entire length.

> [!info] Notes in this cluster
> [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/06_HX_EnergyBalance]] | [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/07_HX_LMTD]] | [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/08_HX_LMTD_WorkedExamples]]

---

## Cluster C: Overall Heat Transfer Coefficient

The parameter $U$ (overall heat transfer coefficient, W/m²°C) encapsulates the entire thermal resistance path between the two fluid streams: inner convection → wall conduction → outer convection. It is the heat exchanger equivalent of a lumped thermal conductance. The key insight is that these resistances are **in series**, so the weakest link (highest resistance) dominates — a very poor $h$ on one side will drag down $U$ regardless of how good the other side is. For a plane wall the analysis is straightforward. For a **cylindrical tube** (the real case in shell-and-tube exchangers), the inner and outer surface areas differ, which means $U_i \neq U_o$ — they are different numbers referring to different areas, but $U_i A_i = U_o A_o$ always holds. This makes $U$ meaningless unless the reference area is stated. When wall thickness is small and thermal conductivity is high (thin metal tubes), the wall resistance can be neglected and $U$ simplifies to $U = h_i h_o / (h_i + h_o)$. Representative values of $U$ span three orders of magnitude across different fluid pairings, from ~10 W/m²°C for gas-to-gas up to ~8500 W/m²°C for feedwater heaters.

> [!info] Notes in this cluster
> [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/09_HX_OverallHTC_PlaneWall]] | [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/10_HX_OverallHTC_Cylindrical]] | [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/11_HX_OverallHTC_Simplified]]

---

## Cluster D: Design Methods and Degradation

With $U$ and LMTD known, the master design equation $Q = UA\Delta T_m$ closes the problem. The **LMTD method** is the natural tool when all four temperatures are specified and area is the unknown (sizing problem). Its procedure is systematic: find unknown temperatures via energy balance → compute LMTD → find U → solve for A. However, when the exchanger is already built (area known) and you need to find *outlet temperatures*, LMTD requires tedious iteration because $\Delta T_m$ depends on the very temperatures you are trying to find. The **ε–NTU method** eliminates this by recasting the problem in terms of dimensionless groups: effectiveness $\varepsilon$ (ratio of actual to maximum possible heat transfer) and NTU (Number of Transfer Units, $= UA/C_{min}$). In real exchangers, performance degrades over time due to **fouling** — the deposition of scales, sediments, or biological matter on heat transfer surfaces. Fouling adds thermal resistance and is characterised by a fouling factor $R_f$ (m²K/W) which inflates the denominator of the U expression. Since $R_f$ cannot be calculated theoretically, it must be determined experimentally or taken from standard tables.

> [!info] Notes in this cluster
> [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/12_HX_Fouling]] | [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/13_HX_LMTD_vs_NTU]] | [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/14_HX_NTU_Effectiveness]]

---

## Cross-Cluster Connections

- [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/02_HX_Classification]] ↔ [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/03_HX_FlowArrangements]]: The recuperator type is defined by its flow arrangement — classification and flow direction are inseparable.
- [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/03_HX_FlowArrangements]] ↔ [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/07_HX_LMTD]]: The definition of $\Delta T_1$ and $\Delta T_2$ changes depending on whether flow is parallel or counter — flow arrangement feeds directly into the LMTD calculation.
- [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/05_HX_PhaseChange]] ↔ [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/14_HX_NTU_Effectiveness]]: When one fluid undergoes phase change ($C \to \infty$), it becomes the $C_{max}$ fluid, the capacity ratio $C^* = C_{min}/C_{max} \to 0$, and the NTU–ε relations simplify dramatically.
- [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/06_HX_EnergyBalance]] ↔ [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/07_HX_LMTD]]: The energy balance must be solved first to find any unknown temperatures before LMTD can be computed.
- [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/09_HX_OverallHTC_PlaneWall]] ↔ [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/10_HX_OverallHTC_Cylindrical]]: The plane wall case is the conceptual foundation; the cylindrical case extends it with the area asymmetry correction.
- [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/11_HX_OverallHTC_Simplified]] ↔ [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/12_HX_Fouling]]: The clean $U$ expression becomes the dirty $U$ by adding fouling resistance terms to the denominator.
- [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/13_HX_LMTD_vs_NTU]] ↔ [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/08_HX_LMTD_WorkedExamples]]: The limitations of LMTD exposed by worked examples motivate the NTU method.

---

## Open Problems / Gaps

> [!question] Gap 1 — LMTD Correction Factor F
> For multi-pass shell-and-tube and cross-flow exchangers, pure counter-flow LMTD must be corrected by a factor F (< 1): $\Delta T_m = F \cdot \Delta T_{lm,CF}$. This is not covered in the lecture slides — consult the textbook for F-factor charts.

> [!question] Gap 2 — NTU–ε Relations for All Configurations
> The slides introduce the ε–NTU concept but do not provide the full set of analytical expressions for different flow configurations. These closed-form relations are needed for problem solving.

> [!question] Gap 3 — First Principles Derivation of LMTD
> The LMTD formula is presented as a result; its derivation from a differential energy balance on an elemental slice $dA$ of the exchanger is not shown in the slides.

> [!question] Gap 4 — Pressure Drop Considerations
> Heat exchanger design always involves a thermal–hydraulic trade-off: increasing surface area or using baffles improves heat transfer but raises pressure drop (pumping cost). This topic is absent from the slides.

> [!question] Gap 5 — Fouling Mitigation Strategies
> The slides describe fouling and quantify its effect, but do not discuss how to minimise it (surface coatings, flow velocity control, periodic cleaning). This is covered in engineering handbooks.

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/00_HeatExchanger_Hub]]
*Links to:* All 13 atomic notes listed above
