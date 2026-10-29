# PESU SEM-3 Course Notes 

This repository is a comprehensive, intuitive, and deeply structured collection of coursework study notes covering core 3rd-semester subjects in Computer Science & Engineering and AI & Data Science.

If you've ever felt that university lecture slides are too brief and formula-heavy, while 1,000-page textbooks take way too long to navigate right before an exam, this vault bridges that gap. Every note is written in a conversational, "think-out-loud" style: explaining *why* things work from first principles before throwing math or code at you, walking through complete step-by-step examples, and visualizing concepts with clean Mermaid diagrams.

---

## What's Inside

The vault covers 5 complete university subjects, organized by lecture decks and modular units:

| Subject | Folder | Units | Total Lectures | Highlights |
| :--- | :--- | :--- | :--- | :--- |
| **Operating Systems** | [`OS/`](OS/README.md) | 4 | 44 Lectures | Process lifecycle, CPU scheduling, IPC, POSIX multithreading, synchronization primitives, deadlocks, virtual memory & paging, file systems, disk scheduling, and security access matrices. |
| **Computer Networks** | [`CN/`](CN/README.md) | 4 | 41 Lectures | The 5-layer Internet model, HTTP/HTTPS, DNS, socket programming, reliable transport (`rdt 1.0` to `3.0`), TCP congestion control, IPv4/IPv6, subnetting & CIDR, routing algorithms (Dijkstra, Distance Vector), CSMA/CD, and Ethernet switching. |
| **Digital Logic & Computer Design** | [`DLCD/`](DLCD/README.md) | 4 | 42 Lectures | Boolean algebra, K-map minimization, universal gate logic, adders & multipliers, multiplexers, latches & flip-flops, Mealy/Moore FSMs, counters, computer organization, single/multi-bus CPU datapath, and control unit design. |
| **Data Structures & Applications** | [`DSA/`](DSA/README.md) | 4 | 37 Lectures | Pointers & dynamic memory (`malloc`/`free`), linked lists (singly, doubly, circular, header, skip lists), stacks & queues, tree traversals, BST, AVL trees with rotations, splay trees, heaps, graphs (BFS, DFS, Dijkstra), hashing, and tries. Complete with runnable C code and Big-O tables. |
| **Mathematical Foundation for AI & Data Science** | [`Maths/`](Maths/README.md) | 4 | 37 Lectures | **Linear Algebra**: Systems $A\mathbf{x}=\mathbf{b}$, Gaussian elimination, LU decomposition, Four Fundamental Subspaces, projections, Least Squares, Gram-Schmidt & QR, eigenvalues, Spectral Theorem, SVD & PCA.<br>**Probability & Statistics**: Sampling models (tangible vs conceptual), random variables, CLT, point estimation (MSE), MLE, MAP, confidence intervals, $Z$/$t$-tests, ANOVA, and Chi-Square tests. |

---

## How to Use These Notes

You can use these notes however you prefer to study:

### 1. Directly on GitHub
All diagrams are written in Mermaid, and all formulas use LaTeX math syntax. GitHub natively renders both:
- **Diagrams**: Process states, memory layouts, network packets, and tree rotations render as visual flowcharts.
- **Math**: Display and inline equations render with full mathematical typography.
- **Navigation**: Click through breadcrumbs, unit roadmaps, and forward-looking lecture bridges to follow the syllabus sequentially.

### 2. In Obsidian (Recommended for Local Study)
Clone this repository and open the folder as an Obsidian vault:
- **Zero Broken Links**: All internal relative links are 100% valid and cross-linked across units and lecture files.
- **Graph View**: Explore visual connection graphs showing how concepts in Operating Systems (e.g. process queues) connect to Data Structures (e.g. circular queues) and Computer Architecture.

### 3. In VS Code or Any Markdown Editor
Any editor with a Markdown previewer supporting Mermaid and MathJax will render these notes out-of-the-box.

---

## Quick Subject Links

- **[Operating Systems (OS) Index](OS/README.md)** — [Topic Listing](OS/INDEX.md)
  - [Unit 1: Computer System Architecture, Processes, and Scheduling](OS/Unit%201/Introduction.md)
  - [Unit 2: Inter-Process Communication, Threads, and Synchronization](OS/Unit%202/Introduction.md)
  - [Unit 3: Memory Management and Virtual Memory](OS/Unit%203/Introduction.md)
  - [Unit 4: File Systems, Storage, and Security](OS/Unit%204/Introduction.md)

- **[Computer Networks (CN) Index](CN/README.md)** — [Topic Listing](CN/INDEX.md)
  - [Unit 1: Foundation and the Application Layer](CN/Unit%201/Introduction.md)
  - [Unit 2: Advanced Application Protocols and Transport Layer Fundamentals](CN/Unit%202/Introduction.md)
  - [Unit 3: Transport Layer Protocols and Network Layer Data Plane](CN/Unit%203/Introduction.md)
  - [Unit 4: Network Layer Control Plane and the Link Layer](CN/Unit%204/Introduction.md)

- **[Digital Logic & Computer Design (DLCD) Index](DLCD/README.md)** — [Topic Listing](DLCD/INDEX.md)
  - [Unit 1: Combinational Logic Design and Gate-Level Minimization](DLCD/Unit%201/Introduction.md)
  - [Unit 2: Synchronous Sequential Logic, Registers, and Counters](DLCD/Unit%202/Introduction.md)
  - [Unit 3: Basic Computer Structure, Addressing Modes, I/O, and Memory](DLCD/Unit%203/Introduction.md)
  - [Unit 4: Computer Arithmetic and Processing Unit Design](DLCD/Unit%204/Introduction.md)

- **[Data Structures and Applications (DSA) Index](DSA/README.md)** — [Topic Listing](DSA/INDEX.md)
  - [Unit 1: Pointers, Memory Allocation, Linked Lists, and Stacks](DSA/Unit%201/Introduction.md)
  - [Unit 2: Circular Lists, Queues, and Trees](DSA/Unit%202/Introduction.md)
  - [Unit 3: Advanced Trees and Heaps](DSA/Unit%203/Introduction.md)
  - [Unit 4: Graphs and Hashing](DSA/Unit%204/Introduction.md)

- **[Mathematical Foundation for AI & Data Science (Maths) Index](Maths/README.md)** — [Topic Listing](Maths/INDEX.md)
  - [Unit 1: Systems of Linear Equations, Vector Spaces, and Fundamental Subspaces](Maths/Unit%201/Introduction.md)
  - [Unit 2: Orthogonality, Eigenvalues, and Matrix Factorizations](Maths/Unit%202/Introduction.md)
  - [Unit 3: Probability Modeling and Parameter Estimation](Maths/Unit%203/Introduction.md)
  - [Unit 4: Hypothesis Testing and Statistical Inference](Maths/Unit%204/Introduction.md)

---

## Pedagogical Philosophy

Every note in this vault was constructed with strict guidelines:
- **Think-Out-Loud Prose**: Concepts are introduced by first asking the fundamental question: *Why does this problem exist?* The solution is derived step-by-step rather than presented as a sterile list of facts.
- **Purely Descriptive Headings**: No generic "Section 1" or "Part A" labels—every heading tells you exactly what concept is being tackled.
- **Visuals Over Walls of Text**: Complex memory allocations, network handshakes, logic schematics, and vector projections are mapped out in Mermaid.
- **Production-Quality Code & Worked Math**: DSA operations include full C code with careful memory management (`free()`), and Maths lectures include complete step-by-step numerical walkthroughs.

Happy studying!
