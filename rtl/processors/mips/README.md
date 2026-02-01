# MIPS Processor Architectures
Implementation of MIPS32 ISA in three different microarchitectures, demonstrating the evolution of processor design.

## Versions
1. **Single Cycle:** Executes one instruction per clock cycle (long critical path).
2. **Multi Cycle:** Breaks instruction execution into smaller steps (higher clock frequency).
3. **Pipeline:** Parallel execution of instructions (5 stages: IF, ID, EX, MEM, WB) with hazard detection and forwarding unit.

