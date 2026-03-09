---
publish: true
comments: true
created: 2026-03-09T19:45:27.691+05:30
modified: 2026-03-09T19:46:02.967+05:30
cssclasses: ""
---

# Section 2: Electrochemistry of Batteries
*(Covers L3, L4, L5, L6, L9, L10)*

## 2.1 Fundamentals
*   **Electrochemistry:** Study of converting chemical energy to electrical energy via **Redox reactions**.
*   **Redox:** Anode undergoes oxidation (loses electrons), Cathode undergoes reduction (gains electrons).
*   **Electrolytes:** Facilitate ion movement while maintaining charge neutrality.

## 2.2 Electrode Potentials & Nernst Equation
*   **Standard Reduction Potential:** Measured against Standard Hydrogen Electrode (SHE).
*   **Lithium:** Very high negative potential (-3.04 V), making it an excellent reducer for high-voltage cells.
*   **Nernst Equation:** `E = E° - (RT/nF)ln(Q)`. Predicts cell potential under non-standard concentrations and temperatures.

## 2.3 Working Principle of Li-ion
*   **Discharge:** Li-ions move from Anode to Cathode through the electrolyte; electrons flow through the external circuit.
*   **Charge:** External power forces Li-ions from Cathode back to Anode (Intercalation).
*   **Intercalation:** The process of ions inserting into the host structure (graphite or metal oxide).

## 2.4 Internal Resistance
*   **Ohmic Resistance:** Resistance of conductive materials.
*   **Polarization Resistance:** From reactions and ion movement.
*   **Impact:** Causes voltage drop under load and heat generation.

## 2.5 Aging and Cycle Life
*   **Cycle Life:** Number of charge/discharge cycles before capacity drops to ~80%.
*   **Calendar Aging:** Degradation over time regardless of use.
*   **Factors:** Temperature (heat = faster aging), DOD (deeper = more stress), and C-rates (high = more heat).
*   **Mechanisms:** SEI layer growth, Lithium plating (at low temps/high charge), and mechanical degradation of electrode materials.

## 2.6 Lead-Acid vs. Li-ion
*   Li-ion has higher cycle life (3500+ vs 400), higher usable capacity, and is much lighter.

---
## Expanded Notes & Deep Dive

### 2.1 The Thermodynamics of Electrochemistry
Batteries operate on the principles of Gibbs Free Energy ($\Delta G$). The electrical work a battery can do is related to the chemical energy change: $\Delta G = -nFE$, where $n$ is the moles of electrons, $F$ is Faraday's constant, and $E$ is the cell potential. A spontaneous reaction (discharge) has a negative $\Delta G$ and a positive cell potential.

### 2.2 Deep Dive: Nernst Equation in Practice
The Nernst equation explains why a battery's voltage drops as it discharges. As the reactants (e.g., Li-ions in the anode) are depleted and products (Li-ions in the cathode) build up, the reaction quotient ($Q$) increases. Because the term $- (RT/nF)\ln(Q)$ is subtracted from the standard potential ($E^\circ$), the overall cell voltage $E$ decreases. This creates the typical discharge curve of a battery.

### 2.3 The Mechanism of Intercalation
Unlike traditional batteries where electrodes dissolve and rebuild (like Lead-Acid), Li-ion batteries use "intercalation" or "rocking-chair" chemistry. 
*   Lithium ions insert themselves into the interstitial spaces of the host material's crystal lattice (e.g., between the graphene layers).
*   This process involves minimal structural changes to the host material, which is why Li-ion batteries can withstand thousands of cycles.

### 2.5 Advanced Degradation Mechanisms
*   **Solid Electrolyte Interphase (SEI):** During the very first charge (formation), the liquid electrolyte reacts with the graphite anode to form a passivation layer called the SEI. This layer is crucial as it prevents further electrolyte decomposition while allowing Li-ions to pass. However, over time, the SEI slowly grows, continually consuming active lithium and increasing internal resistance (Capacity Fade).
*   **Lithium Plating:** Occurs primarily during fast charging at low temperatures. The intercalation of Li-ions into graphite becomes sluggish. Instead of entering the graphite lattice, lithium ions accumulate on the anode surface as metallic lithium. This not only permanently reduces capacity but can also form needle-like structures (dendrites) that pierce the separator and cause catastrophic short circuits.
