---
publish: true
title: Network Topologies (Star and Bus)
created: 2026-05-09T10:30:22.424+05:30
modified: 2026-05-09T10:22:00.140+05:30
tags:
  - evci
  - operations
  - networking
cssclasses: ""
---


# Network Topologies (Star and Bus)

**EV charging networks utilize different Ethernet topologies to connect individual chargers to a central site gateway or router.**

## Comparison of Topologies

### 1. Star Topology (Standard)
Each charger has a dedicated cable to a central switch.
- **Advantage:** High reliability. If one cable fails, only one charger goes offline.
- **Disadvantage:** High cabling cost in large parking lots.

### 2. Bus (Daisy-Chain) Topology
Chargers are connected in a series line.
- **Advantage:** Lowest cabling cost.
- **Disadvantage:** Single point of failure. If the first charger's network port fails, the entire line goes offline.

## Why It Matters

For **Public Charging Hubs**, the Star topology is mandatory for reliability. For **Residential Apartment Blocks** with 50+ chargers, a hybrid approach (clusters of stars) is often used to balance cost and redundancy.

> [!warning] Bus Topology Error
> A bus topology is generally **unsuitable** for revenue-critical networks. The "Cascading Failure" risk makes it difficult to maintain the 99.9% uptime required by many government tenders (like FAME-II).

---
## Backlink Summary
*Linked from:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/02d_EVCI_Safety_Ops_MOC]]
*Links to:* [[EVCLASSNOTES/AI-GEN NOTES/EVCI_NOTES/03_Charging_Management_Systems_CSMS]]
