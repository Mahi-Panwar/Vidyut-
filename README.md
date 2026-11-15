# ⚡ Vidyut: Gandhi Sagar Renewable Nexus
### AI-Powered Integrated Solar + Wind + Hydro + BESS Hybrid Ecosystem

[![Three.js](https://img.shields.io/badge/Three.js-r128-black?logo=three.js)](https://threejs.org/)
[![WebGL](https://img.shields.io/badge/WebGL-2.0-red?logo=webgl)](https://get.webgl.org/)
[![Status](https://img.shields.io/badge/Status-Hackathon%20Prototype-success)](#)
[![License](https://img.shields.io/badge/License-MIT-blue)](#)

---

## 📌 Project Overview

**Vidyut (Gandhi Sagar Renewable Nexus)** is an AI-coordinated, dispatchable virtual power plant (VPP) concept designed for **Gandhi Sagar Dam, Mandsaur, Madhya Pradesh, India**.

Rather than designing three independent, disconnected power plants that strain the grid and suffer curtailment, **Vidyut** treats Solar, Wind, Hydro, and a Battery Energy Storage System (BESS) as **one unified renewable ecosystem** operated by an intelligent dispatch engine—the **Gandhi Sagar AI Energy Brain**.

```
                           ┌───────────────────────────┐
                           │   AI Energy Brain (VPP)   │
                           │ Forecasting & MPC Dispatch│
                           └─────────────┬─────────────┘
                                         │
        ┌───────────────────┬────────────┴───────┬───────────────────┐
        ▼                   ▼                    ▼                   ▼
┌───────────────┐   ┌───────────────┐   ┌────────────────┐   ┌───────────────┐
│ Ground/Float  │   │ Ridgeline     │   │ Existing Hydro │   │ LFP BESS      │
│ Solar (35-70M)│   │ Wind (10-20M) │   │ Firming (~5-10M│   │ (20-40 MWh)   │
└───────┬───────┘   └───────┬───────┘   └────────┬───────┘   └───────┬───────┘
        │                   │                    │                   │
        └───────────────────┴───────────┬────────┴───────────────────┘
                                        ▼
                        ┌───────────────────────────────┐
                        │ 33 kV / 132-220 kV Substation │
                        │      Evacuation to Grid       │
                        └───────────────────────────────┘
```

---

## 🚀 Live Demo & How to Run

1. **Option 1: Direct in Browser**
   - Clone or download this repository.
   - Double-click [`index.html`](index.html) (or `gandhi-sagar-nexus.html`) to launch in Google Chrome, Microsoft Edge, or Mozilla Firefox.
   - *Works completely offline* using the included [`three.min.js`](three.min.js) fallback or via CDN.

2. **Option 2: GitHub Pages**
   - Enable GitHub Pages in your repository settings (`Settings` → `Pages` → Source: `main` branch, folder: `/ (root)`).
   - Access the live digital twin instantly at `https://<username>.github.io/Vidyut-/`.

---

## ✨ Key Features & Capabilities

### 1. Photorealistic 3D Digital Twin & Terrain Model
- **Geological Stratification:** Procedural terrain skirt modeling 7 distinct geological rock and soil strata (`#5e432a` to `#6b665e`), providing a civil-engineering physical maquette feel.
- **Procedural Chambal Topography:** Mathematical heightmap $H(x,z)$ carving out the reservoir basin, Chambal River canyon, leveled infrastructure pads, and elevated northern ridgelines.
- **GPU Instanced Mesh Architecture:** Instanced rendering for solar arrays, single-axis tracker poles, 520 vegetation canopies, floating pontoons, and local settlements running at 60 FPS.
- **Physical Buoyancy Synchronization:** When switching between *Dry Season*, *Monsoon*, and *High Water*, the water surface plane dynamically raises, and the floating solar pontoons automatically float up.
- **Animated Energy Flows:** Dynamic particle trails illustrating real-time power transfers:
  - 🟡 **Yellow:** Ground & floating solar generation
  - 🔷 **Cyan:** Ridge wind generation
  - 🔵 **Blue:** Hydro turbine dispatch
  - 🟢 **Green:** Bidirectional BESS charging and discharging
  - ⚪ **White:** High-voltage catenary transmission line evacuation
- **Interactive 3D Terrain Caliper:** Built-in measurement tool calculating point-to-point distances (m), enclosed polygon area (ha), and relative elevation differences (m).
- **Lighting & Atmospheric Presets:** Toggle between **Daylight**, **Golden Hour / Evening**, **Night**, **Monsoon Rain**, and **Dry Season**.

### 2. AI Energy Brain: Real-Time Dispatch Simulator
Experience the rule-based real-time virtual power plant controller:
- **Diurnal Sun Curve & Cloud Cover:** Attenuation of solar irradiance based on hour of the day and real-time cloud percentage.
- **Wind Turbine Aerodynamics:** Cubic power curve adhering to cut-in (3 m/s), rated, and cut-out (25 m/s) wind speeds with active feathering protection.
- **Frequency Support (Primary Grid Regulation):** Automatic active power ramp-up from BESS/Hydro on under-frequency ($< 49.70\text{ Hz}$) and automated curtailment on over-frequency ($> 50.30\text{ Hz}$).
- **Peak Shifting & Battery Arbitration:** Pre-evening peak reservation ensuring battery state-of-charge (SOC) is held high during 15:00–18:00 to supply the 18:00–22:00 evening peak demand.
- **Edge Controller Fail-Safe Interlocks:** Hardware interlocks maintaining safe-state limits if communications or AI dispatch solvers fail.

### 3. Engineering Rigor & Honest Assumptions
Unlike generic presentations, Vidyut maintains high statutory and engineering integrity:
- **Verified Infrastructure:** Acknowledges the existing ~115 MW Gandhi Sagar Dam and powerhouse (operated by MPPGCL since c. 1960) under the **Dam Safety Act 2021**, strictly respecting irrigation and Central Water Commission (CWC) water-release rules.
- **Wildlife & Environmental Screening:** Visual exclusion zones draped on the 3D terrain marking the **Gandhi Sagar Wildlife Sanctuary 5 km eco-sensitive buffer**, bird/bat mortality risk corridors, and BESS fire-safety clearances.
- **Hydro Relations Calculator:** Real-time physics calculation $P = \rho \cdot g \cdot Q \cdot H \cdot \eta$ with editable discharge ($Q$), net head ($H$), and hydraulic turbine efficiency ($\eta$).

### 4. Dynamic Financial Workbench
- **Capacity Scaling:** Instant toggle between **50 MW** (35 MW Solar + 10 MW Wind + 5 MW Hydro + 20 MWh BESS) and **100 MW** (70 MW Solar + 20 MW Wind + 10 MW Hydro + 40 MWh BESS).
- **Comprehensive Sensitivity Modeling:**
  - Editable CAPEX (₹ cr/MW), Capacity Factors (%), and blended tariffs (₹/kWh).
  - Debt/equity ratios (70:30) and 15-year debt servicing (EMI).
  - **Base vs. Conservative Stress Test** ($-10\%$ CF, $-10\%$ tariff, $+15\%$ CAPEX) ensuring DSCR remains robust $> 1.25$.

---

## 📂 Repository Structure

```
Vidyut-/
├── index.html                 # Main landing file (GitHub Pages ready, standalone 3D twin + dashboard)
├── gandhi-sagar-nexus.html    # Original standalone project file
├── three.min.js               # Three.js r128 local fallback for 100% offline usage
├── README.md                  # Comprehensive technical documentation & project guide
└── files/
    ├── gandhi-sagar-nexus.html
    ├── README.txt             # Quick start notes
    └── three.min.js           # Three.js library file
```

---

## 🛠 Tech Stack

- **3D Graphics & Rendering:** [Three.js](https://threejs.org/) (r128), WebGL, PCF Soft Shadow Mapping, ACES Filmic Tone Mapping.
- **Frontend Architecture:** Vanilla JavaScript (ES6+), HTML5 Canvas, Responsive CSS with custom theme modes (Dark / Glassmorphic / Modern).
- **Physics & Simulation Engine:** Procedural Perlin/Simplex-style terrain heightmaps, Catenary wire curves, Particle-based fluid and electrical flow dynamics.
- **Mathematical Formulations:** Hydraulic potential energy formula, cubic wind aerodynamics, and empirical solar radiation diurnal modeling.

---

## 👥 Hackathon Presentation Guide

| Time | Topic | Action / Screen |
| :--- | :--- | :--- |
| **0:00 - 0:45** | **The Problem & Digital Twin** | Open 3D model, switch to *Evening (🌇)*, toggle *Energy Flows (ON)*. Demonstrate how solar drop-off is balanced by wind and BESS. |
| **0:45 - 1:45** | **AI Energy Brain in Action** | Navigate to *AI Brain* tab. Increase *Cloud Cover* to 80% $\rightarrow$ observe instant battery discharge. Set frequency to 49.60 Hz to trigger frequency response. |
| **1:45 - 2:30** | **Engineering & Financial Feasibility** | Switch between 50 MW and 100 MW. Click *Conservative* scenario to show project bankability, DSCR, and payback. Show environmental exclusion buffer zones. |
| **2:30 - 3:00** | **Q&A & Statutory Defense** | Address Dam Safety Act compliance, Wildlife Sanctuary clearances, and MP Transco grid interconnect feasibility. |

---

## 📜 Disclaimer

*This project is an advanced conceptual engineering model and pre-feasibility digital twin developed for hackathon demonstration. Terrain, layouts, costs, and capacity factors are illustrative prototypes and should be verified against official ground-truth data from MPPGCL, WRD MP, CWC, and MP Transco.*
