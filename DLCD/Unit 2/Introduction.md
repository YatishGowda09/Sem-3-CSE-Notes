[DLCD Index](../README.md)

# Unit 2: Synchronous Sequential Logic, Registers, and Counters

Welcome to Unit 2 of **Digital Logic and Computer Design**.

In Unit 1, every circuit we designed was strictly **combinational**: its outputs depended entirely and instantaneously on the current values applied to its inputs. Combinational circuits have no memory. They cannot track sequence, retain a previous arithmetic result, or coordinate actions that occur in a specific order over time.

Real computers, however, are fundamentally **state machines**. When an operating system boots, or when a processor steps through the instruction cycle, the hardware must maintain memory of where it is in the execution flow. 

Unit 2 introduces **Sequential Logic**, where circuits incorporate **memory elements** and **feedback paths**. In sequential circuits, the outputs depend not only on the current inputs, but also on the circuit's **present state** (its stored history). We focus on **synchronous** sequential circuits, where all state transitions across the entire machine are coordinated by a periodic master timing signal: the **system clock**.

---

## Unit 2 Roadmap

The lectures in this unit build systematically from cross-coupled physical gates to synchronous registers and counting machines:

- [**L01 - Storage Elements - Latches and Flip-Flops**](L01%20-%20Storage%20Elements%20-%20Latches%20and%20Flip-Flops.md) — The physics of feedback and bistability, SR Latch using NOR and NAND gates, the forbidden state hazard, Gated D Latch, the transparency race-around problem, edge-triggering, Master-Slave architecture, Edge-Triggered D, JK, and T flip-flops, characteristic equations, and excitation tables.
- [**L02 - Analysis of Clocked Sequential Circuits**](L02%20-%20Analysis%20of%20Clocked%20Sequential%20Circuits.md) — The systematic 5-step analysis pipeline: flip-flop input equations, output equations, next-state equations, state tables, and state diagrams.
- [**L03 - Mealy and Moore State Machine Models**](L03%20-%20Mealy%20and%20Moore%20State%20Machine%20Models.md) — Classical Finite State Machine (FSM) models: Moore machines (outputs depend only on state) vs. Mealy machines (outputs depend on state and inputs), timing comparisons, clock-to-output latency, and glitch vulnerability.
- [**L04 - State Reduction, State Assignment, and Sequential Design**](L04%20-%20State%20Reduction,%20State%20Assignment,%20and%20Sequential%20Design.md) — Minimizing sequential hardware: state equivalence theorems, row-matching state reduction, binary/Gray/one-hot state assignments, and the complete 7-stage sequential design procedure (sequence detector synthesis using D and JK flip-flops with self-starting verification).
- [**L05 - Registers and Shift Registers**](L05%20-%20Registers%20and%20Shift%20Registers.md) — Multi-bit data storage: why clock gating causes dangerous clock skew, 4-bit register with parallel load (using input multiplexers), shift registers (SISO, SIPO, PISO, PIPO), serial transfer, and serial addition.
- [**L06 - Ripple Counters**](L06%20-%20Ripple%20Counters.md) — Asynchronous counters: 4-bit binary ripple up-counters, down-counters, BCD ripple counters, propagation delay accumulation ($n \cdot t_{pd}$), and maximum operating frequency limits.
- [**L07 - Synchronous Counters**](L07%20-%20Synchronous%20Counters.md) — High-speed parallel counters: 4-bit binary synchronous up-counter with enable chain logic, and arbitrary non-binary sequence counter synthesis using excitation tables.
- [**L08 - Ring Counter and Johnson Counter**](L08%20-%20Ring%20Counter%20and%20Johnson%20Counter.md) — Specialized non-binary counters: Ring counters (circulating single-bit timing signals with zero decoding gates), Johnson (twisted-ring) counters ($2N$ states with glitch-free 2-input AND decoding), and counter architecture comparisons.

---

## Objectives

- Understand how cross-coupled feedback transforms memoryless combinational gates into bistable storage elements.
- Analyze the critical distinction between level-sensitive latches and edge-triggered flip-flops.
- Master the operational characteristics, characteristic equations, and excitation tables of D, JK, and T flip-flops.
- Execute the complete analysis pipeline for clocked sequential circuits to extract state diagrams from gate schematics.
- Distinguish between Mealy and Moore finite state machines and evaluate their timing and architectural trade-offs.
- Apply state reduction and state assignment methods to minimize hardware cost.
- Synthesize complex sequential controllers from word specifications using systematic design procedures.
- Design registers, shift registers, asynchronous ripple counters, synchronous counters, ring counters, and Johnson counters.

---

Let's begin by discovering how a simple loop of silicon wires can preserve a bit of information forever. Read [**L01 - Storage Elements - Latches and Flip-Flops**](L01%20-%20Storage%20Elements%20-%20Latches%20and%20Flip-Flops.md).
