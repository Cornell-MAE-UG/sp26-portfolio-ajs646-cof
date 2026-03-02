---
layout: project
title: "Macadamia Nutcracker (Simple Lever Design)"
image: assets/images/macadamia.jpg
---

## Problem Statement (Find)
Design a simple lever nutcracker that can crack a macadamia nut. Determine handle length and nut placement so that a typical user can generate enough force to crack the nut.

## Constraints & Inputs (Given)
- Nut size (design diameter): ~250 mm
- Target shell cracking load (jaw force needed): ~2178.84 N (literature-reported average cracking load; Schrauf et al., 2008, appendix)
- Assumed human input force: 350 N (combined)

Reference:
- Schrauf et al. (2008). "Do capuchin monkeys use weight to select hammer tools?" Animal Cognition. (Use the appendix values for cracking load.) https://doi.org/10.1007/s10071-007-0131-2

---
## Approach & Calculations
### Step 1 — Model as a simple lever about the pivot
Assume the nutcracker works like a lever about the hinge:

Let:
- Fgrip = input force applied by the hands at the handles
- Fjaw = jaw force on the nut
- Lhandle = distance from pivot to where the hands apply force
- Ljaw = distance from pivot to where the nut is contacted

- ΣM pivot = 0
- Fgrip x Lhandle - Fjaw x Ljaw = 0
- Fgrip x Lhandle ≈ Fjaw x Ljaw

Mechanical advantage:
- MA = Fjaw / Fgrop ≈ Lhandle / Ljaw

---

### Step 2 — Compute the required mechanical advantage
We need the jaw force to reach the cracking load:

- Required jaw force (cracking load) = 2178.84 N
- Fgrip = 350 N

So:
- Fjaw / Fgrip = 2178.84 / 350 = 6.22

This means the geometry must satisfy:
- Lhandle / Ljaw ≥ 6.22

---

### Step 3 — Choose a practical jaw placement using nut size (25 mm)
The nut is about 20 mm in diameter, so the nut must be able to sit in the pocket. Practical it should sit a bit further away to away room for a pocket.

Choose:
- Ljaw = 3.0 cm

Handle length:
- Lhandle ≥ 6.22 x 3.0 cm = 18.66 cm

Select a larger final number to account for error and hand size:
- Lhandle = 20 cm

---

### Step 4 — Check 
Mechanical advantage:
- MA = 20 / 3.0 = 6.67

Estimated jaw force:
- Fjaw = MA x Fgrip = 6.67 x 350 N = 2333.33 N

Compare:
- 2333 N ≥ 2178.84 N ✔️

So this design should be able to crack a typical macadamia nut under these assumptions.

---

## Usability Discussion

What works well:
- 20 cm handles are realistic for a handheld kitchen tool and allow comfortable squeezing.
- Placing the nut close to the pivot (3.0 cm) provides high mechanical advantage, so the user does not need extreme grip strength.
- A jaw pocket sized for a 20 mm nut improves alignment and reduces slipping.

Potential issues and improvements:
- Pinch hazard near the hinge: add a simple hinge guard or spacer so fingers cannot get caught.
- Nut slipping/ejection: use serrations or a high-friction insert and a cup/V-groove pocket to hold the nut securely.
- Hand comfort/fatigue: use thicker, ergonomic grips and a slightly curved handle profile.
- Nut-to-nut variability: if some nuts require higher-than-average force, increasing handle length (e.g., 23–35 cm) would increase jaw force without changing the jaw geometry.

---