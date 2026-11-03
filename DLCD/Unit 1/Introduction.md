[DLCD Index](../README.md)

# Unit 1: Combinational and Sequential Logic Design

Welcome to Unit 1 of **Digital Logic and Computer Design** (`UE25CS251A`), structured directly around the course syllabus from PES University and foundational principles from David Money Harris and Sarah L. Harris (*Digital Design and Computer Architecture*, 2nd Edition, Morgan Kaufmann / Elsevier).

In this opening unit, we establish the fundamental abstraction that makes modern digital computing possible: **the digital abstraction**. We learn how continuous, analog voltages are disciplined into discrete binary zeros and ones, how Boolean algebra allows us to express logical specifications as mathematical formulas, how Karnaugh maps minimize silicon area, and how higher-level combinational building blocks like multiplexers and decoders route data.

We then cross the threshold from memoryless combinational logic into **sequential logic**. We examine how cross-coupled feedback gives birth to bistable storage elements (latches and flip-flops) and analyze the iron rules of synchronous digital design that keep clock-driven microprocessors running reliably at gigahertz frequencies.

---

## Unit 1 Roadmap

- [**L01 - Introduction and Digital Abstraction**](L01%20-%20Introduction%20and%20Digital%20Abstraction.md) — The digital abstraction, analog vs. digital signals, digital circuits as black boxes with functional and timing specifications, inputs, outputs, internal nodes, combinational vs. sequential logic, and the rules of combinational composition.
- [**L02 - Boolean Equations and Logic Gates**](L02%20-%20Boolean%20Equations%20and%20Logic%20Gates.md) — Boolean equations, literals, minterms, maxterms, Sum-of-Products (SOP), Product-of-Sums (POS), Boolean algebra axioms and theorems (identity, null, complement, idempotence, involution, commutativity, associativity, distributivity, DeMorgan's laws), and logic gate synthesis.
- [**L03 - Karnaugh Map Minimization**](L03%20-%20Karnaugh%20Map%20Minimization.md) — Systematic visual logic minimization using 2-, 3-, and 4-variable K-maps, Gray code adjacency, grouping rules, prime implicants, essential prime implicants, Don't Care conditions ($X$), and Product-of-Sums (POS) minimization.
- [**L04 - Combinational Building Blocks - Multiplexers and Decoders**](L04%20-%20Combinational%20Building%20Blocks%20-%20Multiplexers%20and%20Decoders.md) — Modular combinational building blocks: 2:1 and 4:1 multiplexers (data selectors), implementing arbitrary logic using multiplexers as lookup tables, $n$-to-$2^n$ line decoders, priority encoders, and tri-state buffers with high-impedance (Hi-Z) states.
- [**L05 - Storage Elements - Latches and Flip-Flops**](L05%20-%20Storage%20Elements%20-%20Latches%20and%20Flip-Flops.md) — Introducing feedback into logic circuits: bistable cross-coupled inverters, SR latches (NOR and NAND implementations), Gated D latches and the transparency race hazard, edge-triggered D flip-flops (Master-Slave architecture), enabled flip-flops, and resettable flip-flops (synchronous vs. asynchronous).
- [**L06 - Synchronous Logic Design and Timing**](L06%20-%20Synchronous%20Logic%20Design%20and%20Timing.md) — The rules of synchronous sequential circuit composition, eliminating cyclic race hazards, clock distribution, dynamic timing parameters (setup time $t_{\text{setup}}$, hold time $t_{\text{hold}}$, propagation delay $t_{\text{pcq}}$, contamination delay $t_{\text{ccq}}$), clock skew, and calculating the maximum clock frequency of digital systems.

---

## Objectives

- Understand the digital abstraction and distinguish between functional and timing specifications of digital circuits.
- Formulate Boolean equations from truth tables and problem statements using SOP and POS canonical forms.
- Minimize Boolean logic expressions using Boolean algebraic theorems and Karnaugh maps with Don't Care conditions.
- Design combinational subsystems using multiplexers, decoders, priority encoders, and tri-state buses.
- Trace the internal circuit mechanics of SR latches, D latches, and edge-triggered D flip-flops.
- Apply the rules of synchronous sequential composition and solve setup-time and hold-time timing constraints to calculate maximum operating frequencies.

---

Let's begin by examining how the digital abstraction disciplines continuous physics into discrete computation. Read [**L01 - Introduction and Digital Abstraction**](L01%20-%20Introduction%20and%20Digital%20Abstraction.md).
