---
publish: true
title: Heat Exchanger Flow Arrangements
created: 2026-05-03T10:20:50.458+05:30
modified: 2026-05-03T10:34:38.327+05:30
tags:
  - heat-exchanger
  - MTE3252
  - flow-arrangement
  - parallel-flow
  - counter-flow
  - cross-flow
  - atomic
cssclasses: ""
---


# Heat Exchanger Flow Arrangements

**The flow arrangement of a recuperative heat exchanger — whether hot and cold fluids travel in the same direction, opposite directions, or perpendicular to each other — fundamentally determines the temperature profiles along the exchanger length and therefore the mean driving force for heat transfer.**

---

## Definition

Flow arrangement describes the relative direction of the hot and cold fluid streams inside a recuperative heat exchanger. The three primary types are parallel flow, counter flow, and cross flow.

---

## Mechanism / How It Works

### 1. Parallel Flow

Both hot and cold fluids enter at the **same end** and travel in the **same direction**.

```
Hot in (Th1) ──────────────────────► Hot out (Th2)
             ════════════════════
Cold in (Tc1) ──────────────────────► Cold out (Tc2)
```

Temperature profile: Hot fluid temperature drops steeply at first (large ΔT near inlet), then flattens as temperatures converge. The cold fluid rises sharply then levels off. Both streams approach a common intermediate equilibrium temperature asymptotically. **The outlet cold temperature can never exceed the outlet hot temperature.**

Temperature differences for LMTD (see [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/07_HX_LMTD]]):
$$\Delta T_1 = T_{h1} - T_{c1} \quad \text{(inlet end)}$$
$$\Delta T_2 = T_{h2} - T_{c2} \quad \text{(outlet end)}$$

### 2. Counter Flow

Hot and cold fluids enter at **opposite ends** and travel in **opposite directions**.

```
Hot in (Th1) ──────────────────────► Hot out (Th2)
             ════════════════════
Cold out (Tc2) ◄─────────────────── Cold in (Tc1)
```

Temperature profile: Hot fluid drops gradually along the length; cold fluid rises gradually. The temperature difference between the two streams remains much more **uniform** along the length, maintaining a sustained driving force.

Temperature differences for LMTD:
$$\Delta T_1 = T_{h1} - T_{c2} \quad \text{(hot-inlet end)}$$
$$\Delta T_2 = T_{h2} - T_{c1} \quad \text{(hot-outlet end)}$$

> [!note] Critical Difference
> In counter flow, the cold fluid outlet temperature $T_{c2}$ can exceed the hot fluid outlet temperature $T_{h2}$ — something that is physically impossible in parallel flow. This is the key advantage: more complete heat recovery is achievable.

### 3. Cross Flow

The two fluids flow **perpendicular** to each other. This is the standard arrangement in compact heat exchangers (e.g., car radiators, air conditioning coils).

Cross flow is further divided:

| Type | Description | Effect |
|---|---|---|
| **Unmixed** | Plate fins force fluid into fixed channels — cannot spread transversely | Each stream has a temperature gradient in both flow and transverse directions |
| **Mixed** | No fins — fluid free to mix transversely | Temperature is uniform across the width at any cross-section |

> [!note]
> The presence or absence of mixing significantly affects the LMTD correction factor $F$ used for cross-flow exchangers. The LMTD for cross-flow is calculated using counter-flow LMTD multiplied by a correction factor $F < 1$.

> [!caution] Low Confidence
> The correction factor F charts for cross-flow are not covered in the provided lecture slides. This is based on general heat transfer knowledge — verify against your textbook (Cengel Ch. 11) before using in assessments.

---

## Key Details: Comparison of Parallel vs Counter Flow

| Property | Parallel Flow | Counter Flow |
|---|---|---|
| Outlet $T_c$ relative to outlet $T_h$ | Always $T_{c2} < T_{h2}$ | Can have $T_{c2} > T_{h2}$ |
| Temperature uniformity along length | Poor (large ΔT at inlet, small at outlet) | Good (more uniform ΔT throughout) |
| LMTD for same inlet/outlet temps | Lower | Higher |
| Heat transfer area required | Larger (lower driving force) | Smaller (higher driving force) |
| Practical use | Where uniform temperature exposure is needed; simpler connections | Preferred for maximum efficiency |

> [!warning] Exam Trap
> When calculating LMTD, the formulas for $\Delta T_1$ and $\Delta T_2$ are **different** for parallel and counter flow. Mixing them up is one of the most common errors. Always draw the temperature profile diagram first to identify which end is which. See [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/07_HX_LMTD]] for the full derivation.

---

## Why It Matters

Counter flow is almost always thermodynamically superior. For the same inlet and outlet temperatures, a counter-flow exchanger has a higher LMTD, which means a smaller required area (cheaper, more compact). In practice, shell-and-tube exchangers with multiple tube passes (see [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/04_HX_ShellAndTube]]) approximate counter-flow behaviour.

---

## Connections to Other Notes

The flow arrangement directly sets up the LMTD calculation in [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/07_HX_LMTD]]. The shell-and-tube exchanger in [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/04_HX_ShellAndTube]] achieves different flow arrangements through pass configurations. The phase-change special case in [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/05_HX_PhaseChange]] renders flow direction irrelevant because one fluid's temperature is constant.

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/00_HeatExchanger_Hub]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/01_HeatExchanger_MOC]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/02_HX_Classification]]
*Links to:* [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/04_HX_ShellAndTube]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/05_HX_PhaseChange]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/07_HX_LMTD]]
