[DLCD Index](../README.md)

# Unit 4: Microarchitecture - Single-Cycle, Multi-Cycle, and Pipelined Processors

Welcome to Unit 4 of **Digital Logic and Computer Design** (`UE25CS251A`), structured directly around the PES University syllabus and David Money Harris & Sarah L. Harris (*Digital Design and Computer Architecture*, 2nd Edition, Morgan Kaufmann / Elsevier).

In Unit 3, we studied the MIPS Instruction Set Architecture (ISA)—the programmer's view of the machine. Now, in this culminating unit of the course, we step behind the curtain into **Microarchitecture**: the actual hardware design that brings the ISA to life in silicon.

We construct three complete processor microarchitectures for a representative subset of MIPS instructions (`add`, `sub`, `and`, `or`, `slt`, `lw`, `sw`, `beq`, and `j`):
1. **The Single-Cycle Processor**: Executes an entire instruction in one long clock cycle. Simple to understand, but speed is penalized by the slowest instruction.
2. **The Multi-Cycle Processor**: Breaks instructions into multiple shorter clock cycles, reusing a single shared ALU and memory array through finite state machine control.
3. **The Pipelined Processor**: Overlaps the execution of five instructions simultaneously across dedicated pipeline stages, achieving an ideal throughput of one instruction per clock cycle while resolving structural, data, and control hazards.

---

## Unit 4 Roadmap

- [**L01 - Microarchitecture Fundamentals and Performance Analysis**](L01%20-%20Microarchitecture%20Fundamentals%20and%20Performance%20Analysis.md) — Architectural state vs. microarchitecture, datapath and control decomposition, the classic execution time formula ($\text{Time} = I \times \text{CPI} \times T_c$), and the MIPS architectural instruction subset.
- [**L02 - Single-Cycle MIPS Datapath Design**](L02%20-%20Single-Cycle%20MIPS%20Datapath%20Design.md) — Assembling the single-cycle hardware datapath incrementally: instruction fetch, register operand read, immediate sign-extension, ALU execution, memory access, branch target calculation, and jump logic into a unified circuit.
- [**L03 - Single-Cycle MIPS Control Unit Design**](L03%20-%20Single-Cycle%20MIPS%20Control%20Unit%20Design.md) — Synthesizing the brain of the single-cycle CPU: Main Decoder, ALU Decoder, control signal truth tables, and critical-path delay analysis ($T_c$).
- [**L04 - Multi-Cycle MIPS Datapath Design**](L04%20-%20Multi-Cycle%20MIPS%20Datapath%20Design.md) — Overcoming single-cycle limitations: hardware reuse, single unified memory array, single shared ALU, non-architectural internal registers (`IR`, `MDR`, `A`, `B`, `ALUOut`), and multiplexer steering.
- [**L05 - Multi-Cycle MIPS Control Unit and State Machine**](L05%20-%20Multi-Cycle%20MIPS%20Control%20Unit%20and%20State%20Machine.md) — The multi-cycle control Finite State Machine: Fetch, Decode, Execute, Memory Access, and Writeback states, instruction CPI analysis, and performance trade-offs.
- [**L06 - Pipelined MIPS Processor Architecture and Hazards**](L06%20-%20Pipelined%20MIPS%20Processor%20Architecture%20and%20Hazards.md) — The 5-stage RISC pipeline (IF, ID, EX, MEM, WB), pipeline registers, control propagation, and comprehensive hazard resolution: structural hazards, RAW data forwarding and load stalls, and branch control hazard flushing.

---

## Objectives

- Calculate CPU execution time using the three fundamental performance variables ($I$, $\text{CPI}$, $T_c$).
- Trace dataflow paths through the Single-Cycle MIPS datapath for R-type, memory, branch, and jump instructions.
- Design Main Decoder and ALU Decoder combinational logic tables to control processor multiplexers and write-enable lines.
- Synthesize the Finite State Machine controlling a Multi-Cycle MIPS processor.
- Trace instruction progression through the 5 pipeline stages of a pipelined processor.
- Resolve data hazards using forwarding and stalling, and control hazards using early branch evaluation and pipeline flushes.

---

Let's begin by examining microarchitectural performance analysis. Read [**L01 - Microarchitecture Fundamentals and Performance Analysis**](L01%20-%20Microarchitecture%20Fundamentals%20and%20Performance%20Analysis.md).
