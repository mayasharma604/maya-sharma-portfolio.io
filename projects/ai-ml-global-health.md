---
layout: default
title: ParaVision — AI for Malaria Microscopy
---
# ParaVision: AI‑Based Parasite Quantification for Malaria Diagnosis
**Computer Vision · Deep Learning · Global Health · Medical AI**  
*YOLOv8 · Python · PyTorch · OpenCV · Data Augmentation*

ParaVision is an AI‑driven computer vision system designed to automate **parasite quantification in malaria blood smears**, addressing a critical diagnostic bottleneck in low‑resource clinical settings. The project focuses on **accurate, scalable, and explainable object detection** to support clinical decision‑making and public‑health surveillance.

---

## Problem Context
Manual microscopy is the clinical gold standard for malaria diagnosis, but it is:
- Slow (15+ minutes per slide)
- Highly variable between technicians
- Resource‑intensive in regions with limited trained personnel

Accurate **parasite quantification** directly affects disease severity assessment, treatment decisions, and surveillance quality. Existing automated solutions struggle with generalization, cost, or insufficient accuracy.

---

## Technical Approach
We developed an **AI‑based object detection pipeline** to identify and localize malaria parasites and white blood cells (WBCs) in **thick‑smear microscopy images**, prioritizing robustness and deployability.

### Model & Training
- **Architecture:** YOLOv8s (selected for accuracy–efficiency tradeoff)
- **Dataset:** Lacuna Malaria Dataset (3,045 images)
- **Classes:** Parasites, WBCs
- **Training Setup:**
  - 70 / 20 / 10 train–val–test split
  - 100 epochs, AdamW optimizer
  - Extensive data augmentation to simulate real‑world smear variability
- **Compute:** Single NVIDIA A100 GPU

### Image Processing Pipeline
- Automated background removal via contour detection
- Standardized resizing and tiling to preserve small object detail
- Careful handling of partial bounding boxes to reduce label noise

---

## System Design Considerations
- Designed to integrate into **existing clinical workflows**
- Supports smartphone‑captured microscope images
- Lightweight model suitable for **low‑resource deployment**
- Outputs interpretable bounding boxes to keep humans in the loop

---

## Analysis & Insights
 - Parasite localization is significantly harder than WBC detection due to scale, morphology, and contrast
 - Error analysis highlighted recall as the primary bottleneck, motivating future work in multi‑stage detection and larger architectures
 - Demonstrated that object detection models can support quantitative clinical metrics, not just classification

---

## Impact & Relevance
- Reduces diagnostic variability across technicians
- Accelerates slide review without specialized hardware
- Produces standardized data for **national malaria surveillance**
- Aligns with **UN SDG 3 (Good Health)** and **SDG 9 (Innovation & Infrastructure)**

---

## Limitations & Future Work
- Dataset sourced from a single institution → limited domain diversity
- Recall and quantification error require improvement for clinical deployment
- Future work includes:
  - Multi‑site data expansion
  - Higher‑capacity models and multi‑stage detection
  - Automated parasite density estimation
  - Offline‑capable interfaces and health‑system integration

---

## Key Skills
- End‑to‑end ML system design (data → model → evaluation → deployment context)
- Strong grounding in **computer vision, optimization, and error analysis**
- Ability to translate global health constraints into tractable ML solutions
- Experience applying ML to **real‑world, high‑impact** healthcare problems

---


**Reference:** WHO Malaria Microscopy Quality Assurance Manual
