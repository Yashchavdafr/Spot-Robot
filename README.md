# 🤖 Boston Dynamics Spot Robot — 3R Planar Mechanism Design

> A complete engineering analysis and SolidWorks CAD project implementing a **3R Planar Mechanism** for quadruped leg actuation, modeled after the Boston Dynamics Spot robot.

---

## 📁 Repository Structure

```
.
├── Assemblage1.SLDASM        # Full leg assembly (SolidWorks Assembly)
├── BODY.SLDPRT               # Robot body part file
├── L bottom.SLDPRT           # Lower leg (shank) part file
├── L1.SLDPRT                 # Hip link part file (L₁ = 150 mm)
├── L2.SLDPRT                 # Thigh link part file (L₂ = 200 mm)
├── Capture 1.png             # Assembly render / screenshot 1
├── Capture 2.png             # Assembly render / screenshot 2
├── Capture 3.png             # Assembly render / screenshot 3
├── Capture 4.png             # Assembly render / screenshot 4
└── Report.pdf                # Full engineering analysis report
```

---

## 📐 Project Overview

This project presents a **detailed mechanical design and analysis** of a 3R (three revolute joint) planar leg mechanism inspired by the Boston Dynamics Spot robot. The 3R configuration was selected for its optimal balance of workspace coverage, control simplicity, and mechanical reliability.

### Mechanism Link Parameters

| Link | Name  | Length | Mass  | Material         |
|------|-------|--------|-------|------------------|
| L₁   | Hip   | 150 mm | 2.0 kg | Aluminum 6061-T6 |
| L₂   | Thigh | 200 mm | 1.5 kg | Aluminum 6061-T6 |
| L₃   | Shank | 250 mm | 1.0 kg | Aluminum 6061-T6 |

### Robot Specifications

| Parameter | Value |
|-----------|-------|
| Total Mass | 32.5 kg |
| Payload Capacity | 14 kg |
| Max Walking Speed | 1.6 m/s |
| Max Running Speed | 3.3 m/s |
| Battery Capacity | 605 Wh |
| Operating Time | 90 minutes |
| Mission Range | 8.6 km |
| Protection Rating | IP54 |

---

## 🔧 Engineering Analysis

### Kinematics

**Forward Kinematics** — Foot position in Cartesian coordinates:

```
x = L₁·cos(θ₁) + L₂·cos(θ₁+θ₂) + L₃·cos(θ₁+θ₂+θ₃)
y = L₁·sin(θ₁) + L₂·sin(θ₁+θ₂) + L₃·sin(θ₁+θ₂+θ₃)
```

**Workspace:**
- Maximum reach: 600 mm (L₁ + L₂ + L₃)
- Reachable workspace area: ~0.85 m²
- Optimal working zone: 250–450 mm from hip joint

### Dynamics

The complete dynamic model follows the standard Lagrangian form:

```
M(θ)θ̈ + C(θ,θ̇)θ̇ + G(θ) = τ
```

Where `M` is the inertia matrix, `C` accounts for Coriolis and centrifugal forces, and `G` is the gravitational vector.

### Joint Specifications

| Joint | Range of Motion | Continuous Torque | Peak Torque | Gear Ratio |
|-------|----------------|-------------------|-------------|------------|
| Hip (θ₁) | ±90° | 125 Nm | 200 Nm | 50:1 |
| Knee (θ₂) | ±120° | 100 Nm | 160 Nm | 40:1 |
| Ankle (θ₃) | ±90° | 60 Nm | 100 Nm | 30:1 |

All joints use **Brushless DC Servo Motors** with **Planetary Gear Reducers** and **20-bit absolute encoders**.

---

## 🛠️ Tools & Software

- **SolidWorks** — 3D CAD modeling and assembly
- **MATLAB / Simulink** *(referenced in report)* — Kinematic and dynamic simulation
- **FEA** — Structural stress analysis and validation

---

## 📄 Report

The full engineering report (`Report.pdf`) covers:

1. Executive Summary
2. Robot Specifications
3. 3R Planar Mechanism Design
4. Forward & Inverse Kinematic Analysis
5. Dynamic Analysis (Lagrangian Formulation)
6. Structural Design & Stress Analysis
7. Transmission System Specifications
8. Gait Analysis
9. Control System Design
10. Manufacturing Considerations & Tolerances

---

## 👤 Author

**Yashchavdafr**
- Repository: `Yashchavdafr/Report`
- Initial commit + design files uploaded 7 months ago

---

