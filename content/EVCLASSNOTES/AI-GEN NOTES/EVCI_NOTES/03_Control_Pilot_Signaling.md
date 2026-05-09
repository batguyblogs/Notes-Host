---
publish: true
title: Control Pilot Signaling
created: 2026-05-09T10:30:22.422+05:30
modified: 2026-05-09T10:22:00.136+05:30
tags:
  - evci
  - standards
  - signaling
cssclasses: ""
---


# Control Pilot (CP) Signaling

**The Control Pilot is a dedicated signal wire that uses a 1 kHz PWM signal to communicate charging state and the maximum available current from the EVSE to the EV.**

## Mechanism / How It Works

The CP signal uses voltage levels to indicate **State** and duty cycle to indicate **Current Limit**.

### State Machine (Voltage Levels)
Measured on the EV side relative to Protective Earth (PE):
- **State A (+12V):** Standby (No vehicle connected).
- **State B (+9V):** Vehicle connected (detected by 2.74 kΩ resistor).
- **State C (+6V):** Vehicle ready to charge (switches in 882 Ω resistor).
- **State D (+3V):** Ventilation required (rare, for lead-acid batteries).
- **State E (0V):** Fault (EVSE error).
- **State F (-12V):** Unavailability/Error.

### Duty Cycle ($D$) to Current ($I_{max}$) Formula
Per IEC 61851-1:
- **For $10\% \le D \le 85\%$:**
  $$I_{max} = D_{\%} \times 0.6\ \text{A}$$
  *(e.g., 50% = 30A)*
- **For $85\% < D \le 96\%$:**
  $$I_{max} = (D_{\%} - 64) \times 2.5\ \text{A}$$
  *(e.g., 96% = 80A)*

## Why It Matters

### Noise Immunity
By using **Duty Cycle** instead of voltage magnitude to communicate current, the system is robust against the high electrical noise (EMI) found in automotive environments.

### Safety Interlock
Energy flow is only permitted in **State C**. If the plug is even slightly withdrawn, the voltage jumps to State B or A, and the EVSE must disconnect power within **100 ms** to prevent arcing.

> [!warning] Exam Trap
> Remember that the duty cycle communicates the **limit** of the EVSE. The vehicle's On-Board Charger (OBC) decides how much current to actually draw, provided it stays *below* this limit.

---
## Backlink Summary
*Linked from:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/02b_EVCI_Standards_Comm_MOC]]
*Links to:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Proximity_Pilot_and_Interlocks]], [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_CCS_Architecture_and_PLC]]
