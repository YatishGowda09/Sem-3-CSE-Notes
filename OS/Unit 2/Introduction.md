# Unit 2: IPC, Threads, Synchronization, and Deadlocks

In Unit 1, we studied the isolated life of a single process: how it is structured in memory, how its registers and state are tracked in a Process Control Block, and how the CPU scheduler decides which process runs on a hardware core.

Unit 2 takes the next crucial leap: **what happens when processes need to cooperate, share work, and run concurrently?**

If processes were completely isolated from each other, modern computing would be impossible. A web browser could not fetch data and render pages simultaneously; a database server could not handle thousands of concurrent queries; and two processes could not exchange a single byte of data.

---

## Unit 2 Roadmap

The lectures in this unit trace concurrency from inter-process communication and multithreading to hardware synchronization, semaphores, deadlocks, and signals:

- [**L01 - IPC - Shared Memory and Message Passing**](L01%20-%20IPC%20-%20Shared%20Memory%20and%20Message%20Passing.md) — Inter-Process Communication models, shared memory regions vs. message passing (direct/indirect, synchronous/asynchronous), and buffering.
- [**L02 - System Calls for IPC**](L02%20-%20System%20Calls%20for%20IPC.md) — POSIX and System V IPC APIs: anonymous pipes (`pipe()`), named pipes (FIFOs, `mkfifo()`), shared memory (`shmget`, `shmat`), and message queues.
- [**L03 - Threads and Concurrency**](L03%20-%20Threads%20and%20Concurrency.md) — Motivation for lightweight threads, process vs. thread memory footprint, shared vs. private state, benefits of multithreading, and multicore programming hazards.
- [**L04 - Multithreading Models, Creation, and Scheduling**](L04%20-%20Multithreading%20Models,%20Creation,%20and%20Scheduling.md) — User-level vs. kernel-level threads, Many-to-One, One-to-One, and Many-to-Many models, POSIX Pthreads API, and Process/System Contention Scope (PCS vs. SCS).
- [**L05 - Windows Threads**](L05%20-%20Windows%20Threads.md) — Windows thread architecture, executive threads (ETHREAD) and kernel threads (KTHREAD), TEB, context switching, and thread pools.
- [**L06 - Mutual Exclusion - Software Approaches**](L06%20-%20Mutual%20Exclusion%20-%20Software%20Approaches.md) — The Critical-Section Problem, Mutual Exclusion, Progress, Bounded Waiting, and the formal proof of correctness for Peterson's Algorithm.
- [**L07 - Concurrency Principles and Synchronization Hardware**](L07%20-%20Concurrency%20Principles%20and%20Synchronization%20Hardware.md) — Race conditions, hardware instruction reordering, memory barriers, and atomic hardware instructions (`TestAndSet`, `CompareAndSwap`).
- [**L08 - Mutex Locks and Semaphores**](L08%20-%20Mutex%20Locks%20and%20Semaphores.md) — Mutex locks, spinlocks vs. sleep-locks, counting and binary semaphores, `wait()` and `signal()` primitives, and deadlock/starvation hazards.
- [**L09 - Classical Problems of Synchronization**](L09%20-%20Classical%20Problems%20of%20Synchronization.md) — Formal semaphore solutions to the Bounded-Buffer (Producer-Consumer) problem, Readers-Writers problem, and Dining Philosophers problem.
- [**L10 - Deadlocks**](L10%20-%20Deadlocks.md) — Four Coffman conditions for deadlock, Resource-Allocation Graphs (RAG), deadlock prevention, deadlock avoidance via Dijkstra's Banker's Algorithm, detection, and recovery.
- [**L11 - Signals**](L11%20-%20Signals.md) — Asynchronous notification in Unix/Linux: signal generation, kernel delivery, pending and blocked masks, default vs. custom handlers, and system calls (`kill()`, `sigaction()`).

---

## Objectives

- Contrast the two fundamental IPC models: **Shared Memory** vs. **Message Passing** (direct/indirect, synchronous/asynchronous).
- Understand and implement POSIX and System V IPC system calls: pipes, FIFO named pipes, shared memory (`shmget`, `shmat`), and message queues.
- Distinguish between a heavyweight process and a lightweight **Thread**, analyzing the shared vs. private components of thread state.
- Evaluate the three multithreading models: **Many-to-One**, **One-to-One**, and **Many-to-Many** (Two-Level Model), and trace thread scheduling via PCS and SCS.
- Understand the Windows thread architecture, executive threads, ETHREAD/KTHREAD blocks, and thread pools.
- Formulate the **Critical-Section Problem** and its three mandatory criteria: *Mutual Exclusion*, *Progress*, and *Bounded Waiting*.
- Prove the correctness of **Peterson's Algorithm** for two-process mutual exclusion.
- Analyze hardware atomic instructions: **`TestAndSet`** and **`CompareAndSwap`**, and understand memory barriers.
- Master synchronization tools: **Mutex Locks**, **Binary Semaphores**, and **Counting Semaphores**, analyzing spinlocks vs. blocking sleep-locks.
- Solve the three **Classical Problems of Synchronization**: *Bounded-Buffer (Producer-Consumer)*, *Readers-Writers*, and *Dining Philosophers*.
- Identify the four necessary Coffman conditions for **Deadlock**, construct **Resource-Allocation Graphs (RAG)**, run the **Banker's Algorithm** for deadlock avoidance, and implement deadlock detection and recovery algorithms.
- Explain the lifecycle of Unix **Signals**: generation, delivery, pending/blocked masks, default vs. custom handlers, and system calls (`kill()`, `signal()`, `sigaction()`).
