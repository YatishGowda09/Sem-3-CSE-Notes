[DSA Index](../README.md)

# Unit 1: Pointers, Memory Allocation, Linked Lists, and Stacks

Welcome to Unit 1 of **Data Structures and Applications**.

Computer programs process information. But before an algorithm can sort, search, or transform data, that data must be organized in physical computer memory.

Unit 1 explores the foundational building blocks of linear data structures:
- How memory is addressed and manipulated through **Pointers** and **Dynamic Memory Allocation** (`malloc`, `calloc`, `realloc`, `free`).
- How custom composite data types are defined using **Structures** and abstracted into formal **Abstract Data Types (ADTs)**.
- How contiguous memory limitations of arrays are overcome using **Singly Linked Lists**.
- How special list variations—such as **Header Linked Lists**, **Polynomial Linked Lists**, **Multilists**, and probabilistic **Skip Lists**—optimize real-world applications.
- The fundamental Last-In, First-Out (LIFO) engine of computation: **Stacks**, their array and linked implementations, and their vital applications in **Infix-to-Postfix conversion**, **arithmetic expression evaluation**, **function call frames**, and **recursion**.

---

## Unit 1 Roadmap

- [**L01 - Review of Pointers and Dynamic Memory Allocation**](L01%20-%20Review%20of%20Pointers%20and%20Dynamic%20Memory%20Allocation.md) — Pointers, memory addresses, pointer arithmetic, double pointers, dynamic heap management (`malloc`, `calloc`, `realloc`, `free`), memory leaks, and dangling pointers.
- [**L02 - Structures and Abstract Data Types**](L02%20-%20Structures%20and%20Abstract%20Data%20Types.md) — Structures in C, self-referential structures, memory alignment and padding, Abstract Data Types (ADTs), interface vs. implementation abstraction.
- [**L03 - Singly Linked Lists - Fundamentals and Insertion**](L03%20-%20Singly%20Linked%20Lists%20-%20Fundamentals%20and%20Insertion.md) — Node architecture, dynamic allocation, inserting at beginning, end, and arbitrary position, handling empty list edge cases.
- [**L04 - Singly Linked Lists - Deletion and Traversal**](L04%20-%20Singly%20Linked%20Lists%20-%20Deletion%20and%20Traversal.md) — Deleting from beginning, end, and by key value, linear traversal, searching, reversing a singly linked list in-place, and Big-$O$ complexity.
- [**L05 - Header Linked Lists and Circular Header Nodes**](L05%20-%20Header%20Linked%20Lists%20and%20Circular%20Header%20Nodes.md) — Grounded header lists vs. circular header lists, metadata encapsulation, and eliminating boundary condition edge-case code.
- [**L06 - Polynomial Representation and Arithmetic**](L06%20-%20Polynomial%20Representation%20and%20Arithmetic.md) — Modeling polynomials using linked lists (coefficient, exponent, link), polynomial addition, polynomial multiplication, and symbolic differentiation.
- [**L07 - Specialized Lists - Multilists and Skip Lists**](L07%20-%20Specialized%20Lists%20-%20Multilists%20and%20Skip%20Lists.md) — Multilists, sparse matrix representation with orthogonal row and column headers, Skip List architecture, probabilistic height assignment, and $O(\log n)$ search efficiency.
- [**L08 - Stacks - Representation and Operations**](L08%20-%20Stacks%20-%20Representation%20and%20Operations.md) — The LIFO principle, Stack ADT, array implementation with overflow and underflow detection, linked list stack implementation, and $O(1)$ push/pop mechanics.
- [**L09 - Applications of Stacks - Infix, Prefix, and Postfix**](L09%20-%20Applications%20of%20Stacks%20-%20Infix,%20Prefix,%20and%20Postfix.md) — Arithmetic notation, operator precedence and associativity, Shunting-Yard algorithm for Infix to Postfix/Prefix conversion, and stack-based Postfix evaluation.
- [**L10 - Applications of Stacks - Function Calls and Recursion**](L10%20-%20Applications%20of%20Stacks%20-%20Function%20Calls%20and%20Recursion.md) — Run-time stack frames, parameter passing, return address linkage, tracing recursion activation records, the Tower of Hanoi, and converting recursive algorithms to iterative stacks.

---

## Objectives

- Master dynamic memory allocation and pointer arithmetic in C to prevent memory leaks and segmentation faults.
- Implement singly linked lists with insertion, deletion, searching, and reversing operations.
- Construct specialized linked structures: header lists, polynomial accumulators, sparse matrices, and skip lists.
- Design Stack Abstract Data Types using both contiguous arrays and dynamic linked nodes.
- Solve expression parsing problems (infix to postfix and expression evaluation) using stack data structures.
- Analyze recursive execution trees and trace run-time activation records.

---

Let's begin by mastering the physical mechanics of computer memory and pointer manipulation. Read [**L01 - Review of Pointers and Dynamic Memory Allocation**](L01%20-%20Review%20of%20Pointers%20and%20Dynamic%20Memory%20Allocation.md).
