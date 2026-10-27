[DLCD Index](../README.md) / [Unit 2: Synchronous Sequential Logic](Introduction.md)

# L05 - State Reduction and State Assignment

When you translate an engineering specification into an initial Finite State Machine, your primary focus is correctness: making sure every branch, timeout, and condition is accounted for. As a result, initial state diagrams almost always contain **redundant states**—multiple states that perform the exact same logical function.

In silicon design, states are not free. An $m$-state machine requires:
$$n = \lceil \log_2 m \rceil \text{ flip-flops}$$

If a machine has 5 states, it requires 3 flip-flops (which can support up to 8 states). If we can reduce those 5 states to 4, we save a flip-flop and eliminate substantial combinational gating.

In this lecture, we explore the two primary algorithms for **State Reduction**—Row Elimination and the Implication Table method—and examine how **State Assignment** determines the ultimate hardware cost of the circuit.

---

## The Principle of State Equivalence

How do we prove that two states are truly redundant?

From the outside world, a sequential circuit is a black box: an engineer applies a stream of input bits and observes the stream of output bits. If you can replace State $A$ with State $B$, and no possible sequence of future inputs can ever reveal a difference in the outputs, then States $A$ and $B$ are **equivalent**.

### The State Equivalence Theorem

> **Two states $S_i$ and $S_j$ are equivalent ($S_i \equiv S_j$) if and only if, for every possible input combination:**
> 1. They produce the exact same external outputs.
> 2. Their next states are either identical or equivalent.

If two states are equivalent, we can eliminate one of them entirely and replace all transitions pointing to it with the remaining state, without altering the external behavior of the system.

---

## Method 1: The Row Elimination Method

The simplest way to find equivalent states is direct inspection of the state table.

### Procedure:
1. Examine the state table for any two rows that have:
   - **Identical next states** for all input columns, AND
   - **Identical outputs** for all input columns.
2. If such a pair $(S_i, S_j)$ exists, they are trivially equivalent.
3. Remove row $S_j$.
4. Replace all occurrences of $S_j$ in the next-state columns with $S_i$.
5. Repeat the process on the modified table until no further identical rows can be found.

---

### Worked Example: Row Elimination

Consider the following 7-state Mealy state table:

| Present State | Next State ($x = 0$) | Next State ($x = 1$) | Output $y$ ($x = 0$) | Output $y$ ($x = 1$) |
| :---: | :---: | :---: | :---: | :---: |
| **a** | a | b | 0 | 0 |
| **b** | c | d | 0 | 0 |
| **c** | a | d | 0 | 0 |
| **d** | e | f | 0 | 1 |
| **e** | a | f | 0 | 1 |
| **f** | g | f | 0 | 1 |
| **g** | a | f | 0 | 1 |

Let's inspect the rows systematically:

#### Pass 1: Compare Rows $e$ and $g$
- Row **e**: Next states $(a, f)$, Outputs $(0, 1)$.
- Row **g**: Next states $(a, f)$, Outputs $(0, 1)$.
- Both the next states and the outputs are identical!
- **Conclusion**: State $e$ is equivalent to state $g$ ($e \equiv g$).
- We eliminate row **g**, and replace every occurrence of $g$ in the table with $e$.

Row **f** previously had next state $g$ for $x = 0$. It now points to $e$:
- Row **f**: Next states become $(e, f)$, Outputs $(0, 1)$.

---

#### Pass 2: Compare Rows $d$ and $f$
Now inspect the updated table:
- Row **d**: Next states $(e, f)$, Outputs $(0, 1)$.
- Row **f**: Next states $(e, f)$, Outputs $(0, 1)$ (updated in Pass 1).
- They are now identical!
- **Conclusion**: State $d$ is equivalent to state $f$ ($d \equiv f$).
- We eliminate row **f**, and replace every occurrence of $f$ with $d$.

Let's update the remaining rows:
- Row **d**: Next states become $(e, d)$.
- Row **e**: Next states $(a, f)$ become $(a, d)$.

---

#### The Reduced State Table

No further rows are identical. Let's inspect the final reduced table:

| Present State | Next State ($x = 0$) | Next State ($x = 1$) | Output $y$ ($x = 0$) | Output $y$ ($x = 1$) |
| :---: | :---: | :---: | :---: | :---: |
| **a** | a | b | 0 | 0 |
| **b** | c | d | 0 | 0 |
| **c** | a | d | 0 | 0 |
| **d** | e | d | 0 | 1 |
| **e** | a | d | 0 | 1 |

Look at what we accomplished:
- We started with **7 states**, which required $\lceil \log_2 7 \rceil = \mathbf{3\text{ flip-flops}}$.
- We reduced the machine to **5 states**. While 5 states still technically requires 3 flip-flops, the next-state logic is substantially smaller because two full rows of decoding were eliminated. If we can eliminate one more state, we drop to 2 flip-flops!

---

## Method 2: The Implication Table Method

While row elimination is fast, it has a serious flaw: **it only catches equivalence when next states are already identical**.

What if State $A$ transitions to State $B$, while State $B$ transitions to State $A$? Their next states are not identical, yet they might be mutually equivalent! Row elimination fails to detect these cyclic dependencies.

To guarantee finding **every single equivalent state pair**, digital engineers use the **Implication Table (or Implication Chart)** method.

---

### The Implication Chart Structure

An Implication Table is a triangular grid where every cell represents a unique pair of states $(S_i, S_j)$. 

For an $n$-state machine with states $a, b, c, d, \dots$:
- The vertical axis lists states $b, c, d, \dots$ (from the second state to the last).
- The horizontal axis lists states $a, b, c, \dots$ (from the first state to the second-to-last).

