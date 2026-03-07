---
publish: true
created: 2026-03-05T15:23:22.718+05:30
modified: 2026-03-05T15:23:22.718+05:30
cssclasses: ""
---

#DetailedNotes

>[!note] Class Notes Index 
>[[FC  _index class notes]]

# What is Vehicle Dynamics? 
to get to vehicle dynamics we first look at Dynamics, 
is a fork ( branch ) of classical mechanics that deals with forces and their impacts on ==Motion==.

so **Vehicle Dynamics** is the study of vehicle motion, i.e. it's movement changes in response 
# Why do we need it?
Apart from needing it for vehicles in general why [[EV]]s in general.
- High motor torque
  [[EV]]s Having the higher torque react differently upon acceleration over [[ICE]] vehicles
- Heavy Battery mass
  The centre of gravity and the vehicle load balance all depend on the immense weight of the batteries
- Software-controlled behaviour 
  since most evs rely on systems like drive by wire and have a lot of software controlled aspects , sometimes including the power delivery it impacts the dynamics
- Safety, comfort, and efficiency challenges 
  self explanatory

# Vehicle Motions
- Longitudinal ( acceleration / braking )
- Lateral ( centripetal forces while taking a turn )
- Vertical ( think suspensions, we don't want too much up and down for ride comfort )
- Rotational:
    - Roll
    - Pitch
    - Yaw

# Core Factors affecting the Vehicle Dynamics? 

1. Distribution of Mass

2. Geometry and Kinematics of Moving Components and Tires

3. Most Contributing Subsystems: Suspension, Steering Frame, Aerodynamics

4. Aerodynamic Forces

# Basic Principles and Concepts to Deal with when studying Vehicle Dynamics
1. Newton's Laws of Motion
   the three laws serve as the foundation of all dynamic analysis
   
2. Forces acting on a vehicle
   refer vehicle motion ⬆
   
3. Tire Dynamics
   tires being the primary interface between the vehicle and the road:
   Rolling resistance
   Grip: the frictional force that allows tires to transmit acceleration, braking and cornering forces
   Slip Angle: The angle between the direction a tire is pointing and the direction its travelling, which influences the cornering perform
   
4. Vehicle motion types
   refer vehicle motion again ⬆
 
5. Key performance metrics
   Stability: Ability to maintain control under various conditions.
   Handling: How the vehicle responds to driver input.
   Ride Comfort: Minimizing vibrations and shocks for passengers.
   Traction: Capability to transmit forces to the road without slipping.
   
6. Vehicle frames of reference
   Analysis requires a reference system ( coordinate system )
   Global Frame: Fixed reference system (ex: Earth's surface )
   Vehicle Frame: Moves with the Vehicle, with:
   Longitudinal axis (x-axis): Forward/backward 
   Lateral axis (Y-axis): left/right centripetal forces while cornering
   Vertical (Z-axis): up/down think of riding over a pothole. 

7. Aerodynamics
   Drag Force
   Lift Force: Acts vertically, potentially reducing tire grip.
   Downforce: Improves grip, especially in performance vehicles. 
   
8. Suspension dynamics
   The suspension system supports vertical loads and improves ride quality. 
   Springs and Dampers: Absorb shocks and maintain contact with the road.
   
9. Vehicle stability
   Under Steer: Front tires lose grip first; the vehicle tends to go straight.
   Over Steer: Rear tires lose grip first; the vehicle tends to spin.
   Neutral steer: Ideal balance between front and rear grip.
# Key aspects 
 