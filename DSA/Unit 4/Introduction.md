[DSA Index](../README.md)

# Unit 4: Graphs, Hashing, and Tries

Welcome to Unit 4 of **Data Structures and Applications**.

In Unit 3, we studied hierarchical tree structures where every node has at most one parent. But real-world data—computer networks, social connections, flight routes, and software dependency chains—is fundamentally non-hierarchical and arbitrary.

Unit 4 explores the most versatile and computationally powerful data structures in software engineering:
- **Graphs**: Formal definitions, directed vs. undirected, weighted edges, and comparing **Adjacency Matrix** vs. **Adjacency List** representations.
- Graph Traversal Algorithms: **Breadth-First Search (BFS)** using queues and **Depth-First Search (DFS)** using recursion/stacks, with complete time and space complexity proofs.
- Solving foundational graph problems: **Connected Components**, **Bipartite testing**, **Cycle Detection**, and **Dijkstra's Single-Source Shortest Path Algorithm**.
- The ultimate $O(1)$ search mechanism: **Hashing**, hash functions, the Pigeonhole Principle and collisions, **Separate Chaining** (Open Hashing), and **Open Addressing** (Linear Probing, Quadratic Probing, Double Hashing).
- High-performance string retrieval: **Tries (Prefix Trees)**, prefix matching, word insertion/deletion, and auto-complete search engines.

---

## Unit 4 Roadmap

- [**L01 - Graph Fundamentals and Representations**](L01%20-%20Graph%20Fundamentals%20and%20Representations.md) — Graph definitions: vertices $V$, edges $E$, directed vs. undirected, self-loops, parallel edges, subgraphs, paths, cycles, degrees, Adjacency Matrix ($O(V^2)$ space) vs. Adjacency List ($O(V+E)$ space).
- [**L02 - Breadth-First Search**](L02%20-%20Breadth-First%20Search.md) — The BFS algorithm, queue data structure, visited tracking arrays, level-order expansion, finding shortest path in unweighted graphs, and $O(V + E)$ time complexity.
- [**L03 - Depth-First Search**](L03%20-%20Depth-First%20Search.md) — The DFS algorithm, recursive and stack implementations, edge classification (tree edges, back edges, forward edges, cross edges), and $O(V + E)$ time complexity.
- [**L04 - Graph Connectivity and Cycle Detection**](L04%20-%20Graph%20Connectivity%20and%20Cycle%20Detection.md) — Connected components in undirected graphs, Strongly Connected Components (SCC) in directed graphs (Kosaraju / Tarjan overview), and cycle detection algorithms.
- [**L05 - Shortest Path Algorithms - Dijkstra**](L05%20-%20Shortest%20Path%20Algorithms%20-%20Dijkstra.md) — Single-source shortest paths on weighted graphs with non-negative edges, greedy relaxation property, priority queue optimization, step-by-step trace, and $O((V+E)\log V)$ complexity.
- [**L06 - Hashing - Fundamentals and Hash Functions**](L06%20-%20Hashing%20-%20Fundamentals%20and%20Hash%20Functions.md) — Direct addressing limitations, hash tables, the hashing concept, properties of ideal hash functions, Division method, Multiplication method, and Mid-Square method.
- [**L07 - Collision Resolution - Open Hashing**](L07%20-%20Collision%20Resolution%20-%20Open%20Hashing.md) — The Pigeonhole Principle, collisions, Separate Chaining (Open Hashing), dynamic linked list buckets, Load Factor ($\alpha = n/m$), and average $O(1)$ search complexity.
- [**L08 - Collision Resolution - Closed Hashing**](L08%20-%20Collision%20Resolution%20-%20Closed%20Hashing.md) — Open Addressing (Closed Hashing), array probing, Linear Probing and primary clustering, Quadratic Probing and secondary clustering, Double Hashing, and lazy deletion.
- [**L09 - Tries - Prefix Trees**](L09%20-%20Tries%20-%20Prefix%20Trees.md) — Multi-way tree structure for strings, node alphabet arrays, word insertion, search, prefix matching, auto-complete dictionary applications, and space-time trade-offs.

---

## Objectives

- Construct graph data structures using both Adjacency Matrices and Adjacency Lists.
- Implement Breadth-First Search (BFS) and Depth-First Search (DFS) traversals and analyze their space-time complexity.
- Detect cycles in directed and undirected graphs.
- Execute Dijkstra's shortest path algorithm using priority queues.
- Design hash tables, evaluate hash functions, and calculate load factors.
- Resolve collisions using Separate Chaining and Open Addressing probing techniques.
- Implement Trie data structures for prefix matching and string search.

---

Let's begin by exploring the mathematical foundations and silicon representations of graph topologies. Read [**L01 - Graph Fundamentals and Representations**](L01%20-%20Graph%20Fundamentals%20and%20Representations.md).
