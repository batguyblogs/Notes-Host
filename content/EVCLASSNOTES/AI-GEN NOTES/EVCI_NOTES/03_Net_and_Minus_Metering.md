---
publish: true
title: Net and Minus Metering
created: 2026-05-09T10:30:22.423+05:30
modified: 2026-05-09T10:22:00.140+05:30
tags:
  - evci
  - grid
  - billing
cssclasses: ""
---


# Net and Minus Metering

**Minus metering is a billing arrangement where energy exported from an EV back to the grid (V2G) is subtracted from the energy imported, facilitating the commercial viability of bidirectional charging.**

## Mechanism / How It Works

A **Bidirectional Smart Meter** is installed at the connection point. It records two separate streams of data:
1. **Import ($E_{in}$):** Energy used to charge the vehicle.
2. **Export ($E_{out}$):** Energy discharged to the grid for frequency regulation or peak support.

### The Calculation
$$\text{Net Billed Energy} = E_{in} - E_{out}$$
- **If Positive:** The customer pays the utility.
- **If Negative:** The customer receives a credit on their bill.

## Why It Matters

### V2G Commercial Viability
Without minus metering, an EV owner exporting energy during a peak window would be charged for that energy as a load or not credited at the same rate, removing the incentive to help the grid.

### Grid Stability
It transforms millions of EVs into a **Virtual Power Plant (VPP)**. By incentivizing discharge during peaks and charging during off-peaks, minus metering helps the utility maintain balance without firing up expensive gas peaking plants.

> [!caution] Time-Sensitive
> Regulation varies significantly by state (in India) and country. Some regions use **Net Billing** (where export is credited at a lower wholesale rate) rather than true **Net Metering** (1:1 swap). Verify local CERC/SERC guidelines.

---
## Backlink Summary
*Linked from:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/02c_EVCI_Infrastructure_MOC]], [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Electricity_Supply_Options]]
*Links to:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Bidirectional_Charging_V2G_V2H]], [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Electricity_Supply_Options]]
