# Unit 3: Memory Management and Virtual Memory

Now that we know that we can share CPU between multiple processes by scheduler using various scheduling algorithms, to improve the utilisation of CPU and speed of the computer response for users.

But to run multiple processes to share the CPU, these processes need to be stored in main memory, where multiple programs will share the memory. 

Due to this we now need to come up with a way to properly manage memory, i.e., Memory management algorithms which use various different strategies, approaches, and hardware mechanisms. Selection of these memory management methods depends on various factors, but the critical one is the hardware design of the Memory Management Unit (MMU).

---

## Unit 3 Roadmap

The lectures in this unit trace the evolution of memory management from physical base/limit registers to modern virtual memory paging and thrashing control:

- [**L01 - Hardware and Address Translation**](L01%20-%20Hardware%20and%20Address%20Translation.md) — Address binding phases (compile, load, execution), logical vs. physical address spaces, base and limit registers, Memory Management Unit (MMU) relocation, dynamic loading, and dynamic linking (stubs and shared libraries).
- [**L02 - Swapping, Allocation, and Fragmentation**](L02%20-%20Swapping,%20Allocation,%20and%20Fragmentation.md) — Standard swapping, backing store I/O, contiguous memory allocation, variable-partition multiprogramming, allocation strategies (First-Fit, Best-Fit, Worst-Fit), internal vs. external fragmentation, and 50-percent rule compaction.
- [**L03 - Segmentation**](L03%20-%20Segmentation.md) — User's view of memory, logical segmentation architectures, segment tables (base and limit), hardware address translation mechanics, protection bits, and segment sharing across processes.
- [**L04 - Paging**](L04%20-%20Paging.md) — Breaking physical memory into fixed frames and logical memory into pages, elimination of external fragmentation, page table address translation (page number $p$ and offset $d$), internal fragmentation overhead, and frame allocation tables.
- [**L05 - Structure of the Page Table**](L05%20-%20Structure%20of%20the%20Page%20Table.md) — Scaling page tables for 32-bit and 64-bit address spaces: Hierarchical Paging (multi-level page tables), Hashed Page Tables, and Inverted Page Tables (mapping frame to PID and page).
- [**L06 - Virtual Memory and Demand Paging**](L06%20-%20Virtual%20Memory%20and%20Demand%20Paging.md) — The illusion of limitless memory, lazy swappers, valid-invalid bit in page tables, page fault trap lifecycle (OS page fault handler), pure demand paging, locality of reference, and Effective Access Time (EAT) calculation.
- [**L07 - Page Replacement Algorithms**](L07%20-%20Page%20Replacement%20Algorithms.md) — Frame allocation bottlenecks, dirty (modify) bit optimization, First-In First-Out (FIFO) and Belady's Anomaly, Optimal Algorithm (OPT), Least Recently Used (LRU) via counters and stack, and LRU approximations (Second-Chance / Clock Algorithm).
- [**L08 - Allocation of Frames and Thrashing**](L08%20-%20Allocation%20of%20Frames%20and%20Thrashing.md) — Minimum frame requirements, equal vs. proportional frame allocation, global vs. local replacement, the mechanics of Thrashing (CPU utilization collapse), the Working-Set Model, and Page-Fault Frequency (PFF) control.

---

## Objectives

- Explain the difference between a logical and a physical address and the role of the *memory management unit (MMU)* in translating addresses.
- Apply first-, best-, and worst-fit strategies for allocating memory contiguously.
- Explain the difference between internal and external fragmentation and calculate compaction trade-offs.
- Trace logical-to-physical address translation in paging systems using page tables and Translation Lookaside Buffers (TLBs).
- Describe hierarchical paging, hashed paging, and inverted page tables.
- Trace the lifecycle of a *page fault* and calculate Effective Access Time (EAT) under demand paging.
- Simulate page replacement algorithms: FIFO, OPT, LRU, and the Clock Algorithm, identifying Belady's Anomaly.
- Diagnose and prevent *Thrashing* using working-set models and page-fault frequency allocation.
