---
layout: project
title: "Macadamia Nutcracker (Simple Lever Design)"
image: assets/images/macadamia.jpg
---

## Problem Statement (Find)
Design a simple hand-powered lever nutcracker that can crack a macadamia nut. Determine key dimensions (handle length and nut placement) so that a typical user can generate enough compressive force at the jaws.

## Constraints & Inputs (Given)
- Nut size (design diameter): ~25 mm
- Target shell cracking load (jaw force needed): ~2200 N (literature-reported average cracking load; Schrauf et al., 2008, appendix)
- Assumed human input force (two-hand squeeze on handles): 300 N (combined)

Reference:
- Schrauf et al. (2008). "Do capuchin monkeys use weight to select hammer tools?" Animal Cognition. (Use the appendix values for cracking load.) https://doi.org/10.1007/s10071-007-0131-2

---
## Approach & Calculations
### Step 1 — Model the nutcracker as a simple lever
Assume the handle acts like a lever about a pivot (hinge).

Moment balance about the pivot:

Fin * Lhandle ≈ Fjaw * Ljaw

Mechanical advantage:
MA = Fjaw / Fin ≈ Lhandle / Ljaw

---
### Step 1 — Model as a simple lever about the pivot
Assume the nutcracker works like a lever about the hinge:
- Input moment about pivot ≈ Output moment about pivot
- (Input force) x (handle distance) ≈ (jaw force) x (jaw distance)

Let:
- Fin = input force applied by the hands at the handles
- Fjaw = jaw force on the nut
- Lhandle = distance from pivot to where the hands apply force
- Ljaw = distance from pivot to where the nut is contacted

Relationship:
- Fin x Lhandle ≈ Fjaw x Ljaw

Mechanical advantage:
- MA = Fjaw / Fin ≈ Lhandle / Ljaw

---

### Step 2 — Compute the required mechanical advantage
We need the jaw force to reach the cracking load:

- Required jaw force (cracking load) = 2200 N
- Fin = 300 N

So:
- MArequired = 2200 / 300 = 7.33

This means the geometry must satisfy:
- Lhandle / Ljaw ≥ 7.33

---

### Step 3 — Choose a practical jaw placement using nut size (25 mm)
The nut is about 25 mm in diameter, so the nut must be able to sit in the pocket. Practical it should sit a bit further away to away room for a pocket.

Choose:
- Ljaw = 30 mm = 3.0 cm

Now solve for handle length:
- Lhandle ≥ 7.33 x 3.0 cm = 22.0 cm

Select a larger final number to account for error:
- Lhandle = 23 cm

---

### Step 4 — Check that the design meets the requirement
Mechanical advantage:
- MA = 23 / 3.0 = 7.67

Estimated jaw force:
- Fjaw = MA x Fin = 7.67 x 300 N = 2300 N

Compare:
- 2300 N ≥ 2200 N  → PASS

So this design should be able to crack a typical macadamia nut under these assumptions.

---

## Usability Discussion

What works well:
- 23 cm handles are realistic for a handheld kitchen tool and allow comfortable two-hand squeezing.
- Placing the nut close to the pivot (3.0 cm) provides high mechanical advantage, so the user does not need extreme grip strength.
- A jaw pocket sized for a 25 mm nut improves alignment and reduces slipping.

Potential issues and improvements:
- Pinch hazard near the hinge: add a simple hinge guard or spacer so fingers cannot get caught.
- Nut slipping/ejection: use serrations or a high-friction insert and a cup/V-groove pocket to hold the nut securely.
- Hand comfort/fatigue: use thicker, ergonomic grips and a slightly curved handle profile.
- Nut-to-nut variability: if some nuts require higher-than-average force, increasing handle length (e.g., 26–30 cm) would increase jaw force without changing the jaw geometry.


---