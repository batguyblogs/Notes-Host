---
publish: true
title: Proximity Pilot and Interlocks
created: 2026-05-09T10:30:22.424+05:30
modified: 2026-05-09T10:22:00.140+05:30
tags:
  - evci
  - standards
  - safety
cssclasses: ""
---


# Proximity Pilot and Interlocks

**The Proximity Pilot (PP) pin serves as a mechanical-to-electrical bridge that prevents vehicle movement and hazardous hot-unplugging during charging.**

## Mechanism / How It Works

The PP pin uses a simple resistor network to provide two independent safety functions.

### 1. Cable Rating Detection
In Type 2 and SAE J1772 cables, a resistor is placed between PP and PE inside the connector. The EVSE measures this resistance to know the current capacity of the cable assembly.
- **1500 $\Omega$:** 13A rated cable.
- **680 $\Omega$:** 20A rated cable.
- **220 $\Omega$:** 32A rated cable.
- **100 $\Omega$:** 63A rated cable.

### 2. Drive-Away Inhibit
Inside the vehicle, the Vehicle Control Unit (VCU) monitors the PP line. If a resistance is detected (indicating a plug is inserted), the VCU **inhibits the drivetrain**. The car will refuse to shift out of "Park" or engage the motor, preventing the driver from accidentally driving away while tethered to the station.

### 3. Safe Disconnection
The connector latch (the button the user presses to release the plug) is electrically coupled to the PP circuit.
- **Latch Pressed:** The PP circuit is broken or its resistance changes.
- **EV Response:** The vehicle immediately ramps current to zero and opens its HV contactors *before* the pins are physically pulled out.
- **Result:** No "Hot-Unplugging" (no DC arc at the connector pins).

## Why It Matters

Without the PP interlock, the two most common causes of charging station damage—**Drive-away incidents** and **Connector pin arcing**—would occur frequently, leading to high maintenance costs and user safety risks.

> [!note] Passive Safety
> The drive-away interlock is a **passive safety mechanism**. It relies on physical hardware presence, making it more reliable than a software-only check.

---
## Backlink Summary
*Linked from:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/02b_EVCI_Standards_Comm_MOC]], [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Control_Pilot_Signaling]]
*Links to:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Control_Pilot_Signaling]]
