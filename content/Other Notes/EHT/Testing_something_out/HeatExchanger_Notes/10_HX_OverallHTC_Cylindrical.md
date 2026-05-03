---
publish: true
title: Overall Heat Transfer Coefficient — Cylindrical Geometry (Ui and Uo)
created: 2026-05-03T10:20:50.458+05:30
modified: 2026-05-03T10:43:33.588+05:30
tags:
  - heat-exchanger
  - MTE3252
  - overall-HTC
  - cylindrical
  - Ui
  - Uo
  - atomic
cssclasses: ""
---


# Overall Heat Transfer Coefficient — Cylindrical Geometry ($U_i$ and $U_o$)

**For cylindrical tubes, the inner and outer surface areas differ, so $U_i \neq U_o$ — two different values of the overall heat transfer coefficient can be defined, but they are related by $U_i A_i = U_o A_o$, and both are correct provided the reference area is stated.**

---

## Definition

In a shell-and-tube heat exchanger, the tube wall is cylindrical. The inner surface area $A_i = 2\pi r_i L$ and outer surface area $A_o = 2\pi r_o L$ are different. Since $U$ is defined per unit area, specifying $U$ alone is ambiguous unless you state which area it refers to.

---

## Mechanism / How It Works

### Thermal Resistance Network (Cylindrical)

The three resistances in series for a cylindrical wall are:

$$R_{conv,i} = \frac{1}{h_i A_i}, \qquad R_{wall} = \frac{\ln(r_o/r_i)}{2\pi k L}, \qquad R_{conv,o} = \frac{1}{h_o A_o}$$

Total resistance:
$$R_{total} = \frac{1}{h_i A_i} + \frac{\ln(r_o/r_i)}{2\pi k L} + \frac{1}{h_o A_o}$$

Heat transfer rate:
$$Q = \frac{T_{\infty 1} - T_{\infty 2}}{R_{total}}$$

### Defining $UA_{ref}$

The product $UA_{ref}$ is unique and unambiguous:

$$UA_{ref} = U_i A_i = U_o A_o = \frac{1}{\dfrac{1}{h_i A_i} + \dfrac{\ln(r_o/r_i)}{2\pi kL} + \dfrac{1}{h_o A_o}}$$

### $U_i$ — Based on Inner Surface Area ($A_i = 2\pi r_i L$)

Dividing both sides by $A_i$:

$$\boxed{U_i = \frac{1}{\dfrac{1}{h_i} + \dfrac{r_i \ln(r_o/r_i)}{k} + \dfrac{1}{h_o}\cdot\dfrac{r_i}{r_o}}}$$

### $U_o$ — Based on Outer Surface Area ($A_o = 2\pi r_o L$)

Dividing both sides by $A_o$:

$$\boxed{U_o = \frac{1}{\dfrac{1}{h_i}\cdot\dfrac{r_o}{r_i} + \dfrac{r_o \ln(r_o/r_i)}{k} + \dfrac{1}{h_o}}}$$

Where:
- $r_i$ = inner radius of tube (m)
- $r_o$ = outer radius of tube (m)
- $h_i$ = convection coefficient on inner surface (W/m²·°C)
- $h_o$ = convection coefficient on outer surface (W/m²·°C)
- $k$ = thermal conductivity of tube wall (W/m·°C)
- $L$ = tube length (m)

---

## Key Details

### The Fundamental Relation

$$U_i A_i = U_o A_o$$

This always holds. It means:
- $U_i \neq U_o$ in general (unless $A_i = A_o$, which only occurs for a flat plate)
- Knowing $U_i$ and the geometry, you can always find $U_o = U_i(A_i/A_o) = U_i(r_i/r_o)$
- **$U$ is meaningless without specifying the reference area**

> [!warning] Critical Point
> This is a very common exam error. If a problem gives $U$ without specifying inner or outer surface, or if you forget to use the correct $A$ when computing $Q = UA\Delta T_m$, your answer will be wrong. Always state and use the same reference area consistently throughout a calculation.

### Worked Example from Lectures

A stainless steel tube ($k = 15.1$ W/m·K), $D_i = 1.5$ cm, $D_o = 1.9$ cm. $h_i = 800$ W/m²K, $h_o = 1200$ W/m²K. Fouling: $R_{f,i} = 0.0004$ m²K/W, $R_{f,o} = 0.0001$ m²K/W.

With fouling (full expression including $R_f$ — see [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/12_HX_Fouling]]):

$$UA_{ref} = U_i A_i = U_o A_o = \frac{1}{\frac{1}{h_i A_i} + \frac{R_{f,i}}{A_i} + \frac{\ln(r_o/r_i)}{2\pi kL} + \frac{R_{f,o}}{A_o} + \frac{1}{h_o A_o}}$$

The total thermal resistance per unit length ($L=1$ m) and derived $U_i$, $U_o$ would be calculated from this expression. (Full numerical solution requires fouling factor tables from [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/12_HX_Fouling]].)

---

### Neglecting Wall Resistance

When wall is thin and conductivity high, $R_{wall} = \ln(r_o/r_i)/2\pi kL \approx 0$, and if $A_i \approx A_o \approx A$:

$$U \approx \frac{h_i h_o}{h_i + h_o}$$

See [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/11_HX_OverallHTC_Simplified]] for this simplification and representative $U$ values.

> [!tip]
> When to neglect wall resistance: thin-walled copper or aluminium tubes (low $r_o/r_i$ ratio, high $k$). When NOT to neglect: thick-walled tubes, stainless steel ($k \approx 15$ W/m·K — relatively low), or tubes with fouling.

---

## Why It Matters

Real heat exchangers use tubes, not flat plates. The cylindrical geometry introduces the area asymmetry that makes $U$ reference-area-dependent. The formula derived here is directly used in all shell-and-tube HX design problems (see [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/04_HX_ShellAndTube]]) and in the fouling correction of [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/12_HX_Fouling]].

---

## Connections to Other Notes

This extends the plane wall derivation in [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/09_HX_OverallHTC_PlaneWall]] to the cylindrical case. The simplified form (wall resistance neglected) is in [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/11_HX_OverallHTC_Simplified]]. Adding fouling to this expression is the subject of [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/12_HX_Fouling]].

---

## Backlink Summary
*Linked from:* [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/00_HeatExchanger_Hub]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/01_HeatExchanger_MOC]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/09_HX_OverallHTC_PlaneWall]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/04_HX_ShellAndTube]]
*Links to:* [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/11_HX_OverallHTC_Simplified]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/12_HX_Fouling]], [[Other Notes/EHT/Testing_something_out/HeatExchanger_Notes/08_HX_LMTD_WorkedExamples]]
