# Advanced Digital Logic & System-on-Chip Portfolio

This repository is a comprehensive collection of my engineering projects, covering the entire flow from **Mathematical System Modeling** to **ASIC/FPGA Physical Implementation**. It showcases my expertise in Digital Design, Functional Verification, and Hardware-Software Co-design.

---

## 🚀 Key Project: ECG SoC Accelerator (TCC2)
An end-to-end SoC integration project developed during the CI Digital program.
* **Core:** NEORV32 (RISC-V ISA).
* **IP Core:** Custom ECG Peak Detector for medical signal processing.
* **Interconnect:** AXI4-Lite bus wrapper for memory-mapped IO.
* **Software:** C drivers and Assembly routines for threshold control and status monitoring.
* **Backend:** Full Cadence Genus flow for synthesis and timing analysis.

---

## 🛠 Repository Structure

### 1. System Modeling & Algorithms (`/system_modeling`)
*Before the RTL, comes the math.*
* **Telecommunications:** Python implementation of a **Doppler Effect Compensator** for LoRa LEO satellite communications using software-defined PLLs.
* **Robotics & AI:** Machine Learning and Deep Learning algorithms for autonomous robot navigation and computer vision.

### 2. RTL Design (`/rtl`)
* **Processors:** - **RISC-V:** Analysis of ElectronRV32 and FemtoRV32 cores.
  - **MIPS:** Single-Cycle, Multi-Cycle, and 5-stage Pipeline implementations.
* **AI Accelerators:** Hardware implementations of **CNN layers (Convolutional Neural Networks)** and **RBF Neurons**.
* **DSP & Math:** CORDIC cores (Sin/Cos), Matrix Inversion modules, and LMS Adaptive Filters.
* **Interfaces & Protocols:** Master/Slave implementations of **I2C, SPI, UART** and high-speed **8b/10b SerDes**.
* **Sequential Logic:** FSM-based multipliers, Handshaking protocols, and custom RAM/FIFO blocks.

### 3. Functional Verification (`/verification_projects`)
*Ensuring the design meets the spec.*
* **UVM (Universal Verification Methodology):** Complete environments (Agent, Driver, Monitor, Scoreboard) for ALU and Adder blocks.
* **SystemVerilog:** Constrained random stimulus and functional coverage (Covergroups/Bins).
* **TLM:** Transaction-Level Modeling integration using TLM FIFOs and analysis ports.

### 4. Synthesis & Physical Design (`/synthesis_physical`)
*Bridging the gap between code and silicon.*
* **Tools:** Industry-standard **Cadence Flow** (Genus, Innovus, Modus).
* **Static Timing Analysis (STA):** Detailed reports on Setup/Hold slack, Critical Path, and Slew/Capacitance calculations.
* **DFT & ATPG:** Insertion of Scan Chains and generation of test patterns for Stuck-at fault coverage.

---

## 🎓 Background
- **Electronic Engineering Student:** University of Brasília (UnB).
- **CI Digital / CI Expert:** Advanced training in Microelectronics and Functional Verification.
- **Interests:** Microelectronics, Functional Verification (UVM), Space Telecom, and AI Hardware Acceleration.

---

## 📬 Contact
- **LinkedIn:** www.linkedin.com/in/vinícius-l-282937151
- **Email:** viniedulopes@icloud.com

---
*“From Algorithm to Silicon.”*