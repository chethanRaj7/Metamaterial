<div align="center">

# Dual-Band Terahertz Metamaterial Absorber with Enhanced Sensing Capabilities

### A microscopic engineered surface that detects minute changes in a material by how it absorbs terahertz light

![IEEE](https://img.shields.io/badge/Presented%20at-IEEE%20SCPGCON%202026-00629B?style=for-the-badge&logo=ieee&logoColor=white)
![Simulation](https://img.shields.io/badge/Simulated%20with-COMSOL%20Multiphysics-orange?style=for-the-badge)
![Domain](https://img.shields.io/badge/Domain-Terahertz%20%7C%20Photonics%20%7C%20Biosensing-8A2BE2?style=for-the-badge)
![Status](https://img.shields.io/badge/Final%20Year%20Project-ECE-success?style=for-the-badge)

**Sai Vidya Institute of Technology, Bengaluru** · Department of Electronics and Communication Engineering

[Paper](paper/SCPGCON_Paper.pdf) · [Certificate](certificate/SCPGCON_Certificate.pdf) · [Results](#key-results-at-a-glance)

</div>

---

## Summary

We designed a microscopic pattern of metal (a **metamaterial absorber**) that **absorbs almost 100% of terahertz light at two specific frequencies**. When a substance is placed on top of this surface, those two absorption frequencies shift slightly. By measuring the shift, the same structure works as a **highly sensitive, label-free sensor** with potential applications in **medical diagnostics and early disease detection**.

The work was shortlisted and presented at the **IEEE SCPGCON 2026** conference.

| What was built | Why it matters | Headline results |
|---|---|---|
| A dual-band terahertz absorber and sensor, designed and simulated in COMSOL Multiphysics | Low-cost, non-destructive, chemical-free detection of biological samples | **99.2%** and **97.79%** absorption; sensitivity of about **2.8 THz/RIU** |

---

## Table of Contents

1. [The Big Picture](#the-big-picture)
2. [Key Concepts in Plain English](#key-concepts-in-plain-english)
3. [How the Design Works](#how-the-design-works)
4. [Design and Specifications](#design-and-specifications)
5. [Design Development](#design-development)
6. [Key Results at a Glance](#key-results-at-a-glance)
7. [Electric and Magnetic Field Analysis](#electric-and-magnetic-field-analysis)
8. [Choice of Metal](#choice-of-metal)
9. [Comparison with Previous Work](#comparison-with-previous-work)
10. [Why This Work Matters](#why-this-work-matters)
11. [Tools and Skills Demonstrated](#tools-and-skills-demonstrated)
12. [Repository Structure](#repository-structure)
13. [Publication and Conference](#publication-and-conference)
14. [Team](#team)

---

## The Big Picture

Checking whether a blood sample, saliva or tissue sample shows signs of disease usually means adding chemical dyes or tags ("labels"), waiting for a laboratory, and using expensive equipment.

This project explores a different approach: shine an invisible light on the sample and read the result from how that light is reflected.

- **Terahertz (THz) waves** are a type of invisible light that sits between microwaves and infrared. They are non-ionizing, so they do not damage biological samples the way X-rays can, and they are very sensitive to what a material is made of.
- We designed a **tiny patterned surface that traps terahertz light**. At two particular frequencies, almost no light is reflected back; nearly all of it is absorbed.
- When a sample is placed on the surface, these two trapping frequencies **shift slightly**. Measuring how much they shift tells us about the sample.

In short, this is a precise, compact, label-free sensing platform, developed and validated through electromagnetic simulation.

---

## Key Concepts in Plain English

| Concept | Explanation |
|---|---|
| **Terahertz (THz) waves** | Invisible light between microwaves (as in Wi-Fi or an oven) and infrared (as in a TV remote). Safe for biological samples and useful for identifying materials. |
| **Metamaterial** | A man-made surface whose *shape*, rather than its chemistry, gives it special properties. Think of a carefully carved sponge: the pattern of holes decides what it soaks up. Ours is a pattern of copper on a base layer. |
| **Absorber** | A surface that soaks up light instead of reflecting it, like a black T-shirt compared with a mirror. A "perfect" absorber takes in nearly 100%. |
| **Resonance** | Every structure has favourite frequencies at which it responds strongly, just as a wine glass rings at one particular note. At resonance, our structure absorbs the most light. |
| **Dual-band** | The device has two resonant frequencies instead of one, giving two independent readings and making sensing more reliable. |
| **Refractive-index sensing** | Every substance bends light by a characteristic amount (its refractive index). When the substance changes, this value changes slightly. The device detects it as a shift in the absorption frequency, like a guitar string changing pitch when it is tightened. |
| **Label-free** | No fluorescent dyes or chemical tags are needed, which lowers cost and time and leaves the sample unaltered. |

### The three performance metrics of a sensor

| Metric | Everyday analogy | What a higher value means |
|---|---|---|
| **Q-factor** | How sharp a musical note is: a pure tone versus a muddy one | A narrower, cleaner absorption peak, making tiny changes easier to detect |
| **Sensitivity (S)**, in THz per RIU | How far the "pitch" moves when the sample changes | A larger shift for the same change in sample, meaning a more sensitive sensor |
| **Figure of Merit (FOM)** | The overall score combining sensitivity and sharpness | Better all-round sensing performance |

*RIU stands for refractive index unit.*

---

## How the Design Works

The absorber is a **three-layer sandwich**, repeated thousands of times like tiles on a floor.

<div align="center">
<img src="assets/cross_section.png" alt="Cross-section of the absorber showing three layers" width="65%"/>

*Side view: patterned metal on top, a dielectric (insulating) layer in the middle, and a solid metal ground plane at the bottom.*
</div>

| Layer | Role |
|---|---|
| **Top: patterned metal** (a square ring and a Z-shaped strip) | Acts as the antenna that captures terahertz light. Its shape determines which frequencies are trapped. |
| **Middle: dielectric spacer** | The region where light energy is held and converted into heat. |
| **Bottom: solid metal sheet** | Acts as a mirror so that no light passes through. Whatever is not absorbed must be reflected, so it can be measured exactly. |

**Core intuition.** Light striking the surface can be reflected, transmitted, or absorbed. The bottom mirror blocks transmission, and the patterned top layer is tuned so that reflection is also nearly zero. What remains is absorption of close to 100%:

```
Absorption = 1 - Reflection - Transmission
             (Transmission is approximately 0 because of the metal ground plane)
```

### Why two shapes?

Rather than one complicated pattern, we combined two simple ones, each responsible for one resonance:

- **Square split-ring:** absorbs strongly near 0.73 THz
- **Z-shaped strip:** absorbs strongly near 0.94 THz

When placed together, the two shapes interact (couple), which shifts both resonances slightly and produces a clean two-peak response.

---

## Design and Specifications

<div align="center">
<img src="assets/unit_cell.png" alt="Top view of the unit cell with labelled dimensions" width="55%"/>

*Top view of a single unit cell of the absorber, with dimensions labelled.*
</div>

| Parameter | Meaning | Value |
|---|---|---|
| **A, B** | Overall unit cell size (period) | 50 µm × 50 µm |
| **C** | Outer square ring side length | 40 µm |
| **D** | Horizontal bar of the "Z" | 26.5 µm |
| **E** | Diagonal bar of the "Z" | 31.6 µm |
| **F, G** | Gaps between resonator sections | 2 µm |
| **H, I** | Strip widths | 5 µm |
| **Z angle** | Diagonal angle with respect to the x-axis | 133.5° |
| **Top-layer material** | Patterned conductor | Copper (σ = 6.3 × 10⁷ S/m) |

*For scale: 1 µm is one-millionth of a metre, and a human hair is roughly 70 µm wide, so a full unit cell is narrower than a single hair.*

**Simulation setup.** Finite Element Method (FEM) in **COMSOL Multiphysics**, with periodic boundary conditions along x and y (to mimic an infinitely repeating surface) and Perfectly Matched Layers (PMLs) along z (to absorb stray waves and avoid artificial reflections).

---

## Design Development

<div align="center">
<img src="assets/design1_design2.png" alt="Design 1 (split ring) and Design 2 (Z shape)" width="55%"/>

*Left: Design 1, the square split-ring. Right: Design 2, the Z-shaped resonator.*
</div>

### Step 1: Design 1 (square split-ring), about 99.2% absorption near 0.73 THz

<div align="center">
<img src="assets/absorption_design1.png" alt="Absorption spectrum of Design 1" width="60%"/>
</div>

### Step 2: Design 2 (Z-shape), about 96.7% absorption near 0.94 THz

<div align="center">
<img src="assets/absorption_design2.png" alt="Absorption spectrum of Design 2" width="60%"/>
</div>

### Step 3: Combined structure, dual-band absorber

<div align="center">
<img src="assets/absorption_combined.png" alt="Absorption spectrum of the combined dual-band design" width="65%"/>

*Two sharp absorption peaks: the two frequencies the sensor monitors.*
</div>

---

## Key Results at a Glance

<div align="center">

| Metric | Band 1 | Band 2 |
|:---|:---:|:---:|
| **Resonant frequency** | **0.7421 THz** | **0.9061 THz** |
| **Absorption** | **99.2%** | **97.79%** |
| **Bandwidth (FWHM)** | 0.0925 THz | 0.1502 THz |
| **Q-factor** | **8.0203** | **6.041** |

| Sensing performance | Value |
|:---|:---:|
| **Sensitivity** | **2.797 to 2.801 THz/RIU** |
| **Figure of Merit (FOM)** | **18.63 to 30.28 RIU⁻¹** |

</div>

### Highlights

- **Near-perfect absorption** at both frequencies, with almost no light wasted.
- **Polarization-independent behaviour:** performs well under both TE and TM polarizations, so the sensor does not depend on how the light is oriented.
- **Stable across incidence angles:** remains reliable even when the light does not strike head-on, which matters in real-world setups.
- **Tunable:** a parametric study showed that adjusting the dimensions moves the absorption peaks predictably, so the design can be adapted to other applications.
- **High sensitivity:** a very small change in the sample produces a large, easily measurable frequency shift (about 2.8 THz per unit change in refractive index).

---

## Electric and Magnetic Field Analysis

To explain *why* the device absorbs so well, and not only show that it does, we examined the electric field, the magnetic field, and how energy concentrates inside a unit cell at each resonance. Red and yellow indicate strong fields; blue indicates weak fields.

### Electric field

<table align="center">
<tr>
<td align="center"><img src="assets/efield_0p7421.png" width="100%"/><br/><b>At 0.7421 THz</b></td>
<td align="center"><img src="assets/efield_0p9061.png" width="100%"/><br/><b>At 0.9061 THz</b></td>
</tr>
</table>

### Magnetic field

<table align="center">
<tr>
<td align="center"><img src="assets/hfield_0p7421.png" width="100%"/><br/><b>At 0.7421 THz</b></td>
<td align="center"><img src="assets/hfield_0p9061.png" width="100%"/><br/><b>At 0.9061 THz</b></td>
</tr>
</table>

**Interpretation.** At each resonance, the light's energy is squeezed into small hotspots along the edges and corners of the metal, much like water funnelled into a narrow channel. That concentrated energy is converted into heat inside the structure, which is why so little light is reflected. These hotspots are also where a sample placed on top has the strongest effect, which is what makes the device a good sensor.

---

## Choice of Metal

The choice of metal strongly affects performance, so four were compared.

<div align="center">
<img src="assets/material_comparison.png" alt="Absorption spectra for gold, copper, silver and cobalt" width="70%"/>
</div>

| Metal | Observation | Practical assessment |
|---|---|---|
| **Gold** | Near-perfect absorption (about 99.5%), stable | Excellent, but expensive for large-scale use |
| **Silver** | Sharpest peaks (Q of about 9.4) | Strong performance, but oxidizes over time |
| **Copper** | High absorption (97 to 99%), moderate Q | Best balance of performance, scalability and cost |
| **Cobalt** | Low Q, broad peaks | Not suitable for precise biosensing |

A copper-silver hybrid configuration was also explored, aiming to combine silver's sharp resonance with copper's durability and low cost.

---

## Comparison with Previous Work

| Parameter | Ref. [15] | Ref. [16] | **This Work** |
|---|---|---|---|
| Absorber shape | Array of rings | Multilayer structure | **Ring with Z-shaped resonator** |
| Operating frequency | 4.5 to 5.6 THz | 4.5 to 5.6 THz | **0.74 to 0.91 THz** |
| Maximum absorbance | 99% | > 95% | **98 to 99.5%** |
| Q-factor | 8.948 | 5.359 | **8.0203** |
| Sensitivity | 3.880 THz/RIU | 429 GHz/RIU | **2.801 THz/RIU** |

**Takeaway.** The design reaches absorption and sharpness comparable to published work while operating at a much lower terahertz frequency (below 1 THz), where devices are generally easier and cheaper to work with. Compared with Ref. [16], it achieves roughly 6.5 times higher sensitivity and a higher Q-factor.

---

## Why This Work Matters

| Healthcare | Research and industry | Broader impact |
|---|---|---|
| Potential for **early disease detection** by spotting tiny changes in tissue or fluids | **Label-free** testing reduces the cost, time and chemicals normally required | Compact, chip-scale devices could enable **portable, low-cost diagnostics** |
| Non-ionizing THz waves are **safe for biological samples** | The same principle applies to food safety, environmental monitoring and security screening | A building block for next-generation **THz sensing, imaging and communication** hardware |

In one line: smaller, cheaper, faster and chemical-free sensing, built from a carefully designed pattern of metal.

---

## Tools and Skills Demonstrated

| Area | Details |
|---|---|
| **Simulation and EM modelling** | COMSOL Multiphysics, Finite Element Method (FEM), periodic boundary conditions, PML |
| **Electromagnetics and photonics** | Metamaterials, terahertz physics, impedance matching, S-parameters, resonance analysis |
| **Sensor engineering** | Q-factor, sensitivity, FOM, refractive-index sensing |
| **Design optimization** | Parametric sweeps, material comparison, angle and polarization robustness study |
| **Research and communication** | Technical writing in IEEE format, peer-reviewed shortlisting, conference presentation |

---

## Repository Structure

```
repository-root
├── assets/        Figures and graphs used in this README
├── paper/         Full conference paper (PDF)
├── certificate/   Conference presentation certificate
└── README.md      This file
```

---

## Publication and Conference

<div align="center">

### Presented at the 2026 Smart RF Communication, Photonics, Geoscience and Remote Sensing Conference (SCPGCON)

**Organized under IEEE**

</div>

This work was shortlisted after peer review and presented at the conference.

| | |
|---|---|
| **Paper** | *Dual-Band Terahertz Metamaterial Absorber with Enhanced Sensing Capabilities*: [Read the full paper (PDF)](paper/SCPGCON_Paper.pdf) |
| **Certificate** | [View the presentation certificate](certificate/SCPGCON_Certificate.pdf) |
| **Format** | IEEE conference paper |

## Team

Department of Electronics and Communication Engineering, **Sai Vidya Institute of Technology**, Rajanukunte, Bengaluru, India.

| Name | Role |
|---|---|
| **Tejashree S** | Author |
| **Chaya B M** | Author |
| **Chethan R** | Author |
| **Likith S** | Author |
