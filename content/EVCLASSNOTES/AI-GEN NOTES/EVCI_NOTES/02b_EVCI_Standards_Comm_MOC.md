---
publish: true
title: Standards & Communication MOC
created: 2026-05-09
modified: 2026-05-09T10:22:00.127+05:30
tags:
  - MOC
  - evci
  - standards
cssclasses: ""
---


# Standards & Communication MOC

**This layer bridges the physical signaling of the charge port with the complex digital protocols required for smart charging and vehicle-to-grid integration.**

## Thematic Clusters

### 1. The Signaling Foundation
The physical handshake between the car and station is the first line of defense, ensuring a safe connection before any energy flows.
> [!info]
> - [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Control_Pilot_Signaling]] — PWM duty cycle, current advertisement, and state machine.
> - [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Proximity_Pilot_and_Interlocks]] — Cable rating detection and drive-away prevention.

### 2. Standard Frameworks
International and national standards define the physical connector shapes and the communication logic to ensure interoperability.
> [!info]
> - [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_EV_Charging_Standards_IEC_SAE_ISO]] — Detailed breakdown of IEC 61851, SAE J1772, and ISO 15118.
> - [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Indian_Standards_BIS_IS17017]] — Specifics of the Bharat DC-001 and AC-001 standards.

### 3. CCS & Advanced Protocols
The Combined Charging System (CCS) merges AC and DC charging into a single inlet, utilizing high-level PLC communication.
> [!info]
> - [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_CCS_Architecture_and_PLC\|CCS Architecture]] — Physical pins, combo connector advantages.
> - [[03_Power_Line_Communication_PLC]] — How HomePlug Green PHY enables digital handshake over the CP line.

### 4. The Handshake Sequence
A successful session follows a rigid 6-step sequence to ensure safety, authentication, and metered delivery.
> [!info]
> - [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Charging_Sequence_and_Interoperability]] — From detection to orderly shutdown.

## Cross-Cluster Connections

- **[[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Control_Pilot_Signaling]] ↔ [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_EV_Charging_Standards_IEC_SAE_ISO]]**: The CP signal is defined by IEC 61851-1 but is reused as the carrier for ISO 15118 digital packets.
- **[[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_CCS_Architecture_and_PLC]] ↔ [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Proximity_Pilot_and_Interlocks]]**: PP interlocks are mandatory in CCS to prevent high-power DC arcs during hot-unplugging.

## Open Problems / Gaps
- Fragmentation between NACS (Tesla) and CCS1 in North America.
- Latency issues in PLC handshakes affecting the user "Plug & Charge" experience.

---
## Backlink Summary
*Linked from:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/01b_EVCI_Communication_Standards_Hub]]
*Links to:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Control_Pilot_Signaling]], [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Proximity_Pilot_and_Interlocks]], [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_EV_Charging_Standards_IEC_SAE_ISO]], [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Indian_Standards_BIS_IS17017]], [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_CCS_Architecture_and_PLC]], [[03_Power_Line_Communication_PLC]], [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Charging_Sequence_and_Interoperability]]
