---
publish: true
title: Inductive Charging (Static and Dynamic)
created: 2026-05-09T10:30:22.423+05:30
modified: 2026-05-09T10:22:00.139+05:30
tags:
  - evci
  - grid
  - WPT
cssclasses: ""
---


# Inductive Charging (Static and Dynamic)

**Inductive charging, or Wireless Power Transfer (WPT), uses resonant magnetic coupling to transfer energy through an air gap, eliminating physical connectors.**

## Mechanism / How It Works

Both types rely on **SAE J2954** standard principles:
- **Transmitter (Ground Pad):** High-frequency AC creates an oscillating magnetic field.
- **Receiver (Vehicle Pad):** Resonates at the same frequency to capture the magnetic flux and convert it back to DC.

### Static Inductive Charging
The vehicle is stationary over a single pad.
- **Applications:** Home garages, taxi ranks, autonomous valet parking.
- **Efficiency:** 85-92% (highly dependent on lateral alignment).

### Dynamic Inductive Charging (DIC)
The vehicle receives power while moving from a series of coils embedded in the road.
- **Applications:** Highway electrification (Electric Road Systems - ERS), Bus Rapid Transit (BRT) routes.
- **Efficiency:** ~80-87% (due to transient coupling as the vehicle moves between segments).

## Why It Matters

### Battery Downsizing
DIC allows vehicles to charge while driving, meaning they can use much smaller (and lighter) battery packs without sacrificing range—a critical enabler for heavy-duty long-haul trucking.

### Autonomous Future
Self-driving taxis cannot plug themselves in. Wireless charging is the foundational infrastructure for a fully autonomous transport ecosystem.

> [!note] The Alignment Challenge
> Inductive charging is sensitive to air gap height (Z-axis) and lateral offset (X/Y). A **75 mm** misalignment can drop efficiency by over 10%. Modern systems use ultrasonic or camera-based **Alignment Assist** to guide the driver.

---
## Backlink Summary
*Linked from:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/02c_EVCI_Infrastructure_MOC]]
*Links to:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Urban_Charging_Network_Planning]]
