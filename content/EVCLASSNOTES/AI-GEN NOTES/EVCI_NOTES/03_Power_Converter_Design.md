---
publish: true
title: Power Converter Design
created: 2026-05-09T10:30:22.424+05:30
modified: 2026-05-09T10:22:00.140+05:30
tags:
  - evci
  - hardware
  - converters
cssclasses: ""
---


# Power Converter Design

**DC fast chargers utilize a two-stage power conversion architecture: a front-end AC-DC stage for power factor correction and a back-end DC-DC stage for isolated battery charging.**

## Mechanism / How It Works

### Stage 1: Front-End AC-DC
- **Purpose:** Converts grid AC (415V 3-phase) to a high-voltage DC bus (700-800V).
- **Topology:** **Active Front End (AFE)** or **Vienna Rectifier**.
- **Key Requirement:** **Power Factor Correction (PFC)** to ensure input current THD < 5% per IEC 61000-3-12.

### Stage 2: Back-End DC-DC
- **Purpose:** Steps the 800V DC bus down (or up) to match the battery's specific voltage (200-1000V).
- **Topology:** **LLC Resonant Converter** or **Dual Active Bridge (DAB)**.
- **Key Feature:** **Galvanic Isolation** provided by a high-frequency transformer.

## Why It Matters

### Efficiency & Thermal Management
System efficiency ($\eta_{total}$) determines the cooling requirement.
$$\eta_{total} = \eta_{AC\text{-}DC} \times \eta_{DC\text{-}DC} \approx 0.98 \times 0.97 = 0.95$$
A 150 kW station at 95% efficiency generates **7.5 kW of heat**, which must be removed via active air or liquid cooling.

### Bidirectional Power Flow
For **Vehicle-to-Grid (V2G)**, both stages must be bidirectional. The DAB topology is preferred for the DC-DC stage as it naturally allows power to flow back to the DC bus.

> [!note] SiC vs Si
> **Silicon Carbide (SiC)** MOSFETs allow switching at >100 kHz (vs 10-20 kHz for Silicon IGBTs). This reduces the size of the high-frequency transformer and inductors, enabling higher energy density.

---
## Backlink Summary
*Linked from:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/02a_EVCI_Hardware_MOC]]
*Links to:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Totem_Pole_PFC_Topology]], [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_DC_Power_Modules_and_Architecture]]
