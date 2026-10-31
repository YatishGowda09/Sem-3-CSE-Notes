[DLCD Index](../README.md)

# Unit 4: Computer Arithmetic and Processing Unit / Control Unit Design

Welcome to Unit 4 of **Digital Logic and Computer Design**.

In Units 1, 2, and 3, we built up from individual transistors and Boolean logic gates, through synchronous sequential flip-flops and registers, to the system-level architecture of memories, buses, and assembly instructions.

Unit 4 is the computational and control climax of the entire subject. Here, we step directly inside the Central Processing Unit to answer the two ultimate engineering questions:
1. **How does the ALU compute complex arithmetic at wire speed?** 
   How do combinational array multipliers multiply unsigned integers, how do sequential circuits multiply signed numbers using Booth's algorithm, how do Wallace Trees compress partial products with Carry-Save Addition, how do Restoring and Non-Restoring dividers calculate quotients, and how does the IEEE 754 Floating-Point standard represent fractional scientific numbers?
2. **How does the Control Unit orchestrate the processor data path?**
   How do internal processor buses move data between registers and the ALU, what microscopic control steps execute an instruction like `Add (R3), R1`, how does multiple-bus organization enable single-cycle ALU execution, and how do we physically synthesize the control unit—using high-speed **Hardwired combinational logic** or flexible **Microprogrammed ROM firmware**?

---

## Unit 4 Roadmap

The lectures in this unit build systematically from high-speed arithmetic data paths to complete control unit synthesis:

- [**L01 - Unsigned Multiplication and Array Multipliers**](L01%20-%20Unsigned%20Multiplication%20and%20Array%20Multipliers.md) — Combinational array multipliers, generating partial products with AND gates, summing with Full Adders, component scaling ($n^2$ AND gates, $n(n-1)$ Full Adders), and deriving the worst-case propagation delay formula ($6(n-1)-1$).
- [**L02 - Sequential Multiplication, Booth's Algorithm, and Fast Multiplication**](L02%20-%20Sequential%20Multiplication,%20Booth's%20Algorithm,%20and%20Fast%20Multiplication.md) — Sequential shift-and-add data paths reusing a single adder, Booth's algorithm for signed 2's complement multiplication via runs of ones, Radix-4 bit-pair recoding to halve summands ($n \to n/2$), and Carry-Save Addition (CSA 3:2 compressors) arranged in Wallace Trees for logarithmic addition time.
- [**L03 - Integer Division - Restoring and Non-Restoring Algorithms**](L03%20-%20Integer%20Division%20-%20Restoring%20and%20Non-Restoring%20Algorithms.md) — Binary longhand division data path ($A, Q, M$), Restoring Division with trial subtractions and restoration additions, Non-Restoring Division eliminating restoration cycles via conditional shift-and-add, and final remainder correction.
- [**L04 - Floating-Point Numbers and IEEE 754 Standard**](L04%20-%20Floating-Point%20Numbers%20and%20IEEE%20754%20Standard.md) — Fixed-point limitations, IEEE 754 Single (32-bit) and Double (64-bit) precision formats: Sign bit, Biased Exponent (Excess-127 / Excess-1023), Mantissa with hidden leading 1, special values (Zero, Denormals, $\pm \infty$, NaN), and floating-point arithmetic rules.
- [**L05 - Fundamental Processing Concepts and Single-Bus Datapath**](L05%20-%20Fundamental%20Processing%20Concepts%20and%20Single-Bus%20Datapath.md) — Internal processor organization, single-bus CPU architecture, register gating signals ($R_{\text{in}}, R_{\text{out}}$), why temporary registers $Y$ and $Z$ are mandatory, ALU operations, and memory read/write handshakes via MAR, MDR, and WMFC.
- [**L06 - Execution of a Complete Instruction and Branching**](L06%20-%20Execution%20of%20a%20Complete%20Instruction%20and%20Branching.md) — The universal instruction fetch phase ($T_1 - T_3$), clock-cycle control sequences for ALU operations (`Add (R3), R1`), memory loads (`Move (R1), R2`), and conditional branching (`Branch_if_zero`), and constructing the master Control Signal Activation Table.
- [**L07 - Multiple-Bus Organization and Control Unit Design**](L07%20-%20Multiple-Bus%20Organization%20and%20Control%20Unit%20Design.md) — Three-Bus CPU architecture (Buses A, B, C) and multi-port register files enabling single-cycle ALU execution, complete processor structure, Hardwired Control synthesis using step counters and combinational logic matrices, and Microprogrammed Control (Maurice Wilkes) using Control Store ROMs, $\mu\text{PC}$, and horizontal vs. vertical microinstructions.

---

## Objectives

- Understand the hardware trade-offs between combinational array multipliers and sequential shift-and-add data paths.
- Execute Booth's algorithm and Bit-Pair (Radix-4) recoding for signed 2's complement multiplication.
- Analyze Carry-Save Addition (CSA) and construct Wallace Tree reduction networks for ultra-fast multiplication.
- Trace Restoring and Non-Restoring integer division algorithms on hardware registers.
- Master the IEEE 754 Floating-Point representation, bias calculations, normalization, and arithmetic execution.
- Trace microscopic register transfers across single-bus and multi-bus processor data paths.
- Write clock-cycle control sequences for ALU operations, memory transfers, and conditional branch instructions.
- Design Hardwired Control Units using step counters, instruction decoders, and combinational logic expressions.
- Construct Microprogrammed Control Units using Control Store ROMs, microinstruction formats, and microprogram sequencing.

---

Let's begin by exploring how combinational arrays multiply binary numbers in hardware. Read [**L01 - Unsigned Multiplication and Array Multipliers**](L01%20-%20Unsigned%20Multiplication%20and%20Array%20Multipliers.md).
