---
publish: true
title: CCS Architecture and PLC
created: 2026-05-09T10:30:22.422+05:30
modified: 2026-05-09T10:22:00.135+05:30
tags:
  - evci
  - standards
  - CCS
cssclasses: ""
---


# CCS Architecture and PLC

**The Combined Charging System (CCS) enables both AC and DC charging using a single vehicle inlet by extending the standard AC connector with two high-power DC pins.**

## Mechanism / How It Works

### Physical Architecture
The CCS Combo connector adds two large DC pins ($DC+$ and $DC-$) below the standard Type 2 (Europe/India) or Type 1 (North America) AC pins.
- **AC Pins:** Used for signaling (CP, PP, PE) and AC power (when charging at home).
- **DC Pins:** Used exclusively for high-power energy transfer (up to 1000V / 500A).

### Power Line Communication (PLC)
While AC charging uses basic PWM signaling on the CP line, DC fast charging requires **High-Level Communication (HLC)**.
- **Protocol:** **HomePlug Green PHY** (broadband over power line).
- **Carrier:** The digital signal is superimposed (multiplexed) onto the **Control Pilot (CP)** line.
- **Significance:** Enables exchange of XML-based messages for authentication, battery limits, and charging schedules per **ISO 15118**.

## Why It Matters

### Single Inlet Design
CCS eliminates the need for separate AC and DC ports on the car, reducing cost, weight, and design complexity for OEMs.

### Advanced Features
PLC communication allows for:
1. **Plug & Charge:** No RFID card needed; the car authenticates itself automatically via the charging cable.
2. **V2G Scheduling:** Grid operators can send pricing or power signals to the vehicle to optimize charging times.

> [!tip] Practical Application
> During a CCS DC session, the AC pins (L1, L2, L3) are inactive. Only CP, PE, and the large DC pins are used for the session.

---
## Backlink Summary
*Linked from:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/02b_EVCI_Standards_Comm_MOC]], [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_EV_Charging_Standards_IEC_SAE_ISO]]
*Links to:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Control_Pilot_Signaling]], [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Charging_Sequence_and_Interoperability]]
