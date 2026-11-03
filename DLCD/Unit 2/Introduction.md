[DLCD Index](../README.md)

# Unit 2: Digital Building Blocks and Finite State Machines

Welcome to Unit 2 of **Digital Logic and Computer Design** (`UE25CS251A`), structured directly around the PES University syllabus and David Money Harris & Sarah L. Harris (*Digital Design and Computer Architecture*, 2nd Edition, Morgan Kaufmann / Elsevier).

In Unit 1, we learned how to minimize Boolean logic and build edge-triggered flip-flops to hold individual bits. Now in Unit 2, we ascend to higher levels of abstraction. We combine combinational logic and clocked registers to construct the two most critical subsystems of any computer:
1. **Control Units**: Governed by **Finite State Machines (FSMs)** that step through algorithmic operational states and orchestrate datapath actions.
2. **Datapaths**: Governed by high-speed **Arithmetic Circuits** (adders, subtractors, comparators, multipliers, and Arithmetic Logic Units) and standardized **Number Representations** (2's complement integers, fixed-point fractions, and IEEE 754 floating-point standards).

---

## Unit 2 Roadmap

- [**L01 - Finite State Machines - Mealy and Moore Models**](L01%20-%20Finite%20State%20Machines%20-%20Mealy%20and%20Moore%20Models.md) — The formal structure of synchronous Finite State Machines: state registers, next-state logic, and output logic. Moore vs. Mealy machine architectures, state transition diagrams, state tables, state encoding strategies (binary vs. one-hot), and comprehensive case studies: Ben Bitdiddle's campus traffic light controller, the divide-by-3 counter, and sequence detectors.
- [**L02 - Arithmetic Circuits**](L02%20-%20Arithmetic%20Circuits.md) — The mathematical engine of the CPU: Half Adders, Full Adders, Ripple Carry Adders (RCA), Carry-Lookahead Adders (CLA) with generate and propagate logic, prefix adders, 2's complement adder-subtractors, magnitude comparators, shifter architectures (logical, arithmetic, barrel), 4x4 array multipliers, and multi-function Arithmetic Logic Units (ALUs) with Set-Less-Than (SLT) comparison.
- [**L03 - Number Systems and Floating-Point Representation**](L03%20-%20Number%20Systems%20and%20Floating-Point%20Representation.md) — How digital circuits represent real-world mathematics: unsigned binary, 2's complement signed integers, fixed-point fractional notation, the IEEE 754 Floating-Point Standard (Single-Precision 32-bit and Double-Precision 64-bit), biased exponents, implicit leading 1s, special numerical encodings ($\pm 0, \pm \infty, \text{NaN}$, denormals), rounding modes, and step-by-step floating-point addition tracing.

---

## Objectives

- Design, analyze, and synthesize synchronous Finite State Machines using both Moore and Mealy models.
- Formulate state transition diagrams and derive next-state and output Boolean equations using binary and one-hot state encodings.
- Evaluate the critical-path propagation delays of Ripple Carry Adders versus Carry-Lookahead Adders.
- Synthesize an integrated multi-function ALU capable of addition, subtraction, bitwise logic, and conditional comparison (`SLT`).
- Encode signed real numbers into fixed-point and IEEE 754 single-precision floating-point formats.
- Trace step-by-step floating-point addition, including exponent alignment, mantissa addition, normalization, and rounding.

---

Let's begin by examining how digital systems make stateful decisions. Read [**L01 - Finite State Machines - Mealy and Moore Models**](L01%20-%20Finite%20State%20Machines%20-%20Mealy%20and%20Moore%20Models.md).
