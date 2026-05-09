---
publish: true
title: Electricity Supply Options
created: 2026-05-09T10:30:22.422+05:30
modified: 2026-05-09T10:22:00.137+05:30
tags:
  - evci
  - grid
  - planning
cssclasses: ""
---


# Electricity Supply Options

**Station operators have three primary arrangements for sourcing power: existing building supply, dedicated new grid connections, or captive renewable generation.**

## Comparison of Options

| Option | Description | Best For | Pros/Cons |
| --- | --- | --- | --- |
| **Existing Connection** | Drawing from the building's current LV board. | Private homes, small offices. | **Pro:** Zero setup cost. **Con:** Limited headroom; risk of tripping main breakers. |
| **New Dedicated Connection** | A separate meter and cable from the utility (DISCOM). | Public charging hubs, high-power DCFC. | **Pro:** High capacity; separate EV tariff. **Con:** High CAPEX; 6-12 month lead time. |
| **Captive Renewable** | On-site Solar PV + Battery Energy Storage (BESS). | Remote locations, sustainability-focused fleets. | **Pro:** Lowest running cost; zero grid stress. **Con:** Highest initial investment. |

## Selection Criteria

The choice depends on the **Demand Factor ($DF$):**
$$P_{available} = (I_{rated} - I_{peak\text{-}load}) \times V \times \sqrt{3}$$
If $P_{required} > P_{available}$, a new connection is mandatory.

## Why It Matters

Infrastructure costs can represent **30-50%** of the total project cost for a public charging hub. Choosing the wrong supply option can either bottleneck growth (existing supply) or create a non-viable business case due to excessive upfront costs (dedicated connection in a low-utilization area).

> [!tip] Hybrid Approach
> The most resilient model for public fast-charging is a **Dedicated Connection + Captive Solar**. The grid provides reliability, while the solar reduces the peak demand charges and energy costs during daylight hours.

---
## Backlink Summary
*Linked from:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/02c_EVCI_Infrastructure_MOC]]
*Links to:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Urban_Charging_Network_Planning]], [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Net_and_Minus_Metering]]
