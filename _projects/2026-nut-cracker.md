---
layout: project
title: "Macadamia Nutcracker"
image: assets/images/macadamia.jpg
---

## Problem Statement
Design a simple lever nutcracker that can crack a macadamia nut. Determine handle length and nut placement so that a typical user can generate enough force to crack the nut.

## Constraints & Inputs
- Nut size (design diameter): ~20 mm
- Target shell cracking load (jaw force needed): ~2178.84 N (literature-reported average cracking load; Schrauf et al., 2008, appendix)
- Assumed human input force: 350 N

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

<details markdown="1">

<summary><strong>Continue: Modeling the Handles as Flexible Beams</strong></summary>

## Flexible Handle Beam Analysis

### The location of Maximum Elastic Deflection 
The maximum elastic deflection occurs at the **free end of the handle**, where the user applies force — the **grip end** of the nutcracker.

### Assumptions

For this analysis, one handle is modeled as a flexible beam. The hinge end is treated as fixed, meaning so it cannot move or rotate. A downward force is applied at the grip, while the nut applies a force closer to the hinge. Only vertical forces are considered

The two handles are symmetrically, so you can only analyze one.

### Explanation

The handle behaves like a beam fixed at one end which is loaded along the length. At the hinge, no deflection occurs.

By moving away from the hinge, displacement adds up. Each point along the handle experiences bending from both the forces.

The nut force creates a bending near the jaw region, however that location is close to the fixed support, so there is very limited distance for the handle to displacement.

The grip end is farthest from the hinge and has the least constrained. It experiences the entire bending along the entire handle, which should result in the largest vertical displacement and thus deformation.

### Final Conclusion

The maximum elastic deflection occurs at the **grip end of the handle**, not at the nut contact point.

---

### Deflection Analysis Using a Beam Table

I used the standard cantilever beam deflection table. The hand force was modeled as a point load applied at the free end of a cantilever beam.

For a cantilever beam with a point load at the free end, the maximum deflection is:

**δ<sub>grip</sub> = PL<sup>3</sup> / 3EI**

The force from the nut is applied closer to the hinge at **x = a**, not at the free end. I used the same cantilever beam case over the length **a**, then extended the slope from the nut location to the grip end.

The deflection at the grip caused by the nut force is:

**δ<sub>jaw</sub> = Qa<sup>2</sup>(3L − a) / 6EI**

Using the free-body diagram from above, the two deflections act in opposite directions:

**δ<sub>max</sub> = δ<sub>grip</sub> − δ<sub>jaw</sub>**

Substituting the design values:

**δ<sub>max</sub> = [350(0.20)<sup>3</sup> / 3EI] − [2333(0.03)<sup>2</sup>(3(0.20) − 0.03) / 6EI]**

Simplifying:

**δ<sub>max</sub> = 0.9333/EI − 0.1995/EI**

Therefore:

**δ<sub>max</sub> = 0.7338/EI**

So the maximum vertical deflection of the handle is:

**δ<sub>max</sub> = 0.7338/EI**

---

### Allowable Deflection

The requirement says that the vertical elastic deflection must be below 2% of the handle length.

**δ<sub>allow</sub> = 0.02L**

Since the handle length is **L = 0.20 m**:

**δ<sub>allow</sub> = 0.02(0.20)**

**δ<sub>allow</sub> = 4.0 mm**

This:

**0.004 m\(\ge \)δ<sub>max</sub> = 0.7338 / EI**

**EI ≥ 0.7338 / 0.004**

**EI ≥ 183.5 N·m<sup>2</sup>**

So the handle needs a flexural rigidity of at least:

**EI<sub>min</sub> = 183.5 N·m<sup>2</sup>**

---

### Selected Beam Design

For the final beam design, I selected a **hollow cylindrical tube** made from **AZ80 magnesium alloy**.

A hollow cylinder is a good  choice for a nutcracker handle because it is lightweight, comfortable to grip, and resists bending and twisting. Magnesium alloy is also good because it has a low specific weight while still having some elastic stiffness.

From the material table:

- Material: **AZ80 magnesium alloy**
- Modulus of elasticity: **E = 45 GPa**
- Specific weight: **1800 kg/m<sup>3</sup>**

The selected tube dimensions are: (from trial and error)

- Outer diameter: **D<sub>o</sub> = 25 mm**
- Wall thickness: **t = 1 mm**
- Inner diameter: **D<sub>i</sub> = 23 mm**

For a hollow circular tube:

**I = π(D<sub>o</sub><sup>4</sup> − D<sub>i</sub><sup>4</sup>) / 64**

Using the chosen dimensions:

**I ≈ 5.44 × 10<sup>−9</sup> m<sup>4</sup>**

The flexural rigidity is:

**EI = (45 × 10<sup>9</sup>)(5.44 × 10<sup>−9</sup>)**

**EI ≈ 244.71 N·m<sup>2</sup>**

This is greater than the required stiffness:

**244.71 N·m<sup>2</sup> > 183.5 N·m<sup>2</sup>**

---

### Predicted Deflection

Using:

**δ<sub>max</sub> = 0.7338 / EI** and **EI ≈ 244.71 N·m<sup>2</sup>**

the predicted maximum deflection is:

**δ<sub>max</sub> = 0.7338 / 244.71**

**δ<sub>max</sub> = 0.0030 m**

**δ<sub>max</sub> = 3.00 mm**

As a percentage of the 200 mm handle length:

**3.00 / 200 × 100 = 1.5%**

As: **1.5% < 2.0%**

the design passes the deflection requirement.

---

### Mass Estimate

The cross-sectional area of the hollow tube is:

**A = π(D<sub>o</sub><sup>2</sup> − D<sub>i</sub><sup>2</sup>) / 4**

Using the above tube dimensions:

**A ≈ 7.54 × 10<sup>−5</sup> m<sup>2</sup>**

Using the magnesium density from the table:

**ρ ≈ 1800 kg/m<sup>3</sup>**

the mass of one handle is:

**m = ρAL**

**m = (1800)(7.54 × 10<sup>−5</sup>)(0.20)**

**m ≈ 0.0271 kg**

**m ≈ 27.1 g**

So each handle would weigh approximately **28 g**.

---

### Final Beam Design Conclusion

The selected beam design is a **25 mm outer diameter, 1.9 mm wall thickness hollow cylindrical tube made from AZ80 magnesium alloy**.

This design gives:

- Maximum predicted deflection: **3.67 mm**
- Percent of handle length: **1.5%**
- Allowable deflection: **4.0 mm**
- Required flexural rigidity: **183.5 N·m<sup>2</sup>**
- Actual flexural rigidity: **244.71 N·m<sup>2</sup>**
- Estimated mass: **28 g per handle**

So, the hollow magnesium tube keeps the handle deflection below 2% of its length while remaining lightweight and practical for a hand-operated nutcracker.

---

#### Acknowledgements 

I used ChatGPT to help edit my GitHub materials and formating as well as the aforementioned article for values. As well as the apenddix of the textboook. 

---