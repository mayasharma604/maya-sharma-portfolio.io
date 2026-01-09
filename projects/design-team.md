---
layout: default
title: Real-Time Force Feedback for Surgical Simulation
show_title: false
---

# Real-Time Quantitative Force Feedback for Surgical Simulation  
**Advanced Design Team (UroSim) — Johns Hopkins University**

## Overview
This project focused on developing a **software-driven perception and sensing framework** for objective feedback in high-fidelity surgical simulation. Many existing simulation platforms rely on qualitative assessment or expert supervision, with limited access to **real-time, quantitative measures of physical interaction**, particularly applied force.

Our team built a **sensor-integrated simulation system** that captures localized force and interaction data during complex endoscopic procedures. The system enables structured analysis of tool–tissue interaction patterns, supporting data-driven assessment of technique while remaining suitable for scalable simulation environments.

> Specific anatomical details, device configurations, and clinical parameters have been intentionally abstracted to protect confidential work.

---

## My Role
**Team Lead — Systems Integration & Data / Perception Pipeline**
- Led end-to-end system design across sensing, data acquisition, and software abstraction  
- Designed calibration and validation workflows for distributed sensor inputs  
- Built real-time data pipelines for synchronized multimodal signal processing  
- Coordinated evaluation with domain experts and guided data interpretation  
- Contributed to technical documentation and research dissemination  

---

## Technical & Algorithmic Approach
The core contribution of this work is a **real-time perception pipeline** that converts raw multimodal sensor signals into structured, time-aligned representations suitable for analysis and learning-based extensions.

At a systems level, the pipeline follows a robotics-inspired architecture:
> **Signal acquisition → state estimation → temporal alignment → data abstraction**

### Signal Acquisition & Processing
Distributed sensor signals were streamed through an embedded acquisition layer into a higher-level software stack. The processing pipeline included:
- Sensor calibration and baseline normalization  
- Noise filtering and drift compensation  
- Continuous multichannel time-series ingestion  

Raw analog measurements were transformed into **localized force and pressure estimates** using resistance-based signal models. Emphasis was placed on numerical stability and repeatability rather than device-specific tuning.

---

### Instrument State Estimation (IMU-Based)
To infer tool motion without external tracking infrastructure, inertial measurement unit (IMU) data (gyroscope, accelerometer, magnetometer) were processed to estimate **instrument pose trends over time**.

Key software concepts:
- Sensor fusion to combine inertial signals into a stable state estimate  
- Temporal smoothing and bias mitigation for noisy real-world signals  
- Frame-consistent representation of motion suitable for downstream correlation  

This approach supports **self-contained state estimation**, enabling deployment in simulation settings where optical or electromagnetic tracking is impractical.

---

### Multimodal Synchronization & Data Abstraction
A Python-based pipeline was developed to:
- Timestamp and synchronize force, pressure, and motion data streams  
- Segment recordings by procedural phase  
- Generate structured datasets for downstream analysis  

Low-level sensor data was abstracted into higher-level representations that enabled detection of:
- High-force interaction events  
- Phase-dependent force patterns  
- Regions associated with elevated mechanical stress  

This abstraction layer mirrors perception pipelines used in robotics and intelligent systems, emphasizing **clean interfaces, modularity, and extensibility**.

---

## ML / AI Features
While the system is deterministic by design, the generated datasets and abstractions are explicitly structured to support learning-based methods, including:
- Skill assessment via temporal pattern recognition  
- Anomaly detection based on force–motion relationships  
- Phase-aware feedback models  
- Trajectory-conditioned performance evaluation  

The project emphasizes **data quality, synchronization, and representation**.

---

## Key Capabilities
- Real-time, localized force sensing in simulation  
- Multimodal sensor fusion without external tracking infrastructure  
- Time-aligned force and motion representations  
- Scalable, non-invasive sensing architecture  

---

## Why This Matters
Complex surgical procedures demand precise control of force and motion, yet training often lacks objective feedback. This work demonstrates how **perception-driven software systems** can surface quantitative insights from physical interaction data, reducing reliance on subjective assessment.

The framework supports safer skill acquisition, objective evaluation, and future integration of intelligent feedback systems in simulation-based training.

---

## Outcomes
- Demonstrated feasibility of real-time force-aware simulation  
- Identified repeatable interaction patterns correlated with procedural phases  
- Established a reusable perception pipeline for simulation environments  

Observed limitations in sensor robustness informed design tradeoffs and future system iterations, reinforcing the importance of software abstraction over hardware specificity.

---

## Skills & Tools
**Perception & Systems**
- Multimodal sensor fusion  
- State estimation from noisy signals  
- Real-time signal processing  

**Software & Data**
- Python-based data pipelines  
- Time-series processing and event segmentation  
- Hardware–software synchronization  
- Dataset generation for learning-based systems  

**Engineering Practice**
- Technical documentation (DHF, risk analysis, validation planning)  
- Cross-disciplinary collaboration  
- Research communication  

---

*Details have been intentionally limited to protect confidential work.  
This project will be presented at the International Meeting on Simulation in Healthcare (IMSH) 2026.*
