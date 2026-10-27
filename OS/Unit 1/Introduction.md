# Unit 1: OS Architecture, Process Management, and CPU Scheduling

An operating system is the software that sits directly between computer hardware and the user's applications. 

Without an operating system, every programmer writing software would need to write their own code to spin up hard disk motors, handle electrical keyboard scan codes, draw raw pixels onto display framebuffers, and manually manage CPU registers. Even worse, only one person or program could ever touch the computer at a time, because there would be no referee to prevent one program from overwriting another program's data.

Unit 1 builds the entire conceptual foundation of how an operating system operates, what services it provides, how multiple programs share a single processor, and how the CPU decides who gets to run next.

---

## Unit 1 Roadmap

The lectures in this unit trace the journey from raw hardware bootstrapping to user-space process execution and CPU scheduling:

- [**L01 - Introduction and Computer System Organization**](L01%20-%20Introduction%20and%20Computer%20System%20Organization.md) — Hardware bootstrapping, interrupts, interrupt vector tables, storage hierarchy, and Direct Memory Access (DMA).
- [**L02 - Computer System Architecture and OS Operations**](L02%20-%20Computer%20System%20Architecture%20and%20OS%20Operations.md) — Multiprocessor systems (SMP vs. ASMP), multi-core architectures, dual-mode execution (user vs. kernel), privileged instructions, and hardware timers.
- [**L03 - OS Services and Process Concept**](L03%20-%20OS%20Services%20and%20Process%20Concept.md) — Operating system services, process memory layout (text, data, BSS, heap, stack), 5-state process lifecycle, and Process Control Blocks (PCB).
- [**L04 - Process Creation, Termination, and System Calls**](L04%20-%20Process%20Creation,%20Termination,%20and%20System%20Calls.md) — Process creation mechanics (`fork()`, `exec()`, `wait()`), process trees, termination, zombie and orphan processes, and init/systemd adoption.
- [**L05 - CPU Scheduling - FCFS and SJF**](L05%20-%20CPU%20Scheduling%20-%20FCFS%20and%20SJF.md) — Scheduling criteria, First-Come First-Served (FCFS) convoy effects, Shortest Job First (SJF), and Shortest Remaining Time First (SRTF) preemptive scheduling.
- [**L06 - Priority and Round Robin Scheduling**](L06%20-%20Priority%20and%20Round%20Robin%20Scheduling.md) — Static and dynamic priority scheduling, starvation and aging, Round Robin (RR) time quantum optimization, and context-switching overhead.
- [**L07 - Multilevel Queue and Feedback Queue Scheduling**](L07%20-%20Multilevel%20Queue%20and%20Feedback%20Queue%20Scheduling.md) — Multilevel Queue (MLQ) partitioning, Multilevel Feedback Queue (MLFQ) dynamic priority aging, and multi-processor CPU scheduling.
- [**L08 - Bash Shell and cron**](L08%20-%20Bash%20Shell%20and%20cron.md) — Shell architecture, command execution, pipes and I/O redirection, shell scripting, environment variables, and automated job scheduling with the cron daemon.

---

## Objectives

- Understand the four basic components of a computer system and the dual view of an OS: as a *resource allocator* and as a *control program*.
- Trace the hardware bootstrapping process and the role of hardware and software *interrupts*.
- Explain the storage hierarchy, caching trade-offs, and how *Direct Memory Access (DMA)* frees the CPU from low-level data transfers.
- Distinguish between single-processor, multiprocessor (SMP vs. ASMP), and multi-core systems.
- Explain *dual-mode operation* (user mode vs. kernel mode) and how hardware timers prevent rogue processes from hijacking the machine.
- Define a *process*, trace its lifecycle through the 5 process states, and examine the contents of a *Process Control Block (PCB)*.
- Trace process creation via `fork()`, process termination, and the lifecycle of *zombie* and *orphan* processes.
- Analyze CPU scheduling criteria and calculate Gantt charts, waiting times, and turnaround times for *FCFS*, *SJF / SRTF*, *Priority*, *Round Robin (RR)*, and *Multilevel Feedback Queues (MLFQ)*.
- Write and schedule automated administrative tasks using the *Bash shell* and the *cron* daemon.
