# CNN Hardware Accelerator (45nm ASIC Implementation)

![Status](https://img.shields.io/badge/Status-Completed-success)
![Technology](https://img.shields.io/badge/Technology-GPDK45nm-blue)
![Language](https://img.shields.io/badge/Language-VHDL-orange)
![Tools](https://img.shields.io/badge/Tools-Cadence_Innovus_|_Genus-red)

## 📌 Project Overview

This project consists of the design, verification, and physical implementation of a **Convolutional Neural Network (CNN) Hardware Accelerator**, specifically targeting the 4th Convolutional Layer (`cnn_conv4`).

The design bridges the gap between high-level AI algorithms and physical silicon implementation. It features a custom Floating-Point Unit (FPU), a pipelined Multiply-Accumulate (MAC) architecture, and a complete RTL-to-GDSII flow using the **Cadence Digital Implementation Suite**.

### Key Features
* **Custom Precision:** 27-bit Floating Point format (1 Sign, 8 Exponent, 18 Mantissa) optimized for inference accuracy vs. area trade-off.
* **Activation Function:** Hardware implementation of ReLU (Rectified Linear Unit).
* **Architecture:** Parallel/Pipelined processing of 32 input features + Bias addition.
* **Physical Design:** Full layout implementation in 45nm technology (GPDK045).

---

## 🏗 Architecture Details

The core module, `cnn_conv4`, orchestrates the arithmetic operations required for feature extraction.

### Data Flow
1.  **Input:** Receives an array of 32 input samples (`sample_adjusted`) and 32 filter weights (`filter`).
2.  **Multiplication:** Uses 32 instances of `multiplierfsm_v2` to perform parallel floating-point multiplication.
3.  **Accumulation:** A sequential Finite State Machine (FSM) accumulates the results using `addsubfsm_v6`.
4.  **Bias & Activation:** Adds the layer bias and applies the ReLU function (`max(0, x)`).
5.  **Output:** Generates a final 27-bit floating-point feature.

### Custom FPU (Floating Point Unit)
Instead of standard IEEE 754 (32-bit), this project uses a custom **27-bit format** defined in `fpupack.vhd` to optimize FPGA/ASIC resources:
* **Sign:** 1 bit
* **Exponent:** 8 bits (Bias 127)
* **Mantissa:** 18 bits
* *Why?* Reduced silicon area while maintaining sufficient precision for Neural Network inference.

---

## ⚙️ ASIC Design Flow (RTL-to-GDSII)

This project simulates the real-world chip design process used in the semiconductor industry.

### 1. Frontend Design & Verification
* **RTL Coding:** VHDL 93/2008.
* **Verification:**
    * **Golden Model:** A C/C++ model was created to generate reference outputs.
    * **Testbench:** `cnn_conv4_tb.vhd` validates bit-true accuracy against the Golden Model.
    * **Simulator:** Cadence Xcelium / SimVision.

### 2. Logic Synthesis
* **Tool:** Cadence Genus.
* **Target:** 45nm Standard Cell Library (GPDK045).
* **Constraints:** Timing (Clock period 10ns / 100MHz), Area, and Power optimization.

### 3. Physical Design (Layout)
* **Tool:** Cadence Innovus (Stylus Mode).
* **Steps:**
    1.  **Floorplanning:** Core aspect ratio 1.0, Utilization 70%.
    2.  **Power Planning:** Power rings and stripes (VDD/VSS) for IR Drop mitigation.
    3.  **Placement:** Standard cell placement with congestion analysis.
    4.  **CTS (Clock Tree Synthesis):** Balanced clock distribution.
    5.  **Routing:** NanoRoute for final signal connections (Metal 1 to Metal 10).
    6.  **Sign-off:** DRC (Design Rule Check) and LVS (Layout vs Schematic).

---

## 📸 Visual Results

### 1. Physical Layout (Innovus)
*The final routed chip layout in 45nm technology.*
![Chip Layout](path/to/your/layout_image.png)
*(Replace this path with your actual image file)*

### 2. Functional Verification (Waveform)
*SimVision waveform showing the MAC operation and valid `ready_soma` signal.*
![Waveform](path/to/your/waveform_image.png)

### 3. Golden Model Validation
*Terminal output comparing VHDL hardware results vs. C software model.*
![Terminal](path/to/your/terminal_image.png)

---

## 📂 Repository Structure

```text
├── rtl/                   # VHDL Source Codes
│   ├── cnn_conv4.vhd      # Top Module
│   ├── fpupack.vhd        # Custom Floating Point Package
│   ├── multiplierfsm_v2.vhd
│   └── addsubfsm_v6.vhd
├── verification/          # Testbenches and C Models
│   ├── cnn_conv4_tb.vhd
│   └── golden_model.c
├── backend/               # Synthesis & Layout
│   ├── synthesis/         # Genus Scripts & Reports
│   └── layout/            # Innovus Scripts & GDSII
└── scripts/               # Automation Tcl Scripts
