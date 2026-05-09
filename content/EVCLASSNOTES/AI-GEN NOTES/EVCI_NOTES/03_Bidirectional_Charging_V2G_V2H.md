---
publish: true
title: Bidirectional Charging (V2G and V2H)
created: 2026-05-09T10:30:22.422+05:30
modified: 2026-05-09T10:22:00.135+05:30
tags:
  - evci
  - operations
  - V2G
cssclasses: ""
---


# Bidirectional Charging (V2G and V2H)

**Bidirectional charging enables an EV to not only draw energy from the grid but also discharge stored energy to power a home (V2H) or support the utility grid (V2G).**

## Mechanism / How It Works

### Hardware Requirements
- **Bidirectional Inverter:** Converts battery DC back to grid-synchronized AC.
- **Four-Quadrant Control:** Power electronics must handle power flow in both directions (Import/Export).
- **Smart Meter:** Must support **Minus Metering** to track exported energy.

### Critical Safety: Anti-Islanding
If the grid goes down, the EV **must** disconnect its export path within **200 ms**.
- **Reason:** To prevent energizing a "dead" grid section where utility workers might be performing repairs.

## Why It Matters

### Grid Resilience
V2G allows EVs to act as a **distributed battery**. They can absorb excess solar during the day and discharge it during the evening peak, providing **Frequency Regulation** and **Peak Shaving** services that stabilize the grid.

### Household Backup
V2H (Vehicle-to-Home) provides energy security during blackouts. A typical 60 kWh EV battery can power a standard house for 3-4 days of emergency use.

> [!note] Battery Health
> Bidirectional use increases the "Cycle Count" of the battery. Modern V2G algorithms use **Shallow Cycles** (e.g., discharging only 10% during peak) to minimize capacity fade.

---
## Backlink Summary
*Linked from:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/02d_EVCI_Safety_Ops_MOC]]
*Links to:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Net_and_Minus_Metering]], [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Demand_Coincidence_and_Peak_Shaving]]
