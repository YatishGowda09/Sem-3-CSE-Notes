[Maths Index](../README.md)

# Unit 1: Systems of Linear Equations, Vector Spaces, and Fundamental Subspaces

Welcome to Unit 1 of **Mathematical Foundation for AI & Data Science (Linear Algebra)**.

Linear algebra is the foundational mathematical language of artificial intelligence, machine learning, and data science:
- Deep neural networks are matrices of synaptic weights.
- High-dimensional datasets are collections of vectors in $\mathbb{R}^n$.
- Image compression, dimensionality reduction, and optimization algorithms are matrix transformations.

Unit 1 explores the foundational theory of linear equations and vector spaces:
- How systems of linear equations ($A\mathbf{x} = \mathbf{b}$) are represented geometrically through row and column pictures.
- Systematic solution mechanisms: **Gaussian Elimination**, Row Echelon Form (REF), and Reduced Row Echelon Form (RREF).
- Matrix invertibility, pivots, free variables, and the **Rouche-Capelli Consistency Theorem**.
- Matrix factorizations: **LU Decomposition** ($A = LU$, $PA = LU$) and **Gauss-Jordan Inversion**.
- The abstract geometry of **Vector Spaces and Subspaces**, linear combinations, linear span, independence, bases, and dimension.
- The crown jewel of linear algebra: **The Four Fundamental Subspaces of a Matrix** ($C(A), N(A), C(A^T), N(A^T)$), the Rank-Nullity Theorem, and the Fundamental Theorem of Linear Algebra.
- **Linear Transformations**, kernel, range, and their matrix representations.

---

## Unit 1 Roadmap

- [**L01 - Systems of Linear Equations and Matrix Representation**](L01%20-%20Systems%20of%20Linear%20Equations%20and%20Matrix%20Representation.md) — Linear systems $A\mathbf{x} = \mathbf{b}$, the row picture (intersecting hyperplanes) vs. the column picture (linear combination of columns), coefficient matrix, and augmented matrix.
- [**L02 - Gaussian Elimination and Row Echelon Form**](L02%20-%20Gaussian%20Elimination%20and%20Row%20Echelon%20Form.md) — Elementary row operations, forward elimination, pivots, Row Echelon Form (REF), Reduced Row Echelon Form (RREF), back-substitution, and computational complexity.
- [**L03 - Matrix Rank and Consistency of Linear Systems**](L03%20-%20Matrix%20Rank%20and%20Consistency%20of%20Linear%20Systems.md) — Rank of a matrix, pivot variables vs. free variables, the Rouche-Capelli theorem, homogeneous systems, and classifying systems into unique solution, infinite solutions, or inconsistent (no solution).
- [**L04 - LU Decomposition**](L04%20-%20LU%20Decomposition.md) — Factoring $A = LU$, elimination matrices $E_{ij}$, unit lower triangular $L$, upper triangular $U$, solving $A\mathbf{x}=\mathbf{b}$ via $L\mathbf{y}=\mathbf{b}$ and $U\mathbf{x}=\mathbf{y}$, permutation matrices, and $PA = LU$.
- [**L05 - Matrix Inversion by Gauss-Jordan Elimination**](L05%20-%20Matrix%20Inversion%20by%20Gauss-Jordan%20Elimination.md) — Definition of inverse, invertibility conditions, Gauss-Jordan method $[A \mid I] \to [I \mid A^{-1}]$, singular matrices, and computational pitfalls.
- [**L06 - Vector Spaces and Subspaces**](L06%20-%20Vector%20Spaces%20and%20Subspaces.md) — The 8 vector space axioms over $\mathbb{R}^n$, closure under vector addition and scalar multiplication, the subspace test, and geometric examples in $\mathbb{R}^2$ and $\mathbb{R}^3$.
- [**L07 - Linear Independence, Basis, and Dimension**](L07%20-%20Linear%20Independence,%20Basis,%20and%20Dimension.md) — Linear combinations, linear span $\text{span}(S)$, linear independence and dependence tests, basis of a vector space, dimension, and minimal spanning sets.
- [**L08 - The Four Fundamental Subspaces**](L08%20-%20The%20Four%20Fundamental%20Subspaces.md) — Column Space $C(A)$, Null Space $N(A)$, Row Space $C(A^T)$, Left Null Space $N(A^T)$, finding bases and dimensions, the Rank-Nullity Theorem ($r + (n-r) = n$), and the Fundamental Theorem of Linear Algebra.
- [**L09 - Linear Transformations**](L09%20-%20Linear%20Transformations.md) — Definition of linear transformations $T: V \to W$, properties, matrix representation with respect to standard and non-standard bases, kernel (null space), range (column space), and change of basis.

---

## Objectives

- Formulate and solve systems of linear equations using Gaussian elimination and row echelon forms.
- Compute matrix ranks and determine system consistency via the Rouche-Capelli theorem.
- Factor matrices into LU and PA=LU forms and apply forward/back-substitution for fast multi-vector solving.
- Calculate matrix inverses using the Gauss-Jordan elimination algorithm.
- Verify vector space and subspace axioms.
- Test for linear independence, construct bases, and compute subspace dimensions.
- Identify and construct bases for the Four Fundamental Subspaces ($C(A), N(A), C(A^T), N(A^T)$) and apply the Rank-Nullity Theorem.
- Represent linear transformations as matrices and compute their kernels and ranges.

---

Let's begin by exploring the geometric duality of linear equations: the row picture versus the column picture. Read [**L01 - Systems of Linear Equations and Matrix Representation**](L01%20-%20Systems%20of%20Linear%20Equations%20and%20Matrix%20Representation.md).
