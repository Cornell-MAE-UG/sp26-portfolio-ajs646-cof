---
layout: project
title: "Macadamia Nutcracker"
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
### Step 1
Assume the nutcracker works like a lever about the hinge:

Let:
- Fgrip = input force applied by the hand at the handle
- Fjaw = jaw force on the nut
- Lhandle = distance from pivot to where the hand applies force
- Ljaw = distance from pivot to where the nut is contacted
- Hhandle = distance from the bottom handle to top handle
- Hjaw = diameter of standard macademia Nut

- ΣM pivot = 0
- Fgrip x Lhandle - Fjaw x Ljaw = 0
- Fgrip x Lhandle ≈ Fjaw x Ljaw

Mechanical advantage:
- MA = Fjaw / Fgrip ≈ Lhandle / Ljaw

<img src="{{ '/assets/images/FBD-MacadamiaNut.jpeg' | relative_url }}" alt="Nutcracker sketch" style="width:300px;">

---

### Step 2
We need the jaw force to reach the cracking load:

- Required jaw force (cracking load) = 2178.84 N
- Fgrip = 350 N

So:
- Fjaw / Fgrip = 2178.84 / 350 = 6.22

This means:
- Lhandle / Ljaw ≥ 6.22

---

### Step 3 
Using smilar triangles:

<img src="{{ '/assets/images/Dimenstion-MacadamiaNut.jpeg' | relative_url }}" alt="Nutcracker sketch" style="width:300px;">

Lhandle / Ljaw = Hhandle / Hjaw

6.22 cm ≥ Hhandle / Hjaw

6.22 cm x 20 mm ≥ Hhandle

12.54 cm ≥ Hhandle

---

### Step 4
The nut is about 20 mm in diameter, so the nut must be able to sit in the pocket. It should sit a bit further away to make room for a pocket.

Choose:
- Ljaw = 3.0 cm

Handle length:
- Lhandle ≥ 6.22 x 3.0 cm = 18.66 cm

Select a larger final number to account for error and hand size:
- Lhandle = 20 cm

---

### Step 5 — Check 
Mechanical advantage:
- MA = 20 / 3.0 = 6.67

Estimated jaw force:
- Fjaw = MA x Fgrip = 6.67 x 350 N = 2333.33 N

Compare:
- 2333 N ≥ 2178.84 N ✔️

So this design should be able to crack a typical macadamia nut under these assumptions.

---

## Usability Discussion
A 20 cm handle length for a macadamia nutcracker is not a very realistic size for a standard handheld kitchen tool. Many common hand tools are closer to 15–19 cm, so 20 cm is on the larger side and could feel awkward to hold and operate comfortably while trying to crack a nut effectively.

Additionally, having the handles positioned about 12.45 cm apart would make the tool harder to grasp, and could reduce control during use. By placing the nut close to the pivot it increases the mechanical advantage, which would helps generate higher jaw force. However, because the design has limited extra margin, it may not accommodate much variability in nut size or shell strength, meaning it might not work reliably for all macadamia nuts.

---