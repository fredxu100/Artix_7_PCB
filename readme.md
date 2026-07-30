# High-Speed 6-Layer Systolic Array Matrix Processor PCB

<p align="center">
  <img src="docs/renders/PCB_iso.png" alt="PCB 3D Render" width="100%">
</p>

## Overview
This repository contains the complete design files, manufacturing outputs, and stackup documentation for an 8-layer high-speed PCB designed around an XC7A FPGA 

---
## Technical Specifications

| Parameter | Specification |
| :--- | :--- |
| **Layer Count** | 8 Layers (SIG1 - GND - SIG2 - GND - PWR - SIG3 GND - SIG4) |
| **Board Dimensions** | 3000 mil × 3000 mil |
| **Impedance Control** | 50 Ω Single-Ended, 90/100 Ω Differential Pairs |
| **Primary CAD Tool** | Altium Designer |

---

## High-Speed Design & Signal Integrity Highlights

### 1. Stackup & Controlled Impedance Architecture
To minimize crosstalk and electromagnetic interference (EMI), an 8-layer stackup was implemented with solid reference planes directly adjacent to primary high-speed signal layers:

* **L1 (Top):** Components, general signal lines, fanout
* **L2 (GND1):** Solid reference ground plane
* **L3 (Inner 1):** High speed signal routing
* **L4 (GND1):** Solid reference ground plane
* **L5 (Power):** Split power planes for 1, 1.35, 1.8, and 3.3 V
* **L6 (Inner 2):** High speed signal routing
* **L7 (GND2):** Solid reference ground plane
* **L8 (Bottom):** High-density breakout signals & secondary routing, decoupling capacitors

<p align="center">
  <img src="docs/renders/stackup.png" alt="Layer Stackup Specs" width="85%">
</p>
---

## Repository Structure

```text
systolic-array-matrix-processor-pcb/
├── README.md                      <-- Project landing page
├── LICENSE                        <-- CERN Open Hardware / MIT License
├── .gitignore                     <-- Altium temp file filter
├── docs/                          <-- Documentation & visual renders
│   ├── renders/                   <-- Board renders and breakout views
│   ├── Schematics.pdf             <-- Clean vector schematic export
│   └── Layer_Stackup_Profile.png  <-- Stackup configuration
├── fabrication_pack/              <-- Gerber X2, NC Drill, and IPC-2581 outputs
├── assembly_pack/                 <-- Interactive BOM, Centroid CSV, and Pick & Place
└── hardware_source/               <-- Raw Altium (.PrjPcb, .SchDoc, .PcbDoc, .OutJob)
