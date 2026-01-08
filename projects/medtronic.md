---
layout: default
title: Medical Device Engineering Projects — Medtronic
---

# Medtronic — Decision Support Software for Surgical Product Bundling

**Product Strategy · Decision Systems · Backend Logic · Healthcare Technology**

Developed an end-to-end software-driven decision system from the ground-up to support sales teams generate accurate, explainable product bundles for complex surgical platforms. The project addressed the gap between highly modular medical hardware offerings and the cognitive burden placed on sales representatives to configure optimal solutions for diverse clinical environments.

---

## Problem Context

Surgical products are not sold in one-to-one configurations. Individual components (e.g., handles, batteries, displays) interact through compatibility constraints, care-area requirements, and customer-specific priorities. Sales representatives must synthesize a large number of inputs under time pressure, often without clear system-level guidance.

---

## Core Software Challenge

Translate a high-dimensional, constraint-heavy product space into clear, justifiable recommendations that:

- Adapt to different clinical use cases (e.g., teaching environments, technology upgrades, sustainability goals)
- Respect backend product dependencies and compatibility constraints
- Align with existing sales strategy and available product options
- Are easy to explain, justify, and defend to customers

---

## Technical & Systems Approach

- Designed a backend decision-logic framework in Python to model product compatibility, dependencies, and configuration constraints
- Developed a **priority-weighted recommendation strategy** to balance competing customer objectives without hard-coding static bundles
- Structured an **input collection and normalization layer** to capture care area, customer preferences, and deployment context
- Implemented **environment matching and dependency mapping** to automatically validate feasible configurations
- Generated frontend system with bundle outputs with concise **rationale summaries**, enabling transparency and explainability in recommendations

---

## Key Software Features

- Rule-based decision modeling with extensibility toward future data-driven or optimization-based approaches
- Abstraction of product relationships into reusable logic rather than brittle, static mappings
- Clear separation between:
  - Input handling
  - Decision logic
  - Output generation and explanation
- Designed for scalability across product lines, care areas, and customer profiles

---

## Impact

- Reduced cognitive load and time required for sales representatives to formulate recommendations
- Improved consistency, accuracy, and confidence in bundle configurations
- Enabled flexible, customer-specific solutions without increasing system complexity

---

## Skills

- Ability to translate ambiguous business and clinical requirements into structured software systems
- Strong systems thinking at the intersection of product strategy, user needs, and backend logic
- Experience designing **explainable decision-support tools** in regulated, real-world healthcare environments

*Details limited due to confidentiality.*
