---
publish: true
title: Authentication and Roaming
created: 2026-05-09T10:30:22.422+05:30
modified: 2026-05-09T10:22:00.135+05:30
tags:
  - evci
  - operations
  - roaming
cssclasses: ""
---


# Authentication and Roaming

**Roaming allows an EV driver to use charging stations from different operators with a single account, managed via inter-network protocols like OCPI.**

## Mechanism / How It Works

### Authentication Methods
1. **RFID / Mobile App:** Manual triggers requiring user interaction.
2. **Plug & Charge (ISO 15118):** Automatic certificate-based handshake.
3. **Credit Card (Ad-hoc):** Guest access without an account.

### Roaming Stakeholders
- **CPO (Charge Point Operator):** Owns the hardware (e.g., Tata Power).
- **e-MSP (e-Mobility Service Provider):** Owns the customer relationship (e.g., a car manufacturer's app).
- **Roaming Hub:** The intermediary (e.g., Hubject) that connects multiple CPOs and e-MSPs.

## Why It Matters

### Preventing Infrastructure Silos
Without roaming, a driver might need 10 different apps and RFID cards to travel across a country. Roaming creates a **Seamless Network** where one app works everywhere, similar to mobile phone roaming.

### The Role of OCPI
The **Open Charge Point Interface (OCPI)** protocol enables the exchange of location data, tariffs, and billing records between different charging networks in real-time.

---
## Backlink Summary
*Linked from:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/02d_EVCI_Safety_Ops_MOC]], [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Charging_Management_Systems_CSMS]]
*Links to:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Charging_Management_Systems_CSMS]]
