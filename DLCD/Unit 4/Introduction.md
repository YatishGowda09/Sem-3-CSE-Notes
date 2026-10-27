[DLCD Index](../README.md)

# Unit 4: Computer Arithmetic and Processing Unit / Control Unit Design

Welcome to Unit 4 of **Digital Logic and Computer Design**.

In Units 1, 2, and 3, we built up from individual transistors and Boolean logic gates, through synchronous sequential flip-flops and registers, to the system-level architecture of memories, buses, and assembly instructions.

Unit 4 is the computational and control climax of the entire subject. Here, we step directly inside the Central Processing Unit to answer the two ultimate engineering questions:
1. **How does the ALU compute complex arithmetic at wire speed?** 
   How do circuits multiply signed integers using Booth's recoding, compress partial products with Wallace Trees, execute restoring and non-restoring integer division, and handle fractional scientific numbers under the IEEE 754 Floating-Point standard?
2. **How does the Control Unit orchestrate the processor data path?**
   How do internal processor buses move data between registers and the ALU, what microscopic control steps execute an instruction like `Add (R3), R1`, and how do we physically synthesize the control unit—using high-speed **Hardwired combinational logic** or flexible **Microprogrammed ROM firmware**?

---

## Unit 4 Roadmap

The lectures in this unit build systematically from high-speed arithmetic data paths to complete control unit synthesis:

- [**L01 - Multiplication of Positive Numbers**](L01%20-%20Multiplication%20of%20Positive%20Numbers.md) — Array multipliers vs. sequential shift-and-add data paths, hardware register organization (Multiplier $Q$, Multiplicand $M$, Accumulator $A$, Down-counter $C$), and clock-cycle-by-cycle multiplication traces.
- [**L02 - Signed Multiplication and Booth's Algorithm**](L02%20-%20Signed%20Multiplication%20and%20Booth's%20Algorithm.md) — Signed 2's complement multiplication, the string-of-ones mathematical theorem, Booth's recoding table, step-by-step register traces, and Radix-4 bit-pair recoding for 50% faster multiplication.
- [**L03 - Fast Multiplication and Carry-Save Addition**](L03%20-%20Fast%20Multiplication%20and%20Carry-Save%20Addition.md) — Overcoming carry propagation latency in multi-operand addition, Carry-Save Adder (CSA) blocks without horizontal ripple, the Wallace Tree multiplier structure, and final carry-propagate summation.
- [**L04 - Integer Division**](L04%20-%20Integer%20Division.md) — Binary longhand division data path, Restoring Division algorithm with register traces ($A, Q, M$), Non-Restoring Division algorithm, and elimination of restoration cycles.
- [**L05 - Floating-Point Numbers and IEEE 754 Standard**](L05%20-%20Floating-Point%20Numbers%20and%20IEEE%20754%20Standard.md) — Scientific notation in binary, IEEE 754 Single (32-bit) and Double (64-bit) precision formats: Sign bit, Biased Exponent (Excess-127 / Excess-1023), Mantissa with hidden leading 1; Special values (Zero, Normalized, Denormalized, $\pm \infty$, NaN); Floating-point addition and multiplication algorithms.
- [**L06 - Fundamental Processing Concepts**](L06%20-%20Fundamental%20Processing%20Concepts.md) — Internal processor organization, single-bus CPU architecture, register gating signals ($R_{\text{in}}, R_{\text{out}}$), temporary registers $Y$ and $Z$, ALU operations, and memory read/write interfacing via MAR and MDR.
- [**L07 - Execution of a Complete Instruction**](L07%20-%20Execution%20of%20a%20Complete%20Instruction.md) — Clock-cycle control step traces: step-by-step register transfer choreographies for ALU instructions (`Add (R3), R1`), memory loads (`Move (R1), R2`), and conditional branches (`Branch_if_zero LOC`), along with control signal activation tables.
- [**L08 - Multiple-Bus Organization**](L08%20-%20Multiple-Bus%20Organization.md) — Single-bus bottlenecks, Three-Bus CPU architecture (Bus A, Bus B, Bus C), executing two-operand ALU operations in a single clock cycle, and performance comparison.
- [**L09 - Hardwired Control Unit Design**](L09%20-%20Hardwired%20Control%20Unit%20Design.md) — Hardwired control unit architecture: step counter, instruction decoder, encoder combinational logic matrix, deriving Boolean equations for control signals, and evaluating high-speed performance vs. inflexibility.
- [**L10 - Microprogrammed Control Unit Design**](L10%20-%20Microprogrammed%20Control%20Unit%20Design.md) — Microprogrammed control concept (Maurice Wilkes): Control Store ROM, microinstructions, micro-operations, microprogram counter ($\mu\text{PC}$), horizontal vs. vertical microinstructions, microprogram sequencing and branching, and architectural trade-offs.

---

## Objectives

- Understand the hardware trade-offs between combinational array multipliers and sequential shift-and-add data paths.
- Execute Booth's algorithm and Bit-Pair (Radix-4) recoding for signed 2's complement multiplication.
- Analyze Carry-Save Addition (CSA) and construct Wallace Tree reduction networks for ultra-fast multiplication.
- Trace Restoring and Non-Restoring integer division algorithms on hardware registers.
- Master the IEEE 754 Floating-Point representation, bias calculations, normalization, and arithmetic execution.
- Trace microscopic register transfers across single-bus and multi-bus processor data paths.
- Write clock-cycle control sequences for ALU operations, memory transfers, and conditional branch instructions.
- Design Hardwired Control Units using state counters and combinational logic expressions.
- Construct Microprogrammed Control Units using Control Store ROMs, microinstruction formats, and microprogram sequencing.

---

Let's begin by exploring how arithmetic units multiply positive numbers using shift-and-add hardware. Read [**L01 - Multiplication of Positive Numbers**](L01%20-%20Multiplication%20of%20Positive%20Numbers.md).
