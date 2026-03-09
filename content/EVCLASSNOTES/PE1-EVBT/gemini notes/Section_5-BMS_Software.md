---
publish: true
comments: true
created: 2026-03-09T19:45:27.691+05:30
modified: 2026-03-09T19:46:28.828+05:30
cssclasses: ""
---

# Section 5: Battery Management Systems (BMS) - Software
*(Covers L22, L23, L24)*

## 5.1 Software Functions
*   **Monitoring:** Continuous sampling of V, I, T.
*   **Data Logging:** Record operational data for diagnostics.
*   **Real-time Processing:** RTOS (Real-Time OS) ensures time-critical tasks (protection) happen first.

## 5.2 Estimation Algorithms
*   **SOC (State of Charge):**
    *   **Coulomb Counting:** Current integration (prone to drift).
    *   **OCV (Open Circuit Voltage):** Voltage lookup (needs rest).
    *   **Machine Learning/Kalman Filters:** Hybrid models for better accuracy.
*   **SOH (State of Health):** Based on capacity fade and internal resistance growth.

## 5.3 Thermal Management
*   Software controls fans/coolant pumps based on temperature inputs and predictive models.

## 5.4 Cell Balancing
*   **Passive:** Bleed excess energy from high-SOC cells via resistors (heat loss).
*   **Active:** Transfer energy between cells using capacitors/inductors (efficient, complex).

## 5.5 Energy/Power Prediction
*   Predicts available discharge power for acceleration and charge power for regenerative braking based on current battery limits.

---
## Expanded Notes & Deep Dive

### 5.2 Advanced SOC Estimation: The Kalman Filter
Coulomb counting (Amp-hour integration) suffers from accumulated sensor noise over time (drift). Open Circuit Voltage (OCV) is accurate but only works when the battery has been at rest for hours. 
*   **Kalman Filtering (EKF/UKF):** An advanced mathematical algorithm used in almost all modern EVs. It uses an Equivalent Circuit Model (ECM) of the battery. 
*   It predicts the cell voltage based on the current being drawn. It then compares its *predicted* voltage to the *actual* measured voltage. Based on the error, it dynamically corrects its internal SOC estimate. This creates a highly robust SOC value that converges to the true value even while driving, completely eliminating Coulomb counting drift.

### 5.3 Thermal Management Control Logic
BMS software must balance cell life, vehicle performance, and passenger comfort.
*   **Derating:** If cells approach their thermal limit (e.g., >55°C), the BMS software dynamically reduces the allowable discharge power limit sent to the VCU (Vehicle Control Unit). This results in reduced acceleration but prevents thermal runaway.
*   **Cold Weather Conditioning:** Li-ion cannot be fast-charged below 0°C without severe lithium plating. The BMS software will use the vehicle's heating systems (or run the stator coils of the electric motor inefficiently to generate heat) to warm the battery pack *before* arriving at a DC fast charger.

### 5.4 Cell Balancing Strategies in Practice
A battery pack is only as strong as its weakest cell. If one cell hits its maximum voltage early, charging must stop for the whole pack. If one cell hits its minimum voltage early, discharging must stop.
*   **Passive Balancing:** The most common approach due to low cost. It is typically only performed near the top of the charge cycle (e.g., >90% SOC). The BMS turns on tiny MOSFETs connected to bleed resistors (dissipating ~50-100mA) for the highest voltage cells until the lower cells catch up.
*   **Active Balancing:** Rarely used in EVs due to cost and complexity, but highly beneficial in second-life applications where cell degradation is highly uneven. It uses DC-DC converters to shuffle energy from strong cells to weak cells, ensuring 100% of the pack's energy is usable.
