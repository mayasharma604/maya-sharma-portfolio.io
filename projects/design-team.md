layout: default
title: Real-Time Force Feedback for Surgical Simulation
---

# Real-Time Quantitative Force Feedback for Surgical Simulation  
**Advanced Design Team (UroSim) — Johns Hopkins University**

## Overview
This project focused on improving **training for Advanced Endoscopic Enucleation of the Prostate (AEEP)**, a technically demanding urologic procedure with a steep learning curve and limited access to structured training tools. While modern prosthetic and surgical systems continue to advance, many simulation platforms lack **real-time, quantitative feedback**, especially related to applied force — a critical factor in avoiding injury to sensitive anatomical structures.

Our team developed a **sensor-integrated hydrogel prostate simulator** capable of capturing **live force distribution data** during simulated AEEP procedures, enabling objective analysis of surgical technique and interaction with anatomy.

---

## My Role
**Team Lead — Systems Integration & Data Analysis**

- Led interdisciplinary collaboration between biomedical engineering students and clinical partners  
- Designed and integrated conductive pressure sensors into a hydrogel simulation phantom  
- Developed calibration and data collection pipelines for real-time force measurement  
- Coordinated testing with expert surgeons and supported data interpretation  
- Contributed to manuscript preparation for journal submission  

---

## Technical Approach
This project was driven by the design of a **software-centric sensing and perception pipeline** for real-time analysis of surgeon–instrument interaction during simulated AEEP procedures.

At a high level, the system abstracted raw multimodal sensor inputs into synchronized, time-aligned representations of **force, pressure distribution, and instrument state**, enabling structured analysis of surgical technique.

### Signal Acquisition & Processing
Analog signals from distributed pressure sensors were digitized via an embedded controller and streamed to a higher-level processing layer. Software routines handled:
- Sensor calibration and baseline normalization
- Noise filtering and drift compensation
- Continuous multichannel time-series acquisition

Force and pressure were inferred through resistance-based signal modeling, producing localized estimates of mechanical interaction across anatomically relevant regions of the phantom.

### Instrument State Estimation
To approximate endoscope motion without relying on external tracking systems, inertial measurement unit (IMU) data (gyroscope, accelerometer, and magnetometer) were processed to estimate **endoscope tip position and motion trends** within the simulator. Sensor fusion techniques were used to transform raw IMU signals into a stable representation of instrument pose over time, enabling correlation between endoscope positioning and observed force patterns.

This approach allowed endoscope behavior to be inferred using onboard sensing alone, supporting scalable deployment in simulation environments without optical tracking infrastructure.

### Data Abstraction & Temporal Alignment
A Python-based software pipeline was developed to:
- Timestamp and synchronize force, pressure, and instrument state data
- Segment recordings by procedural phase
- Generate structured datasets suitable for downstream analysis

By abstracting low-level sensor signals into higher-level representations, the system enabled identification of **high-force events**, **procedure-specific interaction patterns**, and **anatomical regions associated with elevated mechanical stress**.

The resulting architecture uses perception pipelines similar to what is used in robotics and intelligent systems. The algorithmic framework in this project involves multimodal sensor fusion, real-time signal processing, state estimation from noisy inputs, and data-driven interpretation of physical interaction.

This framework provides a foundation for future extensions into **learning-based skill assessment**, **trajectory-aware feedback**, and **adaptive surgical training systems** that integrate perception, control, and human–robot interaction principles.

---

## Key Capabilities
- **Real-time force sensing** during simulated endoscopic procedures  
- **Anatomically distributed sensing** across clinically relevant prostate regions  
- **Synchronized data + video analysis** for objective skill assessment  
- **Noninvasive, low-cost sensing approach** suitable for simulation environments  

---

## Why This Matters
AEEP offers strong clinical outcomes but remains underutilized due to the **high training burden** required to reach proficiency. Current training models rely heavily on expert supervision and lack quantitative guidance on safe force application.

This work demonstrates the feasibility of **force-aware surgical simulation**, opening pathways for:
- Reduced dependence on continuous expert oversight  
- Objective feedback for trainees  
- Safer skill acquisition in high-risk anatomical regions  

---

## Outcomes & Impact
- Demonstrated feasibility of capturing localized force patterns during simulated AEEP  
- Identified procedure phases associated with elevated mechanical stress  
- Informed design improvements for future training platforms  

While this prototype revealed challenges related to sensor robustness and repeatability, it provides a strong foundation for **next-generation simulation systems** that integrate multimodal feedback to improve surgical education.

---

## Future Directions
- Optimizing sensor placement near high-risk anatomical regions  
- Simplifying sensor layouts for improved reliability  
- Integrating additional sensing modalities to infer instrument orientation  
- Expanding the framework to other endoscopic and robotic surgical procedures  

---

## Skills & Tools
**Biomedical Systems**
- Surgical simulation design  
- Sensor integration & calibration  
- Embedded systems for data acquisition  

**Software & Data**
 - Designed end‑to‑end Python-based data pipelines for real-time acquisition, calibration, and analysis of multimodal sensor streams
 - Implemented time‑series processing and event segmentation to identify force patterns across procedural phases
 - Developed hardware–software synchronization mechanisms to temporally align sensor data with procedural video and instrument state
 - Applied signal conditioning, normalization, and noise mitigation to improve robustness of real-world sensor measurements
 - Generated structured datasets to support future learning-based skill assessment, anomaly detection, and perception-driven feedback

**Collaboration**
- Clinical–engineering collaboration  
- Technical documentation (Design History Files (DHF), Competitive Analyses, Concept Evaluations, Risk Analyses, Regulatory Pathways, V&V Testing, etc.)
- Research writing  

---

*Details have been intentionally limited to protect confidential work. This work will be presented at International Meeting on Simulation in Healthcare (IMSH) 2026.*


