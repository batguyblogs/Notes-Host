---
publish: true
title: Hardware Map of Content
created: 2026-05-09
modified: 2026-05-09T10:22:00.127+05:30
tags:
  - MOC
  - evci
  - hardware
cssclasses: ""
---


# Hardware Map of Content (MOC)

**This layer synthesizes the fundamental engineering principles of EV charging hardware, ranging from the atomic behavior of semiconductor switches to the system-level modularity of fast-charging stations.**

## Thematic Clusters

### 1. Fundamental Switching & Transients
At the core of all power electronics is the switching device. The transition from an ideal model to real-world behavior involves managing parasites and thermal constraints.
> [!info]
> - [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Ideal_Switch_Characteristics]] — Ideal vs Real models, conduction vs switching losses.
> - [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Factors_Influencing_Switch_Transients]] — Gate drive, stray inductance, and $dV/dt$ effects.

### 2. High-Voltage Safety Mechanisms
Connecting a battery to an inverter requires precise sequencing to prevent catastrophic inrush currents and contact welding.
> [!info]
> - [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_HV_Contactors_and_Precharge]] — The role of main and pre-charge contactors in galvanic isolation.
> - [[03_Precharge_Calculation_and_Sequence]] — The physics of $\frac{1}{2}CV^2$ energy absorption and timing.

### 3. Power Conversion Topologies
Modern chargers utilize two-stage conversion to maintain grid quality (PFC) while providing isolated DC to the battery.
> [!info]
> - [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Power_Converter_Design]] — AC/DC and DC/DC stages, SiC vs Si comparisons.
> - [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Totem_Pole_PFC_Topology]] — Bridgeless PFC for high-efficiency on-board chargers.

### 4. Modular Fast-Charging Architecture
To achieve power levels above 150 kW, stations move from single large units to parallel power modules.
> [!info]
> - [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_DC_Power_Modules_and_Architecture]] — Scaling via modules, N+1 redundancy, and liquid cooling.

## Cross-Cluster Connections

- **[[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Ideal_Switch_Characteristics]] ↔ [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Power_Converter_Design]]**: The switching frequency limits of real devices dictate the size and topology of the converter magnetics.
- **[[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_HV_Contactors_and_Precharge]] ↔ [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_DC_Power_Modules_and_Architecture]]**: Each power module requires its own protection, but the central system manages the main contactor sequence for the vehicle.

## Open Problems / Gaps
- Thermal limits of air-cooling in high-ambient urban environments.
- Long-term reliability of SiC modules under frequent fast-cycling conditions.

---
## Backlink Summary
*Linked from:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/01a_EVCI_Systems_Hardware_Hub]]
*Links to:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Ideal_Switch_Characteristics]], [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Factors_Influencing_Switch_Transients]], [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_HV_Contactors_and_Precharge]], [[03_Precharge_Calculation_and_Sequence]], [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Power_Converter_Design]], [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Totem_Pole_PFC_Topology]], [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_DC_Power_Modules_and_Architecture]]
