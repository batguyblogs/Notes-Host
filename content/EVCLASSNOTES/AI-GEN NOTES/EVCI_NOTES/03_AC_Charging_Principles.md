---
publish: true
title: AC Charging Principles (Level 1 and 2)
created: 2026-05-09T10:30:22.421+05:30
modified: 2026-05-09T10:22:00.135+05:30
tags:
  - evci
  - standards
  - AC
cssclasses: ""
---


# AC Charging Principles (Level 1 and 2)

**In AC charging, the EVSE acts as a smart switch providing a controlled grid supply, while the vehicle's On-Board Charger (OBC) performs the actual AC-to-DC conversion.**

## Mechanism / How It Works

The defining characteristic of AC charging is that the **Power Electronics** reside inside the vehicle. The EVSE is responsible only for safety interlocks, metering, and current limits.

### Level 1 AC Charging
- **Supply:** Standard domestic socket (120V US / 230V India).
- **Power:** **1.4 kW to 3.3 kW**.
- **Limitations:** Very slow (40-50 hours for a full BEV recharge). Best suited for PHEVs or emergency top-ups.

### Level 2 AC Charging
- **Supply:** Dedicated 230V single-phase or 415V three-phase circuit.
- **Power:** **7.4 kW (1-phase)** or **22 kW (3-phase)**.
- **Applications:** Home overnight charging and workplace parking. This is the primary charging method for >80% of EV users.

## Why It Matters

### Infrastructure Cost
Level 2 EVSEs are significantly cheaper than DC fast chargers because they do not contain expensive power modules or high-frequency transformers.

### Vehicle Constraints
The charging speed is limited by the vehicle's **OBC Rating**. If a car has a 7 kW OBC, it will only draw 7 kW even if plugged into a 22 kW charger.

> [!warning] Exam Trap
> AC charging uses the **Control Pilot (CP)** signal to tell the car the limit, but the car's OBC determines the actual power flow. In DC charging, the **Station** controls the power flow.

---
## Backlink Summary
*Linked from:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/02b_EVCI_Standards_Comm_MOC]]
*Links to:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Control_Pilot_Signaling]], [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_CCS_Architecture_and_PLC]]
