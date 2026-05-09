---
publish: true
title: Urban Charging Network Planning
created: 2026-05-09T10:30:22.424+05:30
modified: 2026-05-09T10:22:00.141+05:30
tags:
  - evci
  - grid
  - design
cssclasses: ""
---


# Urban Charging Network Planning

**Planning an urban public network requires synthesizing daily energy demand from multiple vehicle segments to determine transformer sizing and power distribution schemes.**

## Design Methodology

### Step 1: Demand Aggregation
Total connected power ($P_{total}$) is calculated by identifying the number of units required to meet daily kWh demand within a specific window (typically 8 hours).

### Step 2: Transformer Sizing ($S_{required}$)
To ensure the transformer isn't undersized, we apply a **Demand Factor ($DF$)** and a **Power Factor ($PF$)**.
$$S_{required} = \frac{P_{total}}{PF \times DF}$$
*Standard assumptions: $PF = 0.9$, $DF = 0.85$ (not all chargers at max simultaneously).*

### Step 3: Cable & Protection Sizing
Cables must be sized for **125% of continuous load** to prevent overheating in urban conduit banks.

## Worked Example: Mixed Hub
**Inputs:**
- 2W Demand: 100 kWh/day ($\rightarrow 4$ units of 3.3 kW)
- 3W Demand: 350 kWh/day ($\rightarrow 6$ units of 7.4 kW)
- 4W Commercial: 500 kWh/day ($\rightarrow 2$ units of 50 kW)

**Resulting Peak Power:** $13.2 + 44.4 + 100 = 157.6\ \text{kW}$.
**Selected Transformer:** **250 kVA** (providing a ~15% growth margin).

## Why It Matters

Proper planning prevents **Transformer Failure** and **Voltage Drop** issues. In high-density urban areas, the cost of digging up roads to replace an undersized cable is 10x higher than the cost of sizing it correctly during the initial installation.

---
## Backlink Summary
*Linked from:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/02c_EVCI_Infrastructure_MOC]], [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Grid_Distribution_Impacts]], [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Electricity_Supply_Options]]
*Links to:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Grid_Distribution_Impacts]], [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Site_Planning_Guidelines]], [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Indian_Standards_BIS_IS17017]]
