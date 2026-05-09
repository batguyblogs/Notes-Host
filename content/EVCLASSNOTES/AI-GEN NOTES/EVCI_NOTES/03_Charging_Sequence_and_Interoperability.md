---
publish: true
title: Charging Sequence and Interoperability
created: 2026-05-09T10:30:22.422+05:30
modified: 2026-05-09T10:22:00.136+05:30
tags:
  - evci
  - standards
  - protocol
cssclasses: ""
---


# Charging Sequence and Interoperability

**The EV charging communication sequence is a structured 6-step handshake protocol ensuring safe, metered, and orderly energy transfer.**

## The 6-Step Sequence (CCS DCFC)

### 1. Initialization & Cable Check
Physical connection detected via CP/PP. The EVSE performs self-tests.

### 2. Communication Setup
PLC (ISO 15118) handshake begins. The vehicle and station negotiate the protocol version and security certificates.

### 3. Isolation Check (Safety Gate)
The station applies a high-voltage test signal to verify there are no ground faults in the cable or vehicle before closing contactors.

### 4. Pre-charge
The station ramps its internal voltage to match the battery voltage (e.g., 400V) to prevent inrush current damage when the vehicle's contactors close.

### 5. Energy Transfer (The Bulk Session)
The vehicle BMS sends continuous "Current Request" messages. The station adjusts its power modules to follow the vehicle's optimal charging curve.

### 6. Orderly Shutdown
Charging current is ramped down to zero. Contactors are opened. Lock is released. The session record (CDR) is sent to the back-end.

## Why It Matters

### Preventing "Hot-Unplugging"
The sequence ensures that pins are never pulled under load, which would cause an arc flash at 400-800V DC.

### Interoperability
By following this exact protocol, a station from Manufacturer A can safely charge a vehicle from Manufacturer B, even if their battery voltages are different.

> [!warning] Source Conflict
> While most standards agree on these 6 steps, the **timing requirements** (e.g., how many milliseconds allowed for shutdown) vary between ISO 15118 and CHAdeMO. Interoperability issues often stem from these sub-second timing mismatches.

---
## Backlink Summary
*Linked from:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/02b_EVCI_Standards_Comm_MOC]], [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_CCS_Architecture_and_PLC]]
*Links to:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Insulation_Monitoring_Safety_Protocol]], [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_HV_Contactors_and_Precharge]]
