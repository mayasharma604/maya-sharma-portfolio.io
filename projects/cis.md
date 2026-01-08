---
layout: default
title: Computer Integrated Surgery
---

# Computer Integrated Surgery

## Overview
My work in Computer Integrated Surgery focuses on building perception‑driven, data‑centric systems for surgical simulation and skill assessment. Across multiple projects, I worked at the intersection of sensing, real‑time software pipelines, and algorithmic analysis to quantify surgical interaction, instrument motion, and procedural dynamics. The emphasis was on translating raw multimodal signals into interpretable, time‑synchronized representations of surgical behavior.

---

## Surgical Sensing & Data Pipelines

### Real‑Time Force & Pressure Sensing
I developed a software pipeline to capture, synchronize, and analyze force data from embedded conductive pressure sensors integrated within a hydrogel prostate phantom used for AEEP simulation.

**Key contributions**
- Designed a **Python‑based data acquisition and processing pipeline** interfacing with microcontroller hardware  
- Implemented **calibration and normalization algorithms** to mitigate sensor drift and baseline variability  
- Performed **time‑series analysis** to identify force peaks, transients, and sustained pressure patterns across procedural phases  
- Synchronized force signals with procedural video to enable **temporal alignment between surgeon motion and physical interaction**

This system enabled identification of high‑risk regions where excessive force was applied, forming the basis for future real‑time feedback and automated skill assessment.

---

### Hardware–Software Synchronization
A core challenge was aligning heterogeneous data streams in real time. I worked on:

- **Low‑latency multi‑channel data logging**  
- Timestamp‑based synchronization across force sensors, inertial data, and endoscopic video  
- Software abstractions that decoupled hardware sampling rates from higher‑level analysis, enabling rapid iteration without re‑instrumenting the system  

This modular design allows additional sensing modalities to be integrated with minimal changes to the pipeline.

---

## Instrument Motion & Pose Estimation

### Endoscope Tip Position & Orientation Estimation
To complement force sensing, I contributed to the software approach for estimating endoscope motion using inertial measurements.

**Software approach**
- Processed IMU data streams (gyroscope, accelerometer, magnetometer) to estimate **endoscope orientation and relative tip position**  
- Applied sensor fusion techniques to reduce noise and drift while maintaining responsiveness  
- Integrated motion estimates with force data to reason about **where and how force was applied** during surgical interaction  

This multimodal fusion enabled richer interpretation of surgeon behavior and supports downstream applications in perception, robotics, and intelligent assistance.

---

## Algorithmic Analysis of Surgical Workflow
Using synchronized force and motion data, I developed algorithmic methods to analyze surgical behavior.

- Temporal segmentation of procedures into clinically meaningful phases  
- Identification of force signatures associated with specific dissection actions  
- Comparative analysis across trials to study consistency and variability in expert performance  

This reframes surgical skill as a measurable perception and signal‑processing problem rather than a purely qualitative one.

---
