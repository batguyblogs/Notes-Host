---
publish: true
title: Laminar Flow Through Circular Pipes — Hagen-Poiseuille
created: 2026-05-02
modified: 2026-05-04T06:19:25.155+05:30
tags:
  - FluidMechanics
  - PipeFlow
  - atomic
  - laminar
  - Hagen-Poiseuille
cssclasses: ""
---


# Laminar Flow Through Circular Pipes — Hagen-Poiseuille

**For laminar flow (Re < 2000) in a circular pipe, the velocity profile is parabolic, the maximum velocity is exactly twice the mean velocity, and the pressure drop is given by the Hagen-Poiseuille equation: Δp = 32μūL/D².**

---

## Assumptions

Before beginning the derivation, two assumptions must be stated:

1. The fluid **follows Newton's law of viscosity** (Newtonian fluid)
2. **No-slip condition** at the pipe wall: fluid particles adjacent to the pipe wall have
   zero velocity ($u = 0$ at $r = R$)

---

## Derivation — Force Balance on a Fluid Element

Consider a horizontal circular pipe of radius $R$. Isolate a concentric cylindrical fluid
element of radius $r$ and length $dx$:

```
    ←────────── L ──────────→
    ┌────────────────────────┐
    │   p₁      ←τ·2πr·dx   │  p₂
    │   ↓           ↑        │   ↑
    │ p×πr²    (shear)  (p+∂p/∂x·dx)πr²
    └────────────────────────┘
         ←── r ──→ ← R ─→
```

**Forces acting on the element:**

1. Pressure force at left end: $F_{P,left} = p \cdot \pi r^2$
2. Pressure force at right end: $F_{P,right} = \left(p + \frac{\partial p}{\partial x} dx\right) \pi r^2$ (opposing)
3. Shear force on curved surface: $F_\tau = \tau \cdot 2\pi r \cdot dx$ (opposing flow)

For **steady flow**, net force = 0:

$$p \pi r^2 - \left(p + \frac{\partial p}{\partial x} dx\right)\pi r^2 - \tau \cdot 2\pi r \cdot dx = 0$$

Simplifying:

$$-\frac{\partial p}{\partial x} \pi r^2 \, dx = \tau \cdot 2\pi r \, dx$$

$$\boxed{\tau = -\frac{\partial p}{\partial x} \cdot \frac{r}{2}} \quad \text{...(Eq. 1)}$$

> [!note] Key Result from Eq. 1
> Shear stress varies **linearly with radius** $r$:
> - At the centreline ($r = 0$): $\tau = 0$ (zero shear)
> - At the pipe wall ($r = R$): $\tau = \tau_0 = -\frac{\partial p}{\partial x} \cdot \frac{R}{2}$ (maximum shear)
> The negative sign confirms pressure **decreases** in the flow direction ($\partial p/\partial x < 0$).

---

## Velocity Distribution

Applying Newton's law of viscosity. Since $y = R - r$ (measuring from wall), $dy = -dr$:

$$\tau = -\mu \frac{du}{dr} \quad \text{...(Eq. 2)}$$

Equating Eq. 1 and Eq. 2:

$$-\mu \frac{du}{dr} = -\frac{\partial p}{\partial x} \cdot \frac{r}{2}$$

$$\frac{du}{dr} = \frac{1}{2\mu} \frac{\partial p}{\partial x} \cdot r$$

Integrating with respect to $r$:

$$u = \frac{1}{4\mu} \frac{\partial p}{\partial x} r^2 + C$$

**Applying the no-slip boundary condition**: at $r = R$, $u = 0$:

$$0 = \frac{1}{4\mu} \frac{\partial p}{\partial x} R^2 + C \implies C = -\frac{1}{4\mu} \frac{\partial p}{\partial x} R^2$$

Substituting back:

$$\boxed{u = -\frac{1}{4\mu} \frac{\partial p}{\partial x} \left(R^2 - r^2\right)} \quad \text{...(Eq. 3)}$$

This is a **paraboloid** — the velocity profile for laminar pipe flow is parabolic. This
is the signature result of Hagen-Poiseuille theory.

---

## Maximum Velocity

Velocity is maximum at the centreline where $r = 0$:

$$u_{max} = -\frac{1}{4\mu} \frac{\partial p}{\partial x} R^2 \quad \text{...(Eq. 4)}$$

Equation 3 can be rewritten using $u_{max}$:

