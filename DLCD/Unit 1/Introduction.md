# Unit 1: Gate-Level Minimization and Combinational Logic Design

Welcome to Unit 1 of **Digital Logic and Computer Design**.

At the most fundamental physical level, computers are built from billions of microscopic silicon transistors acting as electronic switches. When electrical charge flows, a transistor conducts; when charge is absent, it insulates. Everything in modern computing—from rendering a 3D video game to training a billion-parameter neural network—is built upon the mathematical abstraction of **Boolean logic** running across these physical switches.

Unit 1 explores the foundational principles of digital logic design:
- How continuous electrical voltages are abstracted into discrete binary states (`0` and `1`).
- The mathematical foundations of **Boolean Algebra** and the laws governing logic simplification.
- How logic functions are expressed in **Canonical SOP and POS forms**.
- Systematic gate-level minimization using **Karnaugh Maps (K-Maps)** with Don't Care conditions.
- Universal gate synthesis using **NAND and NOR** logic.
- The step-by-step design of **Combinational Logic Circuits** where outputs depend strictly on current inputs.
- Essential arithmetic and MSI (Medium Scale Integration) building blocks: **Binary Adders/Subtractors**, **BCD Decimal Adders**, **Multipliers**, **Magnitude Comparators**, **Decoders**, **Priority Encoders**, and **Multiplexers (MUX)**.

---

## Unit 1 Roadmap

The lectures in this unit trace the progression from algebraic theorems to complex MSI combinational circuits:

- [**L01 - Introduction and Boolean Algebra**](L01%20-%20Introduction%20and%20Boolean%20Algebra.md) — Analog vs. digital systems, binary logic levels, basic gates (AND, OR, NOT), Huntington's postulates, Boolean theorems (DeMorgan's laws, Absorption, Consensus), and algebraic simplification.
- [**L02 - Canonical and Standard Forms**](L02%20-%20Canonical%20and%20Standard%20Forms.md) — Minterms ($m_i$) and Maxterms ($M_i$), Sum of Minterms (SOP), Product of Maxterms (POS), conversion between canonical forms, and standard vs. non-standard Boolean expressions.
- [**L03 - Karnaugh Map Minimization**](L03%20-%20Karnaugh%20Map%20Minimization.md) — The map method, Gray code adjacency, 2-, 3-, and 4-variable K-maps, Prime Implicants (PI) and Essential Prime Implicants (EPI), POS minimization, and Don't Care conditions ($d$).
- [**L04 - Logic Gate Implementation with Universal Gates**](L04%20-%20Logic%20Gate%20Implementation%20with%20Universal%20Gates.md) — Universal gates: NAND and NOR; multi-level NAND-NAND and NOR-NOR synthesis using bubble logic; AOI/OAI forms; and Exclusive-OR (XOR) / Exclusive-NOR (XNOR) parity circuits.
- [**L05 - Combinational Logic Analysis and Design Procedures**](L05%20-%20Combinational%20Logic%20Analysis%20and%20Design%20Procedures.md) — Definition of combinational circuits (feedback-free), analysis procedure from schematic to truth table, design procedure from specification to gates, and code converters (BCD to Excess-3, Binary to Gray).
- [**L06 - Binary Adders and Subtractors**](L06%20-%20Binary%20Adders%20and%20Subtractors.md) — Half Adder, Full Adder synthesis, 4-bit Ripple Carry Adder (RCA), carry propagation delays, Half/Full Subtractors, 4-bit 2's complement Adder-Subtractor circuit, and overflow detection.
- [**L07 - Decimal and BCD Adders**](L07%20-%20Decimal%20and%20BCD%20Adders.md) — Binary Coded Decimal (BCD 8421), invalid BCD states, BCD sum detection logic ($K + Z_3 Z_2 + Z_3 Z_1$), the $+6$ ($0110_2$) correction factor, and two-stage BCD adder hardware.
- [**L08 - Binary Multipliers and Magnitude Comparators**](L08%20-%20Binary%20Multipliers%20and%20Magnitude%20Comparators.md) — Binary multiplication data paths, 2-bit and 4-bit array multipliers, 1-bit comparator logic, and 4-bit Magnitude Comparator cascading using XNOR equality bits.
- [**L09 - Decoders and Circuit Implementation**](L09%20-%20Decoders%20and%20Circuit%20Implementation.md) — Decoder definition, 2-to-4 and 3-to-8 line decoders with enable inputs, decoder tree expansion, and implementing arbitrary combinational Boolean logic using decoders and OR/NAND gates.
- [**L10 - Encoders and Priority Encoders**](L10%20-%20Encoders%20and%20Priority%20Encoders.md) — Octal-to-binary encoders, limitations of simple encoders, Priority Encoder architecture, 4-input and 8-input priority truth tables with Don't Cares, and Valid ($V$) bit logic.
- [**L11 - Multiplexers and Demultiplexers**](L11%20-%20Multiplexers%20and%20Demultiplexers.md) — Multiplexers (Data Selectors), 2:1, 4:1, and 8:1 MUX internal logic, building higher-order MUXes from lower-order MUXes, implementing arbitrary Boolean functions with $2^{n-1}:1$ MUXes, and Demultiplexers.

---

## Objectives

- Understand the binary abstraction and the physical representation of digital logic in electrical circuits.
- Apply the postulates and theorems of Boolean algebra to simplify algebraic logic functions.
- Formulate Boolean expressions in canonical Sum of Minterms (SOP) and Product of Maxterms (POS) notations.
- Minimize 2-, 3-, and 4-variable Boolean functions using Karnaugh maps and leverage Don't Care conditions for optimal hardware minimization.
- Implement two-level and multi-level logic circuits exclusively using universal NAND or NOR gates.
- Execute the systematic design procedure: specification $\to$ truth table $\to$ K-map simplification $\to$ circuit diagram.
- Construct arithmetic combinational blocks: Half Adders, Full Adders, Ripple Carry Adders, 2's complement Adder-Subtractors, and BCD Adders.
- Design data routing and decoding logic using Decoders, Priority Encoders, Multiplexers, and Demultiplexers.
