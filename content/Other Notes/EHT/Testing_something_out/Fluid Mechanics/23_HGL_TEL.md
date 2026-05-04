---
publish: true
title: Hydraulic Gradient Line and Total Energy Line
created: 2026-05-02
modified: 2026-05-04T06:19:42.147+05:30
tags:
  - FluidMechanics
  - PipeFlow
  - atomic
  - HGL
  - TEL
  - energy-lines
cssclasses: ""
---


# Hydraulic Gradient Line and Total Energy Line

**The HGL plots piezometric head (P/ρg + z) along the pipe; the TEL plots total head (P/ρg + V²/2g + z); the vertical gap between them equals the velocity head V²/2g, and the TEL always slopes downward in the direction of flow due to energy losses.**

---

## Definitions

### Piezometric Head

The **piezometric head** at any point in a flow is:

$$h_p = \frac{P}{\rho g} + z$$

It is the sum of pressure head and elevation head — representing the height to which
fluid would rise in a piezometer (static pressure tap) connected to the pipe.

### Hydraulic Gradient Line (HGL)

A line joining the piezometric head values at successive cross-sections along the pipe.

$$\text{HGL} = \frac{P}{\rho g} + z$$

### Total Head

The total head (total energy per unit weight) at any point:

$$H = \frac{P}{\rho g} + \frac{V^2}{2g} + z$$

### Total Energy Line (TEL) — also called Energy Gradient Line (EGL)

A line joining the total head values at successive cross-sections:

$$\text{TEL} = \frac{P}{\rho g} + \frac{V^2}{2g} + z$$

---

## Relationship Between HGL and TEL

The vertical distance between TEL and HGL at any section equals the **velocity head**:

$$\text{TEL} - \text{HGL} = \frac{V^2}{2g}$$

```
                   TEL (total energy line)
    ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─
                   ↕  V²/2g (velocity head)
    ───────────────────────────────────────
                   HGL (hydraulic gradient line)
```

- If the pipe is uniform (constant diameter), V²/2g is constant → TEL and HGL are
  **parallel** lines
- If the pipe widens (V decreases), V²/2g decreases → TEL and HGL **converge**
- If the pipe narrows (V increases), V²/2g increases → TEL and HGL **diverge**

---

## Behaviour Along a Pipe System

### TEL Always Slopes Downward

For real fluids flowing without a pump, total energy decreases in the direction of flow.
The TEL always slopes downward with distance (it never rises unless a pump adds energy).
The **slope of the TEL** equals the rate of head loss per unit length:

$$\text{Slope of TEL} = -\frac{h_L}{L} = -\frac{4fV^2}{d \cdot 2g}$$

For a uniform pipe with constant friction, the TEL is a straight line sloping down.

### HGL Can Slope Upward Locally

The HGL can slope upward if a pipe narrows significantly (velocity increases → pressure
decreases → but pressure head alone can rise if velocity head drops more sharply). In
practice, the HGL closely follows the pipe for horizontal flow and drops steeply in
sections with high velocity.

### At Pipe Entrance

At a reservoir surface: $P = P_{atm}$, $V \approx 0$, $z = H$

$$\text{TEL} = P_{atm}/\rho g + 0 + H = \text{constant (datum)}$$

There is a sudden drop at the entrance equal to the entrance loss:

$$\text{Drop at entrance} = h_i = 0.5 \frac{V^2}{2g}$$

### At Pipe Exit

At pipe exit into a reservoir: the entire velocity head is lost.

$$\text{Drop at exit} = h_o = \frac{V^2}{2g}$$

---

## ASCII Illustration

```
Reservoir A                                    Reservoir B
─────────────────────────────────────────────
  TEL ─ ─ ─ ┐ drop h_i     ────────────────────────────
             └──────────────────────────┐  drop h_o
                                         ───────────
  HGL         ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─
             ↕ V²/2g       pipe
═══════════════════════════════════════════════ datum (z = 0)

Notes:
• TEL falls continuously (friction + minor losses)
• HGL is parallel to TEL for constant-diameter pipe
• Gap between TEL and HGL = V²/2g
• At A and B reservoir surfaces: TEL = water surface elevation
```

---

## Key Rules for Sketching HGL and TEL

1. **TEL starts** at the upstream energy level (reservoir surface or known total head)
2. **TEL drops** by $h_i$ (entrance loss) at the pipe inlet
3. **TEL slopes down** uniformly along the pipe at rate $4fV^2/(d \cdot 2g)$
4. **TEL drops sharply** at any local loss (contraction, bend, fitting)
5. **TEL ends** at the downstream reservoir surface (if discharging freely)
6. **HGL = TEL − V²/2g** at every point
7. **HGL below pipe centreline** means pressure in the pipe is **negative** (sub-atmospheric — risk of cavitation)

> [!warning] Sub-atmospheric Pressure
> If the HGL falls below the pipe centreline, the fluid pressure at that section is
> sub-atmospheric. If it drops below the vapour pressure of the fluid, **cavitation**
> occurs — vapour bubbles form and collapse violently, damaging the pipe. Always check
> that HGL stays above the pipe profile in design.

---

## Why It Matters

HGL and TEL are essential diagnostic tools:
- They show **where energy is being lost** in a pipe system
- They reveal whether pressure anywhere is dangerously low (cavitation risk)
- They provide a graphical check on numerical Bernoulli calculations
- They are required in many exam problems to verify or interpret a pipe system

---

## Connections to Other Notes

- Bernoulli's equation — the three heads are the three components of TEL: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/16_BernoullisEquation]]
- Real fluid Bernoulli — hL is the drop in TEL: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/17_BernoulliRealFluid]]
- Darcy-Weisbach determines the slope of the TEL: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/20_MajorLosses_DarcyWeisbach]]
- Minor losses appear as discrete drops in the TEL: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/21_MinorLosses]]

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01c_PipeFlow_Hub]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/02c_PipeFlow_MOC]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/16_BernoullisEquation]]
*Links to:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/16_BernoullisEquation]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/17_BernoulliRealFluid]],
[[Other Notes/EHT/Testing_something_out/Fluid Mechanics/20_MajorLosses_DarcyWeisbach]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/21_MinorLosses]]
