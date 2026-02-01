# ECG Peak Detector SoC Accelerator (NEORV32 + AXI4-Lite)

## Project Overview (TCC2)
This project integrates a hardware-based ECG Peak Detector into a RISC-V SoC (NEORV32) using the AXI4-Lite bus protocol. It demonstrates a full hardware-software co-design flow.

## System Architecture
* **Processor:** NEORV32 (RISC-V).
* **Bus:** AXI4-Lite (Memory Mapped IO).
* **Accelerator:** Custom ECG Peak Detector IP.
* **SW Control:** C/Assembly software to configure thresholds and read detection status via MMIO.

## Workflow & Tools
1. **Design:** SystemVerilog/VHDL.
2. **Integration:** AXI4-Lite Wrapper implementation.
3. **Verification:** Advanced verification environment for the integrated module.
4. **Physical Implementation:** Full Cadence Flow (Genus/Innovus) for Synthesis and Timing Analysis.

## Legacy (TCC1)
Initial implementation and analysis using open-source tools (OpenLane/OpenROAD).

