---
publish: true
comments: true
created: 2026-06-17T10:00:24.933+05:30
modified: 2026-06-18T12:24:24.307+05:30
cssclasses: ""
---

point notes to re-read later 

## OBC (on board charger related)

- Level 1 and level 2 AC versus Level 3 DC
- EVSE doesnt convert much it just is a "smart  relay"
- to convert the grid AC to battery dc we need OBC
- OBC is a lot of weight nearly 3-4 KG and needs dedicated cooling loop
- and its only useful when parked
- if the charger is capable of 22KW AC but the vehicle only supports 7.4 KV the car is bottle necked
- DC removes the conversion from the car to the station, 
- removes deadweight and increases speed by a lot
- gives high voltage DC to the vehicle BUS 
- Makes a physical interface conflict 
- One port for ac another for DC is bad

## CCS
- it takes the existing AC plug (SAC J1772 - american ) or the (Type - 2 Standard - Europe )
- it leaves the Ac pins intact but adds two massive DC pins 
- at home you can use AC
- the AC and DC are physically isolated
- even during DC charging the AC pins are used in communication 
- CP and PP control pilot and proximity pilot 
- they negotiate the power levels before a charging session ensues 

## **C**ontrol **P**ilot
- is used to broadcast the maximum available current to the vehicle's charge controlller
- it uses 1 kHz pwm signal 
- analog signals arent used because of the immense ammount of noise , due to high frequency switching happening very nearby
- if a mistake happens it might request currents more than the evse is capable of 
- the PWM signal isnt bothered by amplitude modulation 
- 53.3%d - 32 amps 

## **P**roximity **P**ilot

> [!quote] Quote of the day - notebooklm
> "The PP is Fascinating"

- it serves a Dual purpose [capacity detection , sequence interruption]
- Capacity detection, the charging cable will have a resistance between it and the ground , the vehicle checks the voltage drop and forces a power throttle to stop the cable melting
- drive away prevention, and a hot unplug mitigation.
- its physically tied to the mechanical latch, when the user unplugs it , it alters the resistance, and the vehicle detects it. 

>[!quote] They just keep coming
>"Because human arms are slow, and electrons are fast.
>
- The vehicle commands the power electronics to drop the current to zero. 
- the charger at 200 Amps would kill anyone and anything disconnecting it.

## Energising the coil
- First an Isolation monitoring, before the main contacter is connected and raw power is dumped into the batteries the vehicle conducts a check to verify that there is a minimum resistance of 1 mega Ohm between any of the high voltage busses and the vehicle chassis ground.
- if the isolation resistance approaches the 100 kilo ohm region the vehicle simply throws a fatal error. and refuses to charge!

## Pre-charge sequence 
- There are HUGE DC Link capacitors there to buffer the huge VOLTAGES
- but when parked they drain to 0 Volts.
- and an empty capacitor is  direct short to incoming voltage 
- say a DC fast charger at 800 Volts. 
### Pre-charge circuit
- a secondary smaller circuit with a LARGE series resistor , the current is throttled through the resistor and fills up the capacitor
- when the potential difference across the main switch is low the contactors are closed.

- the contactors use a continuous 12v supply to energise a magnetic coil to keep them shut, in case of a catastrophic power loss or if the power is cut off in an accident the mechanical spring tension pulls the contactors open and cut the battery off.

## How to monitor an actively charging circuit

- a dead circuit is simple , you just pass a little current and check.
- but doing that with that large of current flowing nearby
- 2 topologies *DC-ELECTRIC-BRIDGE* applies a small dc diagnostic voltage and measures leakage current in the ground. but theres a fatal flaw, 
- the wires being shielded makes them long capacitors really
- theres a natural parasitic capacitance. the dc electric bridge confuses between the cable's capacitance and a dangerous leakage to ground
- to solve this, *AC-INJECTION* by injecting a low frequency ac waveform into the dc high voltage bus, the imd can make complex impedence calculations and perform some math after monitoring the phase. the harmless capacitance is separated from the actual leakage.

### HVI high voltage interlock loop 

- its a low voltage current loop and it routes through all the high voltage connector housing. 
- if any of the high voltage connectors are disconnected, this low voltage loop breaks and opens the high voltage contactors

## Totem Pole / PFC topologies 

PFC ( power factor correction )
when you pull AC from the grid you have to ensure the current and voltage waveform are in phase, other wise you get reactive power and require more current for the same power transmitted leading to poorer efficiencies.

Traditional PFC circuits use a standard diode bridge rectifier to  align them. 
but those suffer from conduction losses and have messy transition periods near the zero crossing.

the Totem pole topology replaces the diodes with active high frequency silicon carbide / gallium nitride switching transistors. 

the compounding benefit is that it doubles the ripple frequency. 

higher frequency -> smaller inductors!  better for the engineers packing the OBC into the car

The **IEC 61851** series is the primary international standard governing conductive (wired) charging systems for electric vehicles. Within this family, the sources provide a detailed comparison between two foundational standards: **IEC 61851-1** and **IEC 61851-23**.

### **IEC 61851-1: The General Framework**

- **Scope:** This acts as the "parent" standard and establishes the overarching framework and general requirements for **all** conductive EV charging systems, regardless of power level, connector type, or whether the system uses AC or DC.
- **Key Elements:** It defines the four different charging modes (ranging from domestic sockets to off-board DC charging) and establishes general safety requirements, such as shock protection and cable management.
- **Communication:** It outlines the primary analog communication mechanisms, specifically the Control Pilot (CP) signal specification for current advertisement and Proximity Pilot (PP) detection.

### **IEC 61851-23: DC Charging Station Specifics**

- **Scope:** This is a "daughter" or part standard that applies **exclusively to off-board DC charging equipment** (such as DC Fast Chargers or DC wallboxes).
- **Key Elements:** It provides highly specific requirements for DC systems, such as permissible DC output voltage and current ranges (up to 1000 V DC and 400 A), and mandates galvanic isolation between the AC input and DC output.
- **DC Safety Sequences:** It dictates the specific control sequences required for DC charging, including mandatory pre-charge verification, protection against backfeed from the vehicle's battery, and insulation monitoring for DC unearthed (IT) systems.

**The Practical Implication:** Because IEC 61851-23 is a specialized extension, a manufacturer designing a DC fast charger must comply with **both** standards. IEC 61851-1 compliance alone is insufficient for DC products; the manufacturer must satisfy the general framework of IEC 61851-1 while also meeting the DC-specific safety and output parameters of IEC 61851-23.

### **Other Relevant IEC Standards**

The sources also detail a few other closely related standards that handle different aspects of the charging ecosystem:

- **ISO/IEC 15118:** This standard operates at the application layer and defines the **digital communication protocol** between the EV and the charger. It transforms charging into a smart, grid-integrated service by enabling "Plug and Charge" (automated authentication without RFID cards or apps) and bidirectional power scheduling for Vehicle-to-Grid (V2G) systems.
- **IEC 62196:** This standard defines the **physical connector** dimensions and ratings used primarily in Europe (often referred to as the Type 2 or Mennekes plug).
- **IEC 61851-21 & IEC 61851-24:** These are additional components of the 61851 family that cover vehicle-side connection requirements and digital communication specifically for DC systems, respectively.


The nominal dimensions for an EV charging parking space vary depending on the type of vehicle and the specific layout needs. According to the sources, the standard guidelines are as follows:

- **Standard EV parking bay:** The typical width is **2.5 meters**, which is the minimum mandated by most national standards.
- **Bays with side-mounted chargers:** A wider space of **2.75 to 3.0 meters** is often recommended to allow sufficient room for connector and cable access without risking door damage.
- **Accessible (disabled) bays:** These require a width of **3.3 to 3.6 meters**, plus an additional **1.2-meter transfer zone** to allow for wheelchair access alongside the vehicle.
- **Commercial vehicle and bus bays:** These spaces need a width of **3.5 to 4.0 meters** to accommodate larger vehicle sizes and cable handling clearances.

Beyond just the width of the spots, the sources outline several other important spatial dimensions to consider in an EV charging layout:

- **Length:** A minimum of **5.0 meters for passenger cars** and **12 to 16 meters for buses or trucks**.
- **Overhead clearance:** At least **2.3 meters for passenger cars** and **4.5 meters for commercial vehicles** (which is particularly important for underfloor charger clearance).
- **Cable routing space:** At least **0.5 meters of clearance** is needed on the charger side to account for the cable drape and the angle at which the connector approaches the vehicle.
- **Aisle width:** A minimum **6.0-meter two-way aisle** (though 6.5 meters is preferred) is necessary so that EVs can easily maneuver into the spots without having to reverse over charging cables.


A Charge Point Operator (CPO) is primarily responsible for planning, installing, owning, operating, and maintaining the physical electric vehicle charging stations and the network infrastructure that connects them.

Their core responsibilities include:

- **Site Acquisition:** Negotiating location agreements with landowners, such as those for car parks, motorways, or retail sites.
- **Civil and Electrical Installation:** Managing the physical infrastructure setup, which includes cabling, transformers, earthing, and other necessary civil works.
- **EVSE Procurement:** Selecting and procuring the actual charging equipment (hardware) to be installed at the sites.
- **Operations and Maintenance:** Ensuring station uptime, responding to faults, rolling out firmware updates, and conducting physical servicing of the hardware.
- **CSMS Operation:** Operating the Charging Station Management System (CSMS), which allows the CPO to monitor all of their charging stations in real time.
- **Grid Connection Management:** Managing agreements with Distribution Network Operators (DNO) or Distribution Companies (DISCOM), as well as handling demand management and ensuring compliance with smart charging protocols.
- **Data Provision:** Providing real-time data regarding station status to roaming hubs and navigation platforms so drivers know which chargers are available.

As part of their revenue model, CPOs typically charge a wholesale rate per kWh or per session to E-Mobility Service Providers (e-MSPs), though they may also charge end customers directly if they operate as both a CPO and an e-MSP.

**Battery Energy Storage Systems (BESS)** are large-scale battery installations designed to store electrical energy so it can be deployed at a later time. Within the electric vehicle charging ecosystem, a BESS can be integrated directly at utility substations or installed at specific charging sites alongside captive renewable energy generation, such as solar PV.

BESS plays a highly strategic role in managing the electricity demand curve through several mechanisms:

- **Flattening the Net Load on the Grid:** A major challenge with mass EV adoption is "peak demand amplification," where EV charging predominantly occurs in the evening (18:00–22:00), exactly coinciding with the existing residential peak demand. Substation-level BESS addresses this by **absorbing surplus energy during off-peak times** (such as midday when solar generation is abundant) and **discharging that stored energy during the evening EV charging peak**. This actively flattens the net load on the high-voltage and medium-voltage network.
- **Buffering Peak Grid Draw at Charging Sites:** For high-power applications—like 150–300 kW opportunity chargers for heavy-duty electric trucks or large public charging hubs—the momentary power demand can severely stress the local grid. Deploying a BESS as a buffer at the terminal **reduces the peak amount of electricity drawn directly from the grid** during these intense charging sessions.
- **Lowering Energy Costs:** By supplying stored energy during periods when grid electricity is most expensive, a BESS allows site operators to **reduce peak grid draw and avoid high time-of-use or commercial demand tariffs**, providing immunity to grid tariff increases.
- **Deferring Infrastructure Upgrades:** By flattening the demand curve and keeping peak loads within manageable thresholds, BESS integration helps utility operators proactively manage the grid. This flexibility can help prevent transformer overloading and defer the need for massive capital expenditures on feeder reinforcements and substation capacity additions.
