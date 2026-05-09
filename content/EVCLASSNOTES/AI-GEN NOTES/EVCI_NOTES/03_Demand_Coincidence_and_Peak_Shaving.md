---
publish: true
title: Demand Coincidence and Peak Shaving
created: 2026-05-09T10:30:22.422+05:30
modified: 2026-05-09T10:22:00.136+05:30
tags:
  - evci
  - grid
  - demand-management
cssclasses: ""
---


# Demand Coincidence and Peak Shaving

**Demand coincidence refers to the overlapping of EV charging loads with existing grid peak periods, necessitating peak shaving strategies to prevent network failure.**

## Mechanism / How It Works

### The Coincidence Problem
Without management, EV users plug in as soon as they return home from work (typically 18:00). This creates a massive spike in demand precisely when the residential grid is already at its limit.

### Peak Shaving Strategies
1. **Managed Charging (V1G):** The station or vehicle limits the charging power based on a signal from the utility (e.g., reducing 7.4 kW to 3.3 kW during peak).
2. **Scheduled Charging:** Users set a timer to begin charging at 02:00 AM when demand is lowest.
3. **Local Storage (BESS):** Using on-site batteries to "buffer" the grid. The BESS charges slowly from the grid during the day and discharges rapidly into the EV during charging sessions.

## Why It Matters

Peak shaving allows utilities to **defer capital expenditure (CAPEX)**. If the peak can be flattened, the existing transformers can serve 2-3x more EVs without needing an upgrade.

> [!example] Numerical Case
> A 100 kVA transformer serving 30 houses has ~30 kVA of headroom. 
> - **Unmanaged:** 5 EVs charging at 7.4 kW = 37 kW (Overload).
> - **Managed:** 10 EVs charging at 3 kW = 30 kW (Within limits).

> [!tip] Practical Application
> Utilities use **ToU (Time-of-Use) Tariffs** to incentivize this behavior. Offering a 50% discount on electricity between 12:00 AM and 05:00 AM effectively shifts the bulk of the charging load away from the peak.

---
## Backlink Summary
*Linked from:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/02c_EVCI_Infrastructure_MOC]], [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Grid_Distribution_Impacts]]
*Links to:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Grid_Distribution_Impacts]], [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Bidirectional_Charging_V2G_V2H]]
