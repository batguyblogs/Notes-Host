---
publish: true
comments: true
created: 2026-03-09T19:45:27.690+05:30
modified: 2026-03-09T19:46:00.779+05:30
cssclasses: ""
---

# Section 1: Introduction to Battery Technology
*(Covers L1, L2, L7, L8)*

## 1.1 Overview of Battery Technologies
*   **Battery technology** has evolved from the 1800s (Voltaic pile) to modern Lithium-ion.
*   **Key Types:**
    *   **Lead-Acid:** Reliable, low cost, used for backup and starter motors. Heavy with low energy density.
    *   **NiCd / NiMH:** NiCd has high surge but "memory effect" and toxic cadmium. NiMH is better for hybrids.
    *   **Li-ion:** High energy density, lightweight, long life. Standard for EVs.
    *   **Li-Po:** Flexible variant of Li-ion.

## 1.2 Historical Milestones
*   1859: First rechargeable lead-acid battery.
*   1991: Sony commercializes first Li-ion battery.
*   Present: Focus on solid-state and fast charging.

## 1.3 Importance in EVs
*   Crucial for **Energy Storage** (range), **Efficiency** (lower loss), **Sustainability** (zero tailpipe emissions), and **Cost** (scaling production).

## 1.4 Key Performance Metrics
*   **Voltage (V):** Potential difference; compatibility with vehicle electrical systems.
*   **Current (I):** Flow rate; higher current means more power but more heat.
*   **C-rate:** Rate of charge/discharge relative to capacity (e.g., 1C discharges 20Ah in 1h).
*   **Capacity (Ah):** Total charge a battery can store.
*   **Energy (Wh):** Work performed (Volt * Ah).
*   **DOD (Depth of Discharge):** Percentage of capacity used. (SOC = 100% - DOD).
*   **SOH (State of Health):** Ratio of current max charge to original rated capacity.
*   **Efficiency (%):** Proportion of energy retrieved vs. energy used to charge.

## 1.5 Energy and Power
*   **Energy Density (Wh/kg):** Determines range (the "water bottle size").
*   **Power Density (W/kg):** Determines acceleration (the "spout size").
*   **Ragone Chart:** Tool to compare chemistry trade-offs between energy and power.

## 1.6 Cell Combinations
*   **Series:** Sums voltage, current remains same.
*   **Parallel:** Sums current capacity (Ah), voltage remains same.
*   **Example (2S3P):** 2 cells in series for voltage, 3 strings in parallel for capacity.

---
## Expanded Notes & Deep Dive

### 1.1 In-Depth: Evolution of Battery Technologies
The transition from lead-acid to lithium-ion was driven by the specific needs of electric vehicles (EVs): high energy density to eliminate "range anxiety" and low weight to improve vehicle efficiency. 
*   **Lead-Acid:** Uses lead dioxide as the cathode, sponge lead as the anode, and sulfuric acid as the electrolyte. While they are fully recyclable and inexpensive, their specific energy is only about 30-50 Wh/kg.
*   **Nickel-Metal Hydride (NiMH):** Dominated early hybrid vehicles (like the Toyota Prius). They use a hydrogen-absorbing alloy for the negative electrode. They offer around 60-120 Wh/kg but suffer from high self-discharge rates.
*   **Lithium-Ion (Li-ion):** Currently offers 150-250+ Wh/kg. Lithium is the lightest metal and has the greatest electrochemical potential, making it ideal for high-voltage, high-capacity cells.

### 1.4 Deep Dive: Key Performance Metrics
*   **C-rate and Internal Resistance:** Charging or discharging at high C-rates (e.g., 3C or higher, common in DC Fast Charging) increases the internal resistance heat ($I^2R$ losses). This requires robust active thermal management.
*   **State of Charge (SOC) vs. Depth of Discharge (DOD):** Operating continuously at extreme SOCs (0% or 100%) accelerates battery degradation. Most EV manufacturers implement "buffers" (e.g., limiting the usable capacity to 10%-90% of the physical capacity) to prolong battery life.

### 1.5 Ragone Chart Analysis
The Ragone chart visually represents the trade-off between power and energy:
*   **Ultracapacitors/Supercapacitors:** Sit at the top-left (extremely high power density, very low energy density). Used for capturing rapid regenerative braking energy.
*   **Fuel Cells:** Sit at the bottom-right (high energy density, low power density).
*   **Li-ion:** Occupies the sweet spot in the middle, capable of balancing both sufficient range (energy) and acceleration (power).

### 1.6 Advanced Cell Configurations
When building a pack, cells are welded together. 
*   **Series ($N_s$):** Increases the pack voltage to reduce the required current for a given power output ($P = V \times I$). Higher voltage means thinner cables and less $I^2R$ loss. Modern EVs are moving from 400V to 800V architectures.
*   **Parallel ($N_p$):** Increases the total Ah capacity. If a single cell in a parallel group fails open, the other cells share the load, offering a degree of redundancy.
