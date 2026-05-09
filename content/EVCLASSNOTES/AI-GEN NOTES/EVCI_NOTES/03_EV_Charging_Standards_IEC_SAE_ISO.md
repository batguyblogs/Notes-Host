---
publish: true
title: EV Charging Standards (IEC, SAE, ISO)
created: 2026-05-09T10:30:22.422+05:30
modified: 2026-05-09T10:22:00.137+05:30
tags:
  - evci
  - standards
  - regulatory
cssclasses: ""
---


# EV Charging Standards (IEC, SAE, ISO)

**International standards provide the unified framework for the physical interface, electrical safety, and digital communication required for global EV interoperability.**

## Key Standards Frameworks

### 1. IEC 61851 (Conductive Charging)
The primary international standard for AC and DC charging.
- **IEC 61851-1:** General requirements (Modes 1-4, CP/PP signaling).
- **IEC 61851-23:** Specific requirements for DC charging stations (up to 1000V).
- **IEC 61851-24:** Digital communication between DC station and EV.

### 2. SAE J1772 (North American Standard)
Published by the Society of Automotive Engineers, this defines the Type 1 connector and the base PWM signaling logic used by nearly all modern standards.

### 3. ISO 15118 (The V2G Standard)
Formally known as "Road vehicles — Vehicle to grid communication interface."
- Enables **Plug & Charge (PnC)** via TLS-encrypted certificates.
- Facilitates **Smart Charging** (power schedules) and **V2G/V2H** energy discharge.

## Comparison of Standards

| Standard | Region | Connector | Communication |
| --- | --- | --- | --- |
| **CCS1** | North America | Type 1 Combo | PLC (ISO 15118) |
| **CCS2** | Europe / India | Type 2 Combo | PLC (ISO 15118) |
| **CHAdeMO** | Japan | CHAdeMO | CAN Bus |
| **GB/T** | China | GB/T | CAN Bus |

## Why It Matters

Standards prevent **Infrastructure Fragmentation**. Without them, an EV from one manufacturer could not charge at a station from another, similar to how mobile phone chargers were non-interchangeable before USB-C.

> [!caution] Time-Sensitive
> These standards are evolving. **ISO 15118-20** (published ~2022) is the current state-of-the-art, adding support for wireless charging and advanced bidirectional features. Verify version compliance for new projects.

---
## Backlink Summary
*Linked from:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/02b_EVCI_Standards_Comm_MOC]]
*Links to:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Indian_Standards_BIS_IS17017]], [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_CCS_Architecture_and_PLC]]
