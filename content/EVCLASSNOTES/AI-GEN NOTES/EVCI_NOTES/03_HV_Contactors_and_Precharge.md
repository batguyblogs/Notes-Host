---
publish: true
title: HV Contactors and Pre-charge
created: 2026-05-09T10:30:22.423+05:30
modified: 2026-05-09T10:22:00.138+05:30
tags:
  - evci
  - hardware
  - safety
cssclasses: ""
---


# High-Voltage Contactors and Pre-charge

**HV contactors are electromechanical switches providing galvanic isolation for the battery pack, while the pre-charge circuit limits inrush current to downstream capacitors during startup.**

## Mechanism / How It Works

EV inverters contain large DC-link capacitors ($C \approx 1000\text{--}10000\ \mu\text{F}$). Suddenly connecting a 400V battery to an uncharged capacitor would create a massive inrush current:
$$I_{peak} = \frac{V_{bat}}{R_{parasitic}} \approx \frac{400\text{V}}{0.01\ \Omega} = 40,000\ \text{A}$$

### The Three-Contactor Sequence
1. **Main Negative ($K_{neg}$):** Closes first to establish the ground reference.
2. **Pre-charge Contactor ($K_{pre}$):** Closes, allowing current to flow through the **Pre-charge Resistor** ($R_{pre}$).
3. **Voltage Monitoring:** The Battery Management System (BMS) monitors the DC-link voltage.
4. **Main Positive ($K_{pos}$):** Closes once $V_{DC\text{-}link} \ge 95\%\ V_{bat}$.
5. **Open $K_{pre}$:** The pre-charge path is removed once the main path is established.

## Why It Matters

### Prevention of Contact Welding
Without pre-charge, the energy of the inrush current would arc across the main contactor tips just before they close, melting the metal and "welding" them shut. This prevents the battery from being disconnected in an emergency.

### Capacitor Protection
High $dI/dt$ can damage the internal dielectric of electrolytic capacitors, leading to premature failure or rupture.

> [!warning] Exam Trap
> The pre-charge resistor must be rated for **Pulse Energy**, not just steady-state power. The energy absorbed in one cycle is:
> $$E = \frac{1}{2} C_{DC\text{-}link} \times V_{bat}^2$$
> Using a standard resistor not rated for this joule-pulse will cause it to fail open-circuit.

---
## Backlink Summary
*Linked from:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/02a_EVCI_Hardware_MOC]]
*Links to:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Insulation_Monitoring_Safety_Protocol]]
