---
layout: default
title: Computer Integrated Surgery
---

# Computer Integrated Surgery (CIS) — Software Projects

**Medical Tracking, Calibration, and Registration Systems**  
*Python · Numerical Linear Algebra · Optimization · Geometry · Sensor Fusion*

Worked on a sequence of software systems for medical navigation and robotic perception, focused on 3D geometry, calibration, registration, and tracking pipelines used in image‑guided surgery. Implemented end‑to‑end algorithms for EM and optical tracking, sensor calibration, distortion correction, and CT‑space navigation, emphasizing numerical stability, modular design, and algorithmic correctness.

---

## 1. Rigid Registration & Coordinate Frame Infrastructure

Built a reusable 3D geometry and transformation library supporting rotations, translations, and homogeneous transforms across multiple coordinate frames.

**Software approach**
- Implemented SVD‑based least‑squares rigid registration (Arun et al., 1987) for 3D point sets  
- Designed utilities for:
  - Frame chaining and inversion  
  - Batch transformation of point clouds  
  - Reflection detection and correction (`det(R) = +1`)  
- Used NumPy for vectorized linear algebra and numerical robustness  

**Key abstractions**
- `register_points(A, B) → (R, t)`  
- `apply_transform(R, t, pts) → frame‑consistent point mapping`  
- Clear separation between geometry, I/O, and algorithms  

---

## 2. Probe Pivot Calibration (EM & Optical Tracking)

Developed calibration algorithms to recover probe tip position from tracked marker data across time.

**Algorithmic formulation**
- Modeled pivot calibration as a stacked linear least‑squares problem  
- Solved for:
  - Fixed probe tip offset in local coordinates  
  - Stationary pivot point in tracker coordinates  
- Unified EM and optical pivot calibration under the same mathematical framework  

**CS emphasis**
- Reduced geometric calibration to a solvable linear system  
- Designed frame‑agnostic pipeline reusable across sensor modalities  
- Quantified residuals to evaluate calibration accuracy  

---

## 3. EM Tracker Distortion Correction (Nonlinear Modeling)

Implemented a nonlinear distortion correction pipeline for EM tracking systems.

**Software & ML‑adjacent approach**
- Modeled EM field distortion using 3D Bernstein polynomial basis functions  
- Constructed a design matrix and solved a large least‑squares optimization problem  
- Built a callable correction function mapping distorted → corrected coordinates  

**Why this matters**
- Introduces function approximation, regression, and numerical optimization  
- Similar structure to learning a spatial correction model from data  
- Emphasizes stability via coordinate normalization and basis design  

---

## 4. Fiducial Localization & EM–CT Registration

Built a full pipeline to localize fiducials and register tracker space to CT image space.

**Pipeline**
- Apply distortion correction to EM measurements  
- Use calibrated probe tip to compute fiducial positions  
- Perform rigid EM → CT registration via least‑squares  
- Validate alignment using known ground‑truth datasets  

**Key ideas**
- Multi‑stage transformation pipelines  
- Error propagation awareness across steps  
- Strong separation between sensing, calibration, and registration logic  

---

## 5. Navigation Pipeline (End‑to‑End System)

Integrated all components into a navigation system that outputs probe tip positions in CT coordinates.

**End‑to‑end flow**
- Sensor correction → probe pose estimation → coordinate registration → CT‑space output  
- Designed for extensibility to real‑time navigation data  
- Emphasis on deterministic, debuggable computation over black‑box methods  

---

## 6. Surface Registration & ICP (Perception‑Focused Project)

Implemented a geometric perception pipeline using Iterative Closest Point (ICP) to align tracked probe data to a surface mesh.

**Algorithms implemented**
- Closest point on triangle (barycentric coordinates)  
- Closest point on mesh (brute‑force, accuracy‑first)  
- Iterative Closest Point (ICP) with:
  - Matching step (closest surface point)  
  - Registration step (SVD‑based alignment)  
  - Convergence criteria  

**Relevance**
- Core ideas from robot perception and mapping  
- Explicit handling of corner cases and numerical instability  
- Mirrors real‑world pose refinement in robotics systems  

---

## Software & Data Emphasis
- Python‑based numerical computing (NumPy, linear algebra)  
- Time‑series processing of multi‑frame sensor data  
- Sensor fusion across EM, optical, and CT coordinate frames  
- Least‑squares optimization, regression, and geometric modeling  
- Modular architecture enabling reuse across projects  

---

## What This Demonstrates
- Strong grounding in algorithms, math, and systems thinking  
- Ability to translate physical sensing problems into solvable computational models  
- Experience building full perception and calibration pipelines, not just isolated scripts  
- Direct relevance to ML, robotics, perception, and medical robotics software roles  

