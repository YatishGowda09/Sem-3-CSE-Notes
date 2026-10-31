[DLCD Index](../README.md)

# Unit 3: Basic Computer Structure, Addressing Modes, I/O, and Memory

Welcome to Unit 3 of **Digital Logic and Computer Design**.

In Units 1 and 2, we worked at the component level: assembling transistors into logic gates, minimizing Boolean equations with K-maps, and building registers, multiplexers, and finite state machines.

Unit 3 elevates our perspective from individual circuits to **Computer Organization and Architecture**. Here, we assemble those arithmetic circuits, registers, and controllers into a unified, general-purpose computing machine. We examine how a computer represents data in memory, how a processor fetches and decodes instructions, how programs manipulate memory through diverse addressing modes, how assembly language bridges human logic and machine code, how the CPU communicates with external input/output peripherals via interrupts and DMA, and how semiconductor RAM memories are organized.

---

## Unit 3 Roadmap

The lectures in this unit trace the architectural blueprint of general-purpose computers, following the classic foundational framework of Carl Hamacher, Zvonko Vranesic, and Safwat Zaky (*Computer Organization*):

- [**L01 - Basic Structure of Computers and Functional Units**](L01%20-%20Basic%20Structure%20of%20Computers%20and%20Functional%20Units.md) — The five classic functional units (Input, Memory, ALU, Output, Control Unit), Von Neumann vs. Harvard architectures, basic operational concepts, single- and multi-bus structures, and the fundamental processor performance equation ($T = N \times S / R$).
- [**L02 - Data Representation and Memory Organization**](L02%20-%20Data%20Representation%20and%20Memory%20Organization.md) — Integer representations (unsigned, sign-magnitude, 1's complement, 2's complement), memory byte addressability, Big-Endian vs. Little-Endian byte ordering, word alignment rules, and alphanumeric character encoding (ASCII).
- [**L03 - Memory Operations and Instruction Sequencing**](L03%20-%20Memory%20Operations%20and%20Instruction%20Sequencing.md) — Memory read and write cycles (MAR, MDR), the instruction execution cycle (Fetch, Decode, Execute), condition code flags (Negative, Zero, Overflow, Carry), and instruction field formats (3-, 2-, 1-, and 0-address machines).
- [**L04 - Addressing Modes**](L04%20-%20Addressing%20Modes.md) — Locating operands in memory and registers: Immediate, Register, Direct (Absolute), Indirect, Register Indirect, Indexed, Base with Index, Relative (PC-Relative), Autoincrement, and Autodecrement addressing modes.
- [**L05 - Assembly Language and Program Execution**](L05%20-%20Assembly%20Language%20and%20Program%20Execution.md) — Assembly language statement fields, mnemonics, assembler directives (`ORIGIN`, `EQU`, `DATAWORD`, `RESERVE`, `END`), two-pass assembler translation, symbol table creation, and the loader.
- [**L06 - Input-Output Organization, Polling, and Interrupts**](L06%20-%20Input-Output%20Organization,%20Polling,%20and%20Interrupts.md) — The I/O interface bridge: Memory-Mapped I/O vs. Port-Mapped I/O, device controllers, status/control/data registers, programmed I/O (polling), interrupt request lines, Interrupt Service Routines (ISR), context saving, vectored interrupts, and priority arbitration via Daisy Chaining.
- [**L07 - Direct Memory Access and Standard IO Interfaces**](L07%20-%20Direct%20Memory%20Access%20and%20Standard%20IO%20Interfaces.md) — High-speed bulk data transfers: the DMA Controller, bus arbitration (Bus Request and Bus Grant), burst mode vs. cycle stealing, and standard interconnect bus architectures (PCI Express, USB).
- [**L08 - Semiconductor RAM Memories**](L08%20-%20Semiconductor%20RAM%20Memories.md) — Internal memory organization: $2^k \times m$ 2D arrays, Static RAM (SRAM 6T cell), Dynamic RAM (DRAM 1T cell), DRAM capacitive leakage and periodic refresh cycles, Synchronous and DDR SDRAM, and memory chip cascading to expand word length and address capacity.

---

## Objectives

- Identify the primary functional units of a computer and trace the flow of instructions and data across system buses.
- Apply the basic computer performance equation ($T = N \times S / R$) to analyze processor throughput and execution time.
- Master memory addressability, word alignment, and byte ordering (Big-Endian vs. Little-Endian).
- Formulate instructions using diverse addressing modes and evaluate their impact on code density and execution speed.
- Trace assembly language translation across Pass 1 (symbol table) and Pass 2 (machine code generation).
- Differentiate between Memory-Mapped I/O and Port-Mapped I/O and analyze polling loops versus hardware interrupts.
- Analyze the end-to-end interrupt handling sequence, including context saving, vectoring, and priority daisy chaining.
- Understand the mechanics of Direct Memory Access (DMA) and evaluate bus arbitration schemes.
- Analyze the internal circuit operation of SRAM and DRAM memory cells, refresh cycles, and memory chip expansion.

---

Let's begin by examining how the primary functional units of a modern computer interact across system buses. Read [**L01 - Basic Structure of Computers and Functional Units**](L01%20-%20Basic%20Structure%20of%20Computers%20and%20Functional%20Units.md).
