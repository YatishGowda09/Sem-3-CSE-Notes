[DSA Index](../README.md)

# Unit 3: Advanced Trees, Search Trees, and Heaps

Welcome to Unit 3 of **Data Structures and Applications**.

In Unit 2, we introduced the theoretical definitions of trees. Now, we transform trees into high-performance search engines and dynamic priority scheduling structures.

Unit 3 covers advanced non-linear structures:
- Systematic traversal of tree topologies: **Inorder, Preorder, Postorder, and Level-Order** traversals implemented both recursively and iteratively using stacks and queues.
- Evaluating mathematical expressions using **Expression Trees**.
- Exploiting wasted null pointers through **Threaded Binary Trees** to perform traversals with zero recursion or stack overhead.
- The fundamental search engine of computer science: **Binary Search Trees (BST)**, their insertion, search, and complex multi-case deletion mechanics.
- Overcoming skewed worst-case $O(n)$ degeneration using self-balancing trees: **AVL Trees** with single (LL, RR) and double (LR, RL) rotations, and self-adjusting **Splay Trees**.
- The foundation of priority scheduling: **Binary Heaps** (Min-Heap, Max-Heap), the in-place $O(n)$ `heapify` algorithm, and the optimal $O(n \log n)$ **Heap Sort**.

---

## Unit 3 Roadmap

- [**L01 - Binary Tree Traversals**](L01%20-%20Binary%20Tree%20Traversals.md) — Depth-First traversals (Inorder, Preorder, Postorder) recursive algorithms, iterative stack implementations, and Breadth-First Level-Order traversal using queues.
- [**L02 - Expression Trees**](L02%20-%20Expression%20Trees.md) — Expression tree representation of arithmetic expressions, tree construction from postfix expressions using stacks, infix reconstruction via parenthesized inorder traversal, and recursive tree evaluation.
- [**L03 - Threaded Binary Trees**](L03%20-%20Threaded%20Binary%20Trees.md) — Utilizing null pointer links ($2n - (n-1) = n+1$ null links), single-threaded and double-threaded trees, inorder successor algorithm, and stack-free traversal.
- [**L04 - Binary Search Trees - Insertion and Search**](L04%20-%20Binary%20Search%20Trees%20-%20Insertion%20and%20Search.md) — The BST ordering property ($\text{Left} < \text{Root} < \text{Right}$), recursive and iterative search, dynamic node insertion, and height-dependent time complexity $O(h)$.
- [**L05 - Binary Search Trees - Deletion**](L05%20-%20Binary%20Search%20Trees%20-%20Deletion.md) — The three deletion cases: deleting a leaf node, deleting a node with one child, and deleting a node with two children via inorder predecessor/successor replacement.
- [**L06 - AVL Trees - Balanced Search Trees**](L06%20-%20AVL%20Trees%20-%20Balanced%20Search%20Trees.md) — The skewing problem in BSTs, Adelson-Velsky and Landis (AVL) height balance property, Balance Factor ($\text{BF} \in \{-1, 0, 1\}$), and detecting unbalance.
- [**L07 - AVL Rotations**](L07%20-%20AVL%20Rotations.md) — Rebalancing unbalanced AVL trees: Left-Left (LL) rotation, Right-Right (RR) rotation, Left-Right (LR) double rotation, and Right-Left (RL) double rotation.
- [**L08 - Splay Trees**](L08%20-%20Splay%20Trees.md) — Self-adjusting binary search trees, the temporal locality heuristic, splaying operations (Zig, Zig-Zig, Zig-Zag), and amortized $O(\log n)$ performance.
- [**L09 - Binary Heaps and Heap Sort**](L09%20-%20Binary%20Heaps%20and%20Heap%20Sort.md) — Complete binary tree structure, array indexing ($2i+1, 2i+2$), Min-Heap and Max-Heap properties, bottom-up $O(n)$ `heapify`, root extraction, and in-place $O(n \log n)$ Heap Sort.

---

## Objectives

- Implement recursive and iterative tree traversals (Inorder, Preorder, Postorder, Level-Order).
- Construct and evaluate arithmetic expression trees.
- Design threaded binary trees to eliminate recursion memory overhead.
- Execute complete Binary Search Tree (BST) operations: search, insertion, and three-case deletion.
- Calculate balance factors and execute single and double AVL rotations to guarantee $O(\log n)$ search times.
- Analyze self-adjusting splay trees and amortized algorithmic complexity.
- Construct binary heaps in contiguous arrays and execute Heap Sort.

---

Let's begin by mastering the pathways through tree topologies. Read [**L01 - Binary Tree Traversals**](L01%20-%20Binary%20Tree%20Traversals.md).
