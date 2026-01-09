---
layout: default
title: Computer Integrated Surgery
---

# Computer Integrated Surgery — Software Projects

**Medical Navigation, Tracking, and Perception Systems**  
*Python · Numerical Linear Algebra · Optimization · Geometry · Sensor Fusion*

Worked on a suite of software systems for medical navigation and robotic perception, focused on translating raw sensor data into accurate, stable, and interpretable spatial information for image‑guided surgery. The work centered on building end‑to‑end pipelines for tracking, calibration, registration, and navigation, emphasizing numerical robustness, modular abstractions, and algorithmic correctness in safety‑critical settings.

These projects collectively address a core problem in medical robotics: **how to reliably map physical instrument motion into a consistent 3D coordinate system that aligns with medical imaging data**.

---

## 1. Rigid Registration & Coordinate Frame Infrastructure

Built a reusable 3D geometry and transformation library to support consistent reasoning across multiple coordinate frames (tracker, instrument, patient, and image space).

**Software approach**
- Implemented SVD‑based least‑squares rigid registration (Arun et al., 1987) for aligning 3D point sets  
- Designed utilities for:
  - Coordinate frame chaining and inversion  
  - Batch transformation of point clouds  
  - Reflection detection and correction to enforce valid rotations  
- Used NumPy for vectorized linear algebra and numerical stability

**Key abstractions**
- Clear separation between geometry, algorithms, and I/O logic

---

## 2. Probe Pivot Calibration (EM & Optical Tracking)

Developed calibration algorithms to recover the physical tip location of tracked surgical probes using time‑series marker data.

**Algorithmic formulation**
- Modeled pivot calibration as a stacked linear least‑squares problem  
- Solved for:
  - Fixed probe tip offset in local probe coordinates  
  - Stationary pivot point in tracker coordinates  
- Unified EM and optical calibration under a single mathematical framework

**Software focus**
- Reduced a physical calibration problem to a solvable linear system  
- Built frame‑agnostic, sensor‑independent calibration pipelines  
- Quantified residual error to assess calibration quality

---

## 3. EM Tracker Distortion Correction (Nonlinear Modeling)

Implemented a nonlinear correction pipeline to compensate for spatial distortion in electromagnetic (EM) tracking systems.

**Software & ML‑adjacent approach**
- Modeled distortion using 3D Bernstein polynomial basis functions  
- Constructed a design matrix and solved a large least‑squares optimization problem  
- Built a callable correction function mapping distorted → corrected coordinates

**Why this matters**
- Applies regression and function approximation to spatial data  
- Mirrors learning a correction model from noisy measurements  
- Emphasizes numerical stability via normalization and basis design

---

## 4. Fiducial Localization & EM–CT Registration

Built a full pipeline to align tracked physical space with preoperative CT imaging.

**Pipeline**
- Apply EM distortion correction  
- Use calibrated probe tip to localize fiducial markers  
- Perform rigid EM → CT registration via least‑squares optimization  
- Validate alignment against known ground‑truth datasets

**Key ideas**
- Multi‑stage transformation pipelines  
- Awareness of error propagation across steps  
- Strong separation between sensing, calibration, and registration logic

---

## 5. Navigation Pipeline (End‑to‑End System)

Integrated all components into a navigation system that outputs real‑time probe tip positions in CT image coordinates.

**End‑to‑end flow**
- Sensor correction → probe pose estimation → coordinate registration → CT‑space output  
- Designed for extensibility to streaming, real‑time data  
- Prioritized deterministic, debuggable computation over black‑box methods

---

## 6. Surface Registration & ICP (Perception‑Focused Project)

Implemented a geometric perception pipeline to align tracked probe data with a 3D surface mesh using Iterative Closest Point (ICP).

**Algorithms implemented**
- Closest point on triangle (barycentric coordinates)  
- Closest point on mesh (brute‑force, accuracy‑first)  
- Iterative Closest Point (ICP):
  - Matching step (closest surface point)  
  - Registration step (SVD‑based alignment)  
  - Convergence criteria and stopping conditions

**Relevance**
- Core concepts from robot perception and mapping  
- Explicit handling of edge cases and numerical instability  
- Reflects real‑world pose refinement used in robotics systems

---

## Software & Data Emphasis

- Python‑based numerical computing (NumPy, linear algebra)  
- Time‑series processing of multi‑frame sensor data  
- Sensor fusion across EM, optical, and CT coordinate frames  
- Least‑squares optimization, regression, and geometric modeling  
- Modular software architecture enabling reuse across systems

---

## Key Skills

- Strong grounding in algorithms, math, and systems design  
- Ability to translate physical sensing problems into computational models  
- Experience building full perception and calibration pipelines, not just isolated scripts  
- Direct relevance to ML, robotics, perception, and medical robotics software roles