$$u = u_{max} \left[1 - \left(\frac{r}{R}\right)^2\right] \quad \text{...(Eq. 5)}$$

---

## Average Velocity

The volumetric flow rate through the full cross-section (integrating over ring elements):

$$Q = \int_0^R u \cdot 2\pi r \, dr = 2\pi u_{max} \int_0^R \left[1 - \frac{r^2}{R^2}\right] r \, dr = \frac{\pi}{2} u_{max} R^2$$

Average velocity:

$$\bar{u} = \frac{Q}{\pi R^2} = \frac{u_{max}}{2}$$

$$\boxed{\frac{u_{max}}{\bar{u}} = 2}$$

> [!note] Critical Result
> **The ratio of maximum (centreline) velocity to mean velocity is exactly 2.0 for laminar
> pipe flow.** This means the average velocity is half the centreline velocity — a direct
> consequence of the parabolic profile. This result is exact, not approximate.

---

## Hagen-Poiseuille Pressure Drop

From the average velocity expression:

$$\bar{u} = -\frac{1}{8\mu} \frac{\partial p}{\partial x} R^2$$

For a pipe of length $L$, writing $-\partial p/\partial x = (p_1 - p_2)/L$:

$$\bar{u} = \frac{(p_1 - p_2) R^2}{8\mu L}$$

Solving for the pressure drop $\Delta p = p_1 - p_2$, and substituting $R = D/2$:

$$\boxed{\Delta p = p_1 - p_2 = \frac{32 \mu \bar{u} L}{D^2}} \quad \textbf{(Hagen-Poiseuille equation)}$$

where $D$ = pipe diameter (m), $L$ = pipe length (m), $\mu$ = dynamic viscosity (Pa·s),
$\bar{u}$ = mean velocity (m/s).

> [!note] Important Scaling
> $\Delta p \propto D^{-2}$: Doubling diameter reduces pressure drop by factor 4.
> Quadrupling diameter reduces pressure drop by factor 16. Small diameter pipes require
> dramatically larger pressure differences to maintain the same flow rate.

---

## Summary of Key Results

| Quantity | Formula |
|---|---|
| Shear stress distribution | $\tau = -\frac{\partial p}{\partial x}\frac{r}{2}$ — linear in $r$ |
| Velocity distribution | $u = u_{max}[1-(r/R)^2]$ — parabolic |
| Maximum velocity | $u_{max} = -\frac{1}{4\mu}\frac{\partial p}{\partial x}R^2$ |
| Average velocity | $\bar{u} = u_{max}/2$ |
| Ratio $u_{max}/\bar{u}$ | **2.0** (exact) |
| Hagen-Poiseuille | $\Delta p = 32\mu\bar{u}L/D^2$ |

> [!example] Worked Example (Q1 from source)
> Crude oil: μ = 0.097 Pa·s, ρ = 900 kg/m³, D = 0.1 m, L = 10 m, $\bar{u}$ = 0.471 m/s
>
> First verify laminar: $Re = 900 \times 0.471 \times 0.1 / 0.097 = 436.9 < 2000$ ✓
>
> Pressure drop:
> $\Delta p = \frac{32 \times 0.097 \times 0.471 \times 10}{(0.1)^2} = \frac{14.617}{0.01} = 1461.7 \text{ N/m}^2$

---

## Connections to Other Notes

- Newton's law of viscosity used in derivation: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/08_DynamicViscosity_NewtonsLaw]]
- Reynolds number to verify laminar regime before applying: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/14_ReynoldsNumber]]
- Friction factor connection: for laminar flow $f = 16/Re$ links H-P to Darcy-Weisbach: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/20_MajorLosses_DarcyWeisbach]]
- Annular geometry extension of this derivation: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/19_LaminarFlow_Annulus]]
- No-slip condition is the same mechanism driving boundary layer growth: [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/26_BoundaryLayer]]

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/01c_PipeFlow_Hub]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/02c_PipeFlow_MOC]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/13_LaminarVsTurbulent_Flow]]
*Links to:* [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/08_DynamicViscosity_NewtonsLaw]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/14_ReynoldsNumber]],
[[Other Notes/EHT/Testing_something_out/Fluid Mechanics/19_LaminarFlow_Annulus]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/20_MajorLosses_DarcyWeisbach]], [[Other Notes/EHT/Testing_something_out/Fluid Mechanics/26_BoundaryLayer]]
