---
publish: true
comments: true
created: 2026-03-11T07:26:16.437+05:30
modified: 2026-03-11T11:00:08.837+05:30
cssclasses: ""
---


## L1 & L2: EV Market Overview and Infrastructure Types

  

### 1. Market Trends and Projections

The global transition toward electrification is accelerating, driven by decarbonization goals such as the EU's "Fit for 55" (55% emission reduction by 2030).

* **Global Scale:** Nearly 50 million EVs are projected on the road by the end of 2025.

* **India's Ambition (NITI Aayog 2030):**

* 80% penetration for 2W and 3W.

* 70% for commercial cars.

* 30% for private cars.

* 40% for buses.

* **Energy Demand:** By 2030, an estimated 230 TWh of energy will be needed globally for EV charging, requiring ~30 million chargers.

  

### 2. Public vs. Private Charging

* **Private Charging:** Currently dominates the market (Home/Workplace). Convenient for overnight charging and utilizes lower off-peak electricity rates.

* **Public Charging:** Essential for urban residents without private parking and for enabling long-distance travel.

* **India's Unique Mix:** Unlike the West, India's infrastructure must cater primarily to 2Ws and 3Ws, which favor AC slow charging or **Battery Swapping**.

  

**Technical Deep Dive: Total Cost of Ownership (TCO) Analysis**

In the engineering phase of EV adoption, TCO is the critical metric for consumers.

* **Formula:** $TCO = \frac{Capital Cost + Operational Cost - Salvage Value}{Total Distance Travelled}$

* **Breakeven Point:** For an e-2W, the TCO typically becomes lower than an ICE counterpart at a daily run of ~12 km. For e-3W (CNG vs Electric), the breakeven is around 20 km/day. This data drives the demand for charging infrastructure in specific urban corridors.

  

---

  

## L3: Policy Impact and Incentives

  

### 1. FAME India Scheme

The "Faster Adoption and Manufacturing of Hybrid and Electric Vehicles" (FAME) is the cornerstone of Indian EV policy.

* **FAME II (2019-2024):** Outlay of ₹10,000 Cr.

* **Focus:** Upfront incentives for EV purchase and grants for charging infrastructure.

* **Impact:** Sanctioned 2,877 public stations in 68 cities and 1,576 stations across 16 national highways.

  

---

  

## L4 & L5: Design Principles and Engineering Considerations

  

### 1. Site Selection and Layout

* **Accessibility:** Visibility from site entrance, ease of entry/egress, and proximity to major roads.

* **Layout Planning:**

* **Linear Arrangement:** Most efficient for curbside/parking lots.

* **Standard Dimensions:** 2.5m width per parking spot with a 1m "stop clearance" at the front for pedestrian safety and cable reach.

* **Civil Engineering:** Foundation requirements for inlets/outlets, drainage systems, and secure enclosures against vandalism.

  

### 2. Grid Integration Topologies

Engineers must choose between AC and DC bus architectures for charging plazas.

* **AC Bus Topology:** Each charger has its own AC/DC rectifier. Higher grid synchronization complexity but lower initial capital cost.

* **DC Bus Topology:** Centralized AC/DC conversion. Higher efficiency due to fewer conversion stages and easier integration with Renewable Energy Sources (RES) like solar and Energy Storage Systems (ESS).

  

**Engineering Context: Power Factor Correction (PFC)**

PFC is mandatory in EVSE to ensure the input current follows a sinusoidal waveform in phase with the grid voltage. This reduces harmonics ($THD < 5\%$) and prevents grid instability. A **DC Link Capacitor** acts as an energy buffer, smoothing the voltage ripple created during the AC/DC conversion process before it reaches the DC/DC stage.

  

---

  

## L6: Types of Charging Stations

  

| Charger Type   | Power Supply           | Power Level  | Approx. Charging Time (24kWh) |
| -------------- | ---------------------- | ------------ | ----------------------------- |
| **Level 1 AC** | 120/230 VAC (12-16A)   | Up to 2 kW   | 12 - 17 Hours                 |
| **Level 2 AC** | 208-240 VAC (15-80A)   | Up to 20 kW  | ~8 Hours                      |
| **Level 3 DC** | 300-600 VDC (Max 400A) | 120 - 240 kW | < 30 Minutes                  |

  

* **Bharat AC001:** 3.3 kW per socket, designed for 2W/3W.

* **Bharat DC001:** 15 kW / 30 kW, typically 48V/72V DC output.

  

---

  

## L7 & L8: Testing, Validation, and Safety

  

### 1. Communication Protocols (Signaling)

The handshake between EV and EVSE is governed by the **Control Pilot (CP)** and **Proximity Pilot (PP)**.

* **PP (Proximity Pilot):** Uses resistance coding to detect if the cable is plugged in and define the maximum current capacity of the cable.

* **CP (Control Pilot):** Uses a 1 kHz, ±12V PWM signal to communicate charging states.

  

### 2. Charging States (IEC 61851-1)

* **State A:** Standby (+12V DC).

* **State B:** Vehicle Detected (+9V / PWM).

* **State C:** Vehicle Ready / Charging (+6V / PWM).

* **State D:** Ventilation Required (+3V / PWM).

* **State E:** Error (0V).

* **State F:** Fault (-12V).

  

**Technical Deep Dive: The PWM Duty Cycle**

The EVSE communicates the maximum permissible current to the EV by modulating the duty cycle ($D$) of the CP signal:

* $10\% \leq D \leq 85\%$: $Max Current (A) = D \times 0.6$

* $85\% < D \leq 96\%$: $Max Current (A) = (D - 64) \times 2.5$

* *Example:* A $50\%$ duty cycle tells the vehicle it can draw up to $30A$ ($50 \times 0.6$).

  

**Technical Deep Dive: The Validation and Safety Sequence**

Before power transfer begins, the EVSE and EV perform a rigorous safety handshake:

1. **Isolation Resistance Testing:** The charger measures the resistance between DC+ and DC- relative to the Protective Earth (PE). This detects high-voltage insulation faults that could cause a chassis to become live.

2. **Pre-Charge Phase:** To prevent massive inrush currents that could damage contactors (arcing), the charging station applies a voltage to the vehicle's intermediate circuit until it matches the battery voltage. Only then does the EV close its main contactors.

3. **Welding Detection:** After charging, the system verifies that contactors have physically opened. If a contactor "welds" shut due to heat, the system flags a critical fault to prevent the user from handling a live connector.

4. **DC Leakage Detection:** Continuous monitoring for residual DC current leakage to ground, ensuring that any insulation failure during the high-power phase triggers an immediate shutdown.

  

---

  

## L9: International and National Standards

  

* **CCS-II (Combined Charging System):** The European standard, supporting both AC and DC through a single inlet. Uses Power Line Communication (PLC) over the CP pin.

* **CHAdeMO:** The Japanese standard, primarily for DC fast charging. Uses CAN bus for high-speed data exchange between the vehicle's BMS and the charger.

* **IS 17017:** The primary Indian standard series for EV conductive charging systems, ensuring safety, EMI/EMC compliance, and interoperability.

* **ISO 15118:** Enables "Plug & Charge" (PnC) and V2G (Vehicle-to-Grid) by facilitating secure digital certificates and high-level communication.

  

---

  

## Deep Dive: Emerging Technologies

  

### 1. Inductive (Wireless) Charging

* **Static:** Charging while parked.

* **Dynamic (DIC):** Charging while in motion via road-embedded power tracks.

* **Principles:** High-frequency (20-100 kHz) magnetic resonant coupling. Eliminates cables and reduces "range anxiety," but faces challenges in alignment efficiency and high infrastructure cost.

  

### 2. Battery Swapping (BaaS)

* **Model:** Users swap a depleted battery for a full one in <5 mins.

* **Advantages:** Eliminates wait times, reduces upfront EV cost (Battery-as-a-Service).

* **Engineering Challenge:** Requires universal battery standards and robust robotic alignment systems to handle diverse chassis designs.