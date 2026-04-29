# **EventReflex-DroneNav**

**Event-Based Perception and Spiking-Inspired Decision Making for Low-Power Autonomous UAV Navigation**

A **minimal, interpretable neuromorphic autonomy pipeline** demonstrating how event-based sensing and spiking-inspired dynamics can drive closed-loop navigation without learning, dense vision models, or hardware-specific dependencies.

> This project intentionally prioritizes **conceptual correctness and system-level design** over benchmark performance or hardware deployment.

---

## Motivation

Autonomous aerial vehicles operating at the edge face strict constraints on:

- **Perception latency**
- **Onboard power consumption**
- **Robustness to lighting and motion**
- **Deployable compute**

Traditional frame-based RGB + CNN pipelines process redundant data and introduce latency.  
Neuromorphic systems, **event-based vision + spiking computation**, offer an asynchronous, sparse, and power-efficient alternative.

This project presents a **minimal end-to-end autonomy loop** to validate that idea at the system-design level.

## What This Micro-Implementation Project Is (and Is Not)

### What this project demonstrates

- Event-based perception via temporal contrast
- Spiking-inspired decision making using LIF neurons
- Closed-loop autonomous navigation
- Interpretable, reflex-like behavior

### What this project does NOT attempt

- No learning or training
- No hardware benchmarking
- No SLAM or planning
- No flight dynamics

## System Overview

```
Environment
 → Event-Based Sensing
 → Spiking-Inspired Integration
 → Action Selection
 → Environment Update
```

## Mathematical Foundations

### Event-Based Vision

Synthetic ON/OFF events are generated using temporal contrast:

$$ΔI = I_t − I_{t−1}$$

### Spiking Neurons

Leaky Integrate-and-Fire (LIF) dynamics integrate event-driven currents and emit spikes when a threshold is crossed.

### Action Encoding

Directional neuron activity determines the navigation action.

## Environment

- 2D AgriDroneRL environment
- Local patch-based observation
- First-visit reward only
- Utility derived from satellite imagery (VARI)

## Folder Structure

```
EventReflex-DroneNav/
├── implement_minimal.ipynb
├── implement_minimal.pdf
├── data/
│   └── satellite.png
├── requirements.txt
└── README.md
└── LICENSE
```

## How to Run

```bash
pip install -r requirements.txt
jupyter notebook
```

Open `implement_minimal.ipynb` and run all the cells.

## References

1. **Event-based Vision: A Survey** - Gallego et al. (arXiv)  
   Comprehensive overview of event cameras, algorithms, and processing techniques.  
   https://arxiv.org/abs/1904.08405

2. **Hardware, Algorithms, and Applications of the Neuromorphic Vision Sensor: A Review** - Cimarelli et al. (arXiv, 2025)  
   Recent survey covering neuromorphic vision hardware, algorithms, and real-world applications.  
   https://arxiv.org/abs/2504.08588

## Conclusion
This project demonstrates how **event-based sensing and spiking dynamics** can form a valid foundation for neuromorphic autonomy at the architectural level.

##### **Author**: Ayushman Mishra  
https://github.com/aymisxx

---