```
b | (a, b)
c | (a, c)  (b, c)
d | (a, d)  (b, d)  (c, d)
e | (a, e)  (b, e)  (c, e)  (d, e)
----+-------------------------------
       a       b       c       d
```

---

### The Systematic Algorithm

1. **Step 1: Output Incompatibility (Initial Cross-Out)**:
   Examine each pair $(S_i, S_j)$. If their outputs differ for *any* input condition, they can never be equivalent. Place an **$\times$** in that square immediately.
2. **Step 2: Enter Implied Next-State Pairs**:
   For cells that were not crossed out, write the pairs of next states that must be equivalent for this pair to be equivalent. 
   - For example, if on input $0$ states $a$ and $b$ transition to $c$ and $d$, write $(c, d)$ in cell $(a, b)$.
   - If the next states are identical (e.g., both transition to $c$), write nothing (self-consistent).
3. **Step 3: Iterative Elimination Passes**:
   Systematically scan every uncrossed cell. Look at the implied state pairs written inside:
   - If *any* implied pair in that cell has an **$\times$** in its own square on the chart, then the premise is false! Place an **$\times$** through this cell as well.
   - Continue making passes across the chart until an entire pass completes **with no new crosses added**.
4. **Step 4: Group Equivalent States**:
   Every square that remains uncrossed represents an equivalent pair. Combine overlapping pairs into equivalence classes (e.g., if $a \equiv b$ and $b \equiv c$, then $\{a, b, c\}$ merge into a single state).

---

## State Assignment (State Encoding)

Once the state machine is reduced to $m$ minimal states, we must translate the abstract symbolic state names ($a, b, c, \dots$) into physical binary bit strings ($00, 01, 10, \dots$).

This mapping is called **State Assignment**.

For an $m$-state machine, we need $n$ state variables (flip-flops) where $2^n \ge m$.
How we assign binary patterns to states does **not** change the functional behavior of the circuit, but it drastically impacts the **number of logic gates** required to implement the next-state equations!

---

### Common State Assignment Strategies

Suppose we have 4 states: $S_0, S_1, S_2, S_3$.

| State | Binary (Straight) | Gray Code | One-Hot Encoding |
| :---: | :---: | :---: | :---: |
| **$S_0$** | 00 | 00 | 0001 |
| **$S_1$** | 01 | 01 | 0010 |
| **$S_2$** | 10 | 11 | 0100 |
| **$S_3$** | 11 | 10 | 1000 |

#### 1. Binary (Straight) Encoding
- Simply assigns states in standard binary counting order ($0, 1, 2, 3$).
- Uses the minimum number of flip-flops ($n = \lceil \log_2 m \rceil$).
- Simple to understand, but can result in irregular next-state logic and simultaneous multi-bit transitions.

#### 2. Gray Code Encoding
- Consecutive states in the primary operational cycle differ by **only a single bit**.
- Minimizes dynamic switching power and reduces the likelihood of transient glitches on state lines.

#### 3. One-Hot Encoding
- Allocates **one dedicated flip-flop for every single state**.
- An $m$-state machine requires $m$ flip-flops! At any instant, exactly one flip-flop holds a `1` while all others hold `0`.
- **Why would anyone waste so many flip-flops?**
  Because the next-state and output logic becomes shockingly simple! You don't need multi-level decoders or large K-maps. The condition "circuit is in state $S_3$" is literally just the wire $Q_3$!
- One-hot encoding is the industry standard for **FPGAs (Field Programmable Gate Arrays)**, where flip-flops are abundant but routing complex combinational logic is costly.

---

### Armstrong's Heuristic Rules for Minimal Combinational Logic

If you are using binary encoding and want to minimize the number of AND and OR gates in your D or JK flip-flop excitation equations, follow these three classic guidelines:

#### Guideline 1: Adjacent Next States (Highest Priority)
> States that have the **same next state** for a given input should be assigned adjacent binary codes (differing by only 1 bit).

*Why*: In the K-map for the next-state variables, these present states will be placed in adjacent cells, allowing them to be grouped together into a larger prime implicant.

#### Guideline 2: Common Present States
> Next states that originate from the **same present state** under complementary inputs should be assigned adjacent binary codes.

*Why*: This simplifies the combinational logic driving the flip-flop inputs from that specific state.

#### Guideline 3: Common Outputs
> States that produce the **same output** for a given input should be assigned adjacent binary codes.

*Why*: This allows the output K-maps to form larger groupings, minimizing the output gate count.

---

## Key Takeaways

- **State Reduction** eliminates redundant states to minimize the required number of flip-flops ($n = \lceil \log_2 m \rceil$) and simplify combinational logic.
- Two states are **equivalent** if and only if they produce the same outputs and transition to identical or equivalent next states for all possible inputs.
- The **Row Elimination Method** finds equivalent states by direct visual inspection of identical rows, but misses cyclic dependencies.
- The **Implication Table Method** provides an exhaustive, algorithmic proof of all state equivalences by tracking implied next-state pairs across a triangular chart.
- **State Assignment** maps symbolic state names to binary bit vectors.
- **One-Hot Encoding** uses $m$ flip-flops for $m$ states, trading flip-flop count for ultra-simple next-state logic.
- **Adjacent state assignments** for states sharing next states or outputs systematically maximize K-map groupings and minimize gate hardware.

---

We have now learned how to analyze sequential circuits, choose between Mealy and Moore architectures, and reduce states to their absolute mathematical minimum. Now we are ready to build. In the next lecture, we walk through the complete end-to-end [**Sequential Circuit Design Procedure**](L06%20-%20Sequential%20Circuit%20Design%20Procedure.md), transforming a raw English problem description into a fully synthesized gate-and-flip-flop schematic.
