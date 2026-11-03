[DLCD Index](../README.md)

# Unit 3: Architecture, Memory, and MIPS Assembly

Welcome to Unit 3 of **Digital Logic and Computer Design** (`UE25CS251A`), structured directly around the PES University syllabus and David Money Harris & Sarah L. Harris (*Digital Design and Computer Architecture*, 2nd Edition, Morgan Kaufmann / Elsevier).

In Units 1 and 2, we built the hardware foundation: logic gates, latches, flip-flops, Finite State Machines, and arithmetic ALUs. Now, in Unit 3, we cross the grand boundary of computer engineering: **the Instruction Set Architecture (ISA)**. The ISA represents the ultimate contract between software and hardware—it defines the programmer's view of the machine, the register file, the instruction encoding formats, and the memory organization.

We begin by examining the sequential hardware components that bridge datapaths and storage: multi-bit counters, shift registers, and semiconductor memory arrays (SRAM, DRAM, and ROM). We then dive into the **MIPS architecture**, exploring its four foundational design principles, its instruction formats (R-type, I-type, J-type), its assembly language programming idioms, addressing modes, and the fundamental limits of parallel performance governed by Amdahl's Law.

---

## Unit 3 Roadmap

- [**L01 - Sequential Building Blocks - Counters and Shift Registers**](L01%20-%20Sequential%20Building%20Blocks%20-%20Counters%20and%20Shift%20Registers.md) — Multi-bit binary counters, asynchronous (ripple) vs. synchronous counters, Modulo-N and decade counters, shift register topologies (SISO, SIPO, PISO, PIPO), universal shift registers, and scan chains for chip testability (DFT).
- [**L02 - Memory Arrays - SRAM, DRAM, and ROM**](L02%20-%20Memory%20Arrays%20-%20SRAM%2C%20DRAM%2C%20and%20ROM.md) — Two-dimensional memory array architecture ($2^k \times m$), wordlines, bitlines, 6T SRAM cells, 1T-1C DRAM cells with charge refresh cycles, ROM variants (Mask ROM, PROM, EPROM, Flash), and multi-ported register files.
- [**L03 - Computer Architecture Principles and MIPS Overview**](L03%20-%20Computer%20Architecture%20Principles%20and%20MIPS%20Overview.md) — Computer architecture vs. microarchitecture, Von Neumann vs. Harvard architectures, the four foundational RISC design principles, and an architectural overview of the 32-bit MIPS processor.
- [**L04 - MIPS Assembly Language - Instructions and Operands**](L04%20-%20MIPS%20Assembly%20Language%20-%20Instructions%20and%20Operands.md) — MIPS assembly syntax, arithmetic operations (`add`, `sub`, `addi`), the 32 general-purpose registers and their software conventions, memory access (`lw`, `sw`), byte addressing, and word alignment.
- [**L05 - MIPS Machine Language and Instruction Formats**](L05%20-%20MIPS%20Machine%20Language%20and%20Instruction%20Formats.md) — Converting human-readable assembly into 32-bit binary machine code: R-Type, I-Type, and J-Type formats, field encoding breakdown, sign-extension vs. zero-extension, and decoding strategies.
- [**L06 - MIPS Programming - Conditionals, Loops, and Logical Instructions**](L06%20-%20MIPS%20Programming%20-%20Conditionals%2C%20Loops%2C%20and%20Logical%20Instructions.md) — Translating high-level programming idioms: bitwise logic (`and`, `or`, `nor`), barrel shifts (`sll`, `srl`, `sra`), conditional branching (`beq`, `bne`), comparisons (`slt`, `slti`), and compiling `if-else` and `while` loops.
- [**L07 - MIPS Addressing Modes**](L07%20-%20MIPS%20Addressing%20Modes.md) — The five MIPS addressing modes: Register, Immediate, Base (Displacement), PC-Relative (branch target calculation), and Pseudo-Direct (jump target calculation).
- [**L08 - Parallelism and Performance Limits**](L08%20-%20Parallelism%20and%20Performance%20Limits.md) — Modern performance scaling: Instruction-Level Parallelism (ILP), Data-Level Parallelism (SIMD), Thread-Level Parallelism (multicore), and the mathematical derivation and implications of Amdahl's Law.
- [**L09 - Architecture and Assembly Practice Problems**](L09%20-%20Architecture%20and%20Assembly%20Practice%20Problems.md) — Step-by-step walkthroughs of representative exam problems: counter synthesis, machine code encoding/decoding, pointer and array translation, branch target offset calculations, and Amdahl's law evaluation.

---

## Objectives

- Design synchronous and asynchronous multi-bit counters and universal shift registers.
- Contrast the transistor-level operation, speed, and density trade-offs of SRAM versus DRAM cells.
- Apply the four design principles of computer architecture to evaluate instruction set trade-offs.
- Write and assemble MIPS programs using arithmetic, memory, logical, branch, and jump instructions.
- Encode and decode MIPS instructions into R-type, I-type, and J-type machine language formats.
- Calculate effective branch and jump target addresses using PC-relative and pseudo-direct addressing modes.
- Apply Amdahl's Law to calculate overall speedup and determine the point of diminishing returns in processor optimization.

---

Let's begin by examining sequential building blocks. Read [**L01 - Sequential Building Blocks - Counters and Shift Registers**](L01%20-%20Sequential%20Building%20Blocks%20-%20Counters%20and%20Shift%20Registers.md).
