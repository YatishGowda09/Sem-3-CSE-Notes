# Unit 4: Storage Management, File Systems, I/O Scheduling, Protection, and Text Processing

Throughout the first three units of this course, we studied the volatile machinery of computation:
- In **Unit 1**, we studied how the CPU is protected via dual modes and multiplexed among competing processes through CPU scheduling.
- In **Unit 2**, we studied how concurrent processes and threads coordinate, synchronize shared state, and avoid deadlocks.
- In **Unit 3**, we studied how the memory hierarchy and Virtual Memory create the illusion of limitless physical RAM through paging and frame allocation.

Yet, every single data structure and process we have examined so far had one fatal property: **volatility**. The moment you turn off the power switch, every CPU register, cache line, and physical RAM frame is completely wiped clean.

Computer systems exist to produce, process, and retain data across time. To build software that survives reboots and hardware resets, the operating system must provide **Persistent Storage**.

---

## Unit 4 Roadmap

The lectures in this unit trace persistent storage from directory abstractions down to disk arm scheduling, RAID arrays, operating system security, and command-line text processing tools:

- [**L01 - File System - Directory Structure**](L01%20-%20File%20System%20-%20Directory%20Structure.md) — The file abstraction, naming, attributes, file types, access methods (sequential vs. direct), directory operations, and directory structures (single-level, two-level, tree-structured, acyclic-graph, general-graph).
- [**L02 - Storage Management - File Concept**](L02%20-%20Storage%20Management%20-%20File%20Concept.md) — File operations, file open/close lifecycle, per-process vs. system-wide open-file tables, file pointers, file locks (shared vs. exclusive, mandatory vs. advisory), and internal fragmentation in disk blocks.
- [**L03 - Mounting, File Sharing, and Protection**](L03%20-%20Mounting,%20File%20Sharing,%20and%20Protection.md) — File-system mounting, mount points, multi-user file sharing, Unix user/group/other permission bits (`chmod`), access control lists, and remote file systems (NFS).
- [**L04 - Implementing File Systems**](L04%20-%20Implementing%20File%20Systems.md) — Layered file-system architecture, on-disk structures (boot control block, superblock, inode table, directory blocks), in-memory structures, and the Virtual File System (VFS) abstraction.
- [**L05 - Disk Space Allocation Methods**](L05%20-%20Disk%20Space%20Allocation%20Methods.md) — Allocation mechanisms: Contiguous Allocation (external fragmentation), Linked Allocation (FAT tables), and Indexed Allocation (direct blocks, indirect blocks, multi-level inodes in Unix UFS/ext4).
- [**L06 - Free Space Management and Efficiency**](L06%20-%20Free%20Space%20Management%20and%20Efficiency.md) — Tracking free disk blocks: Bit Vectors (bitmaps), Linked Free Lists, Grouping, Counting, disk block clustering, and page cache / buffer cache architectures.
- [**L07 - Mass-Storage Structure**](L07%20-%20Mass-Storage%20Structure.md) — Physical disk drive mechanics (platters, tracks, sectors, cylinders, read/write heads), seek time, rotational latency, transfer rate, solid-state drive (SSD) flash cells, flash blocks, and wear leveling.
- [**L08 - Disk Scheduling**](L08%20-%20Disk%20Scheduling.md) — Minimizing mechanical head movement: FCFS, Shortest Seek Time First (SSTF), SCAN (Elevator Algorithm), C-SCAN (Circular SCAN), LOOK, and C-LOOK with worked total head movement calculations.
- [**L09 - RAID**](L09%20-%20RAID.md) — Redundant Arrays of Independent Disks: data striping, mirror redundancy, bit-level vs. block-level parity, and comprehensive analysis of RAID levels 0, 1, 4, 5, 6, and hybrid 0+1 / 10.
- [**L10 - Protection**](L10%20-%20Protection.md) — Goals and principles of protection, Principle of Least Privilege, Protection Domains, Domain Switching, and separation of mechanism from policy.
- [**L11 - Access Matrix**](L11%20-%20Access%20Matrix.md) — Formal model of protection: Access Matrix representation, dynamic rights modification (`copy`, `owner`, `control`), implementation via Access Control Lists (ACLs) and Capability Lists (C-Lists), and revocation of capabilities.
- [**L12 - Security**](L12%20-%20Security.md) — Operating system security: Confidentiality, Integrity, Availability, threat modeling, Trojan horses, trap doors, buffer overflows, viruses/worms, and authentication defense mechanisms.
- [**L13 - AWK and SED**](L13%20-%20AWK%20and%20SED.md) — Practical command-line stream manipulation: `sed` stream editor (substitution, deletion, addressing, regex) and `awk` structured text processing (pattern-action paradigm, `BEGIN`/`END` blocks, field variables `$1..$NF`, and associative arrays).

---

## Objectives

- Understand the file abstraction, attributes, file types, access methods (sequential vs. direct), and directory organizations (Single-level, Two-level, Tree, Acyclic-graph, and General-graph).
- Explain file-system mounting, multi-user file sharing, and permission protection modes.
- Dissect file-system implementation: File Control Blocks (FCB / inode), directory structures, and Virtual File Systems (VFS).
- Contrast disk allocation methods: **Contiguous Allocation**, **Linked Allocation** (FAT), and **Indexed Allocation** (Unix multi-level inodes).
- Analyze free-space management: bit vectors, linked free lists, grouping, and counting.
- Understand physical disk mechanics (seek time, rotational latency, transfer rate) and solid-state drive (SSD) wear leveling.
- Calculate total head movement across disk scheduling algorithms: **FCFS**, **SSTF**, **SCAN**, **C-SCAN**, **LOOK**, and **C-LOOK**.
- Compare **RAID** levels 0 through 6 in terms of striping, mirroring, parity calculation, and fault tolerance.
- Formulate the **Access Matrix** model of protection and evaluate implementations via Access Control Lists (ACLs) and Capability Lists (C-Lists).
- Identify system threats (Trojan horses, trap doors, buffer overflows) and authentication defenses.
- Write robust text transformation scripts using **sed** and structured data parsing programs using **awk**.
