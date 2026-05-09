---
publish: true
title: Grid Distribution Impacts
created: 2026-05-09T10:30:22.423+05:30
modified: 2026-05-09T10:22:00.138+05:30
tags:
  - evci
  - grid
  - utilities
cssclasses: ""
---


# Grid Distribution Impacts

**EV charging introduces a qualitatively different load profile characterized by high power density and geographic clustering that stresses the distribution network in multiple dimensions.**

## Key Stress Factors

### 1. Transformer Overloading
Distribution transformers were sized for residential/commercial loads with a moderate growth factor. 
- **The Problem:** 20 households adding a 7.4 kW Level 2 charger adds ~148 kW of demand. 
- **The Result:** Accelerated insulation aging. Per the Arrhenius relationship, a **$8^\circ\text{C}$ rise** above the rated temperature reduces transformer life by **50%**.

### 2. Voltage Profile Degradation
Concentrated charging at the end of long Low-Voltage (LV) feeders causes significant voltage drops ($V_{drop}$).
$$V_{drop} = I \times (R \cos\phi + X \sin\phi) \times L$$
*Where $L$ is feeder length and $\phi$ is power factor angle.*
- **Impact:** OBCs become less efficient at low voltage and may eventually shut down due to undervoltage protection.

### 3. Harmonic Distortion
Power electronics in chargers draw non-sinusoidal current, injecting harmonics into the grid.
- **Impact:** Overheating of neutral conductors and interference with frequency-based protection relays.

## Why It Matters

Utilities must move from **Reactive Upgrades** (replacing a failed transformer) to **Strategic Planning** (forecasting EV hotspots). Strategic planning reduces the cost ratio of upgrades from 5:1 to nearly 1:1 by aligning infrastructure spend with actual adoption rates.

> [!note] Demand Coincidence
> EVs are statistically charged between 18:00–22:00, exactly coinciding with the residential evening peak. This "double peak" is the primary driver for requiring **Smart Charging** and **Time-of-Use (ToU)** tariffs.

---
## Backlink Summary
*Linked from:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/02c_EVCI_Infrastructure_MOC]]
*Links to:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Demand_Coincidence_and_Peak_Shaving]], [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Urban_Charging_Network_Planning]]
