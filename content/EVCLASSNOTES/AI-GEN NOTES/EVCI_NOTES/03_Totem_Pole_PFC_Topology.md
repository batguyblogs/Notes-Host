---
publish: true
title: Totem Pole PFC Topology
created: 2026-05-09T10:30:22.424+05:30
modified: 2026-05-09T10:22:00.141+05:30
tags:
  - evci
  - hardware
  - PFC
cssclasses: ""
---


# Totem Pole PFC Topology

**The Bridgeless Totem Pole PFC is a high-efficiency AC-DC converter topology that eliminates the input diode bridge to reduce conduction losses in On-Board Chargers (OBC).**

## Mechanism / How It Works

In a traditional Boost PFC, the AC current must pass through two diodes in a bridge rectifier *plus* the boost diode. Each diode has a forward voltage drop ($\approx 0.7\text{--}1.0\ \text{V}$), creating significant heat at 32A (Level 2 AC).

### The Totem Pole Advantage
The Totem Pole topology replaces the diode bridge with high-speed switches (typically **GaN** or **SiC** FETs).
- **High-Frequency Leg:** Two FETs switching at 65-100 kHz to perform the boost/PFC function.
- **Low-Frequency Leg:** Two FETs switching at line frequency (50/60 Hz) to perform the rectification.

### Key Benefits
1. **Efficiency:** Eliminates the $\sim 2\text{V}$ diode bridge drop, improving efficiency by $\approx 0.5\text{--}1.0\%$. This is critical for OBCs where space for cooling is limited.
2. **Bidirectionality:** Naturally supports bidirectional power flow (V2G/V2H) as FETs allow current to flow in both directions.
3. **THD Compliance:** Enables very low Total Harmonic Distortion ($< 5\%$) through digital average current control.

## Why It Matters

For a **7.3 kW OBC** (standard for single-phase Level 2):
- Conduction losses in a standard bridge can be $\approx 50\text{--}70\ \text{W}$.
- The Totem Pole topology reduces this by half, allowing for a more compact, passively cooled or liquid-cooled design within the vehicle's engine bay.

> [!warning] Design Constraint
> Totem Pole PFC requires **Wide Bandgap (WBG)** semiconductors like GaN. Standard Silicon MOSFETs have high body-diode recovery energy ($Q_{rr}$), which makes them inefficient in this topology when operating in Continuous Conduction Mode (CCM).

---
## Backlink Summary
*Linked from:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/02a_EVCI_Hardware_MOC]], [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Power_Converter_Design]]
*Links to:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Power_Converter_Design]]
