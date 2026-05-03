---
publish: true
title: Shell-and-Tube Heat Exchanger
created: 2026-05-03T10:20:50.458+05:30
modified: 2026-05-03T10:36:00.445+05:30
tags:
  - heat-exchanger
  - MTE3252
  - shell-and-tube
  - atomic
cssclasses: ""
---


# Shell-and-Tube Heat Exchanger

**The shell-and-tube heat exchanger is the most widely used type in industrial applications, consisting of a bundle of tubes packed inside a cylindrical shell, with one fluid flowing inside the tubes and the other flowing over the tubes through the shell.**

---

## Definition

A shell-and-tube heat exchanger achieves heat transfer between two fluid streams using a large number of tubes (sometimes several hundred) arranged with their axes parallel to that of the outer shell. The large number of tubes provides substantial surface area in a compact volume.

---

## Mechanism / How It Works

### Basic Structure

```
  Tube outlet          Shell inlet         Baffles
      │                    │                  │ │ │
      ▼            ┌───────▼──────────────────┴─┴─┴──────┐
  ╔═══╧═══╗        │  ←──────── shell-side fluid ───────  │
  ║       │====|   │  ┌────────────────────────────────┐  │
  ║       │====|   │  │→→→→→ tube-side fluid →→→→→→→→│  │
  ║       │====|   │  └────────────────────────────────┘  │
  ╚═══╤═══╝        │  ←────────────────────────────────   │
      │            └─────────────────────────────────────┘
  Tube inlet              Shell outlet         Tube inlet
```

**Key components:**
- **Tubes**: The primary heat transfer surface. Tube-side fluid flows inside.
- **Shell**: The outer pressure vessel. Shell-side fluid flows around the tubes.
- **Baffles**: Transverse plates that force the shell-side fluid to flow *across* (not along) the tube bundle. This increases turbulence, improves the shell-side heat transfer coefficient $h_o$, and maintains uniform tube spacing.
- **Front-end and rear-end headers**: Distribute tube-side fluid into/out of the tubes.

### Pass Configurations

The exchanger is classified by the number of shell passes and tube passes:

**One-shell pass, one-tube pass (1-1)**
- Fluid enters one end of the shell and exits the other
- Tubes run straight through — simplest configuration
- Flow can be arranged as parallel or counter-flow

**One-shell pass, two-tube passes (1-2)**
- Tubes make a U-turn inside the shell
- Tube-side fluid traverses the shell length **twice**
- Produces a mixed flow pattern (partially counter, partially parallel)

**Two-shell passes, four-tube passes (2-4)**
- Shell-side fluid makes two passes; tube-side fluid makes four passes
- Closer approximation to true counter-flow behaviour
- Higher pressure drop but better thermal performance

> [!note] Pass Notation
> The notation "N-shell passes / M-tube passes" always means total passes, not passes per shell. A 1-2 exchanger has one shell journey for the shell fluid and two tube journeys for the tube fluid.

---

## Key Details

### Why Baffles Matter

Without baffles, the shell-side fluid would flow parallel to the tubes (low turbulence, low $h_o$). Baffles force cross-flow, which:
1. Increases the shell-side convection coefficient $h_o$
2. Prevents tube vibration and maintains structural spacing
3. Creates a more tortuous path, increasing residence time

> [!warning]
> Baffles also increase pressure drop on the shell side. This is a design trade-off: better heat transfer vs. higher pumping power required.

### Relation to Flow Arrangements

| Configuration | Approximate flow behaviour |
|---|---|
| 1-1 | True parallel or counter flow |
| 1-2 | Mixed — neither pure parallel nor counter |
| 2-4, 4-8, etc. | Approaches counter flow as passes increase |

For 1-2 and higher configurations, the true LMTD must be corrected by a factor $F$: $\Delta T_m = F \cdot \Delta T_{lm,CF}$, where $\Delta T_{lm,CF}$ is the counter-flow LMTD. See [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/07_HX_LMTD]] for the LMTD derivation.

---

## Why It Matters

Shell-and-tube exchangers dominate industry because they are robust, cleanable, pressure-resistant, and scalable. The cylindrical geometry means that the inner and outer surface areas of the tubes differ — this is why the overall heat transfer coefficient $U$ must be referenced to a specific area. See [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/10_HX_OverallHTC_Cylindrical]] for the full derivation of $U_i$ and $U_o$.

> [!example]
> In an oil refinery, crude oil (high fouling potential) is typically placed on the tube side because tubes are easier to clean mechanically. The cleaner process stream goes on the shell side. This practical decision links directly to the fouling analysis in [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/12_HX_Fouling]].

---

## Connections to Other Notes

The cylindrical tube geometry here underpins the derivation of $U_i$ and $U_o$ in [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/10_HX_OverallHTC_Cylindrical]]. The pass configuration determines the effective flow arrangement, which feeds into [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/03_HX_FlowArrangements]] and the LMTD calculation in [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/07_HX_LMTD]].

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/00_HeatExchanger_Hub]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/01_HeatExchanger_MOC]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/02_HX_Classification]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/03_HX_FlowArrangements]]
*Links to:* [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/07_HX_LMTD]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/10_HX_OverallHTC_Cylindrical]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/12_HX_Fouling]]
