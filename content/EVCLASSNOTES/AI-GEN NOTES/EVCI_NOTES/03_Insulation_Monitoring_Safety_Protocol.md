---
publish: true
title: Insulation Monitoring Safety Protocol
created: 2026-05-09T10:30:22.423+05:30
modified: 2026-05-09T10:22:00.140+05:30
tags:
  - evci
  - safety
  - protocol
cssclasses: ""
---


# Insulation Monitoring Safety Protocol

**A robust safety protocol for DC fast charging utilizes dual, independent monitoring by both the vehicle (BMS) and the station (EVSE) to provide defense-in-depth.**

## The Monitoring Sequence

### Phase 1: Pre-Energization Check
Before the station ramps voltage, both sides perform a static isolation test.
- If station $R_{ins} < 500\ \text{k}\Omega \rightarrow$ **Lock Station.**
- If vehicle sends "Isolation Fault" via ISO 15118 $\rightarrow$ **Abort Handshake.**

### Phase 2: Continuous Monitoring
During energy transfer, the Station IMD monitors the entire coupled circuit (Station + Cable + Vehicle).
- **Warning (500k to 100k):** Log warning to CSMS, alert user, but continue charging.
- **Fault (< 100k):** 
	- **Station:** Performs a "Soft Stop" (ramp to 0A, then open contactors).
	- **Vehicle:** Performs a "Hard Stop" (BMS opens HV contactors within 100ms).

## Why It Matters

### Defense-in-Depth
Neither the station nor the car relies solely on the other. If the station's monitor fails to detect a fault in the cable, the vehicle's internal monitor will still catch the leakage to the chassis and terminate the session.

### Nuisance Trip Mitigation
Modern protocols include a **Graduated Resumption**. A single transient fault may trigger a 5-minute lockout and re-test. If the fault persists 3 times in 24 hours, the station is permanently locked until a technician arrives.

---
## Backlink Summary
*Linked from:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/02d_EVCI_Safety_Ops_MOC]], [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Insulation_Monitoring_Methods]]
*Links to:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Charging_Sequence_and_Interoperability]], [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_HV_Contactors_and_Precharge]]
