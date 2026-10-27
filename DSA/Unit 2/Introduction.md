[DSA Index](../README.md)

# Unit 2: Circular/Doubly Lists, Queues, and Tree Fundamentals

Welcome to Unit 2 of **Data Structures and Applications**.

In Unit 1, we worked with linear structures that grew in one direction and operated strictly under LIFO rules. In Unit 2, we expand our architectural reach:
- We make lists bidirectional through **Doubly Linked Lists** and cyclic through **Circular Linked Lists**.
- We introduce the first-come, first-served (FIFO) counterpart of the stack: **Queues**, exploring linear queues, circular queues with modulo arithmetic, double-ended queues (**Deques**), and **Priority Queues**.
- We apply queues to real-world computational problems: **Round Robin CPU scheduling** and the classic mathematical **Josephus Problem**.
- We transition from linear sequences to non-linear hierarchical structures: **Trees**, mastering fundamental terminology, binary tree properties, full/complete/perfect variations, and methods to convert arbitrary forests and N-ary trees into binary trees.

---

## Unit 2 Roadmap

- [**L01 - Circular Linked Lists**](L01%20-%20Circular%20Linked%20Lists.md) — Circular singly linked lists, advantages of circular traversal, insertion, deletion, and traversing using `do-while` loops.
- [**L02 - Doubly Linked Lists**](L02%20-%20Doubly%20Linked%20Lists.md) — Bidirectional node architecture (`prev` and `next`), forward and backward traversal, insertion and deletion mechanics, and boundary updates.
- [**L03 - Linear Queues - Array and Linked Implementations**](L03%20-%20Linear%20Queues%20-%20Array%20and%20Linked%20Implementations.md) — The First-In, First-Out (FIFO) principle, Queue ADT, front and rear index tracking, the false overflow drift problem in arrays, and linked list queues.
- [**L04 - Circular Queues**](L04%20-%20Circular%20Queues.md) — Overcoming linear array drift using modulo arithmetic ($(r+1)\%N$), full vs. empty queue disambiguation, and count/flag solutions.
- [**L05 - Deques and Priority Queues**](L05%20-%20Deques%20and%20Priority%20Queues.md) — Double-Ended Queues (Input-restricted and Output-restricted Deques), Priority Queue ADT, unordered vs. ordered linked list implementations, and min/max priority retrieval.
- [**L06 - Applications of Queues**](L06%20-%20Applications%20of%20Queues.md) — Operating system process scheduling: Round Robin time-slicing simulation, printer spooling buffers, and solving the Josephus Problem using circular queues.
- [**L07 - Introduction to Trees and Terminology**](L07%20-%20Introduction%20to%20Trees%20and%20Terminology.md) — Non-linear hierarchies, root, parent, child, siblings, leaf nodes, ancestors, descendants, levels, depth, height, degree of a node, and tree properties.
- [**L08 - Binary Trees - Properties and Representations**](L08%20-%20Binary%20Trees%20-%20Properties%20and%20Representations.md) — Strict, full, complete, perfect, and skewed binary trees, mathematical properties (max nodes per level, relation between height and leaves), contiguous array representation, and linked pointer representation.
- [**L09 - Forests and Conversion to Binary Trees**](L09%20-%20Forests%20and%20Conversion%20to%20Binary%20Trees.md) — General trees and N-ary trees, the Left-Child Right-Sibling (LCRS) representation, and systematically converting arbitrary forests into binary trees.

---

## Objectives

- Implement circular and doubly linked lists with full bidirectional pointer manipulation.
- Design Queue Abstract Data Types using contiguous circular arrays and dynamic linked nodes.
- Analyze priority queue implementations and evaluate time-complexity trade-offs.
- Simulate real-world queue scheduling (Round Robin and Josephus problem).
- Define tree hierarchies and compute depth, height, and node relationships.
- Differentiate between full, complete, and perfect binary trees and evaluate array vs. linked memory representations.
- Transform general multi-way trees and forests into equivalent binary trees using the left-child right-sibling technique.

---

Let's begin by mastering cyclic linked structures. Read [**L01 - Circular Linked Lists**](L01%20-%20Circular%20Linked%20Lists.md).
