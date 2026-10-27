[DLCD Index](../README.md)

# Unit 2: Synchronous Sequential Logic, Registers, and Counters

Welcome to Unit 2 of **Digital Logic and Computer Design**.

In Unit 1, every circuit we designed was strictly **combinational**: its outputs depended entirely and instantaneously on the current values applied to its inputs. Combinational circuits have no memory. They cannot track sequence, retain a previous arithmetic result, or coordinate actions that occur in a specific order over time.

Real computers, however, are fundamentally **state machines**. When an operating system boots, or when a processor steps through the fetch-decode-execute cycle, the hardware must maintain memory of where it is in the execution flow. 

Unit 2 introduces **Sequential Logic**, where circuits incorporate **memory elements** and **feedback paths**. In sequential circuits, the outputs depend not only on the current inputs, but also on the circuit's **present state** (its stored history). We focus primarily on **synchronous** sequential circuits, where all state transitions across the entire machine are coordinated by a periodic master timing signal: the **system clock**.

---

## Unit 2 Roadmap

The lectures in this unit build systematically from cross-coupled physical gates to complex synchronous registers and counting machines:

- [**L01 - Latches and Storage Elements**](L01%20-%20Latches%20and%20Storage%20Elements.md) — The physics of feedback and bistability, SR Latch using NOR and NAND gates, the forbidden state race hazard, Gated SR Latch, Gated D Latch, and the transparency timing problem.
- [**L02 - Flip-Flops and Edge-Triggered Storage**](L02%20-%20Flip-Flops%20and%20Edge-Triggered%20Storage.md) — Edge-triggered storage, Master-Slave flip-flop architecture, Edge-Triggered D, JK, and T flip-flops, characteristic tables, characteristic equations, and flip-flop excitation tables.
- [**L03 - Analysis of Clocked Sequential Circuits**](L03%20-%20Analysis%20of%20Clocked%20Sequential%20Circuits.md) — The systematic analysis procedure: flip-flop input equations, next-state equations, state tables, 2D state transition tables, and state diagrams.
- [**L04 - Mealy and Moore State Machine Models**](L04%20-%20Mealy%20and%20Moore%20State%20Machine%20Models.md) — Classical Finite State Machine (FSM) models: Moore machines (outputs depend only on state) vs. Mealy machines (outputs depend on state and inputs), timing comparisons, clock-to-output latency, and glitch vulnerability.
- [**L05 - State Reduction and State Assignment**](L05%20-%20State%20Reduction%20and%20State%20Assignment.md) — Minimizing sequential hardware: state equivalence theorems, row reduction method, implication tables, and optimal binary state assignment heuristics (binary, Gray, one-hot).
- [**L06 - Sequential Circuit Design Procedure**](L06%20-%20Sequential%20Circuit%20Design%20Procedure.md) — Complete end-to-end sequential synthesis: from English functional specification $\to$ state diagram $\to$ state table $\to$ excitation table $\to$ K-map simplification $\to$ flip-flop schematic.
- [**L07 - Registers and Shift Registers**](L07%20-%20Registers%20and%20Shift%20Registers.md) — Multi-bit data storage: 4-bit parallel register with parallel load control, shift registers (SISO, SIPO, PISO, PIPO), and the Universal Shift Register architecture.
- [**L08 - Ripple Counters**](L08%20-%20Ripple%20Counters.md) — Asynchronous counters: binary ripple up-counters, down-counters, BCD ripple counters, propagation delay accumulation, and dynamic decoding glitches.
- [**L09 - Synchronous Counters**](L09%20-%20Synchronous%20Counters.md) — High-speed parallel counters: 4-bit binary synchronous up-counter with carry-lookahead logic, synchronous up/down counters, and arbitrary non-binary sequence counter design.
- [**L10 - Other Specialized Counters**](L10%20-%20Other%20Specialized%20Counters.md) — Ring counters, Johnson (twisted-ring) counters with self-decoding states, self-starting counter synthesis, and lock-out recovery design.

---

## Objectives

- Understand how cross-coupled feedback transforms memoryless combinational gates into bistable storage elements.
- Analyze the critical distinction between level-sensitive latches and edge-triggered flip-flops.
- Master the operational characteristics, characteristic equations, and excitation tables of D, JK, and T flip-flops.
- Execute the complete analysis pipeline for clocked sequential circuits to extract state diagrams from gate schematics.
- Distinguish between Mealy and Moore finite state machines and evaluate their timing and architectural trade-offs.
- Apply state reduction techniques (row elimination and implication tables) and state assignment methods to minimize hardware cost.
- Synthesize complex sequential controllers from word specifications using systematic design procedures.
- Design registers, universal shift registers, asynchronous ripple counters, and high-speed synchronous counters.

---

Let's begin by discovering how a simple loop of silicon wires can preserve a bit of information forever. Read [**L01 - Latches and Storage Elements**](L01%20-%20Latches%20and%20Storage%20Elements.md).
