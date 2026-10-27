[Maths Index](../README.md)

# Unit 2: Orthogonality, Eigenvalues, and Matrix Factorizations

Welcome to Unit 2 of **Mathematical Foundation for AI & Data Science (Linear Algebra)**.

In Unit 1, we established the fundamental algebraic foundations of vector spaces and matrix ranks. Now, we introduce geometric measurements—lengths, angles, perpendicularity, and directional stretching.

Unit 2 explores the core geometric and spectral theory of linear algebra:
- **Inner Products, Vector Norms, and Orthogonality**: measuring distances and angles in $\mathbb{R}^n$.
- Subspace geometry: **Orthogonal Complements** ($C(A^T) \perp N(A)$ and $C(A) \perp N(A^T)$).
- **Projections onto Lines and Subspaces**: the projection matrix $P = A(A^T A)^{-1}A^T$.
- Solving inconsistent overdetermined systems: **Least Squares Approximations** (the mathematical engine of linear regression in AI and machine learning).
- Constructing orthonormal bases: the **Gram-Schmidt Process** and the **$A = QR$ Factorization**.
- **Eigenvalues and Eigenvectors**: characteristic polynomials, trace, determinant, algebraic vs. geometric multiplicity.
- **Matrix Diagonalization** ($A = X \Lambda X^{-1}$) and decoupled dynamic systems.
- **Symmetric Matrices and the Spectral Theorem** ($A = Q \Lambda Q^T$).
- An introduction to the crown jewel of modern data science: **Singular Value Decomposition (SVD)** and **Principal Component Analysis (PCA)**.

---

## Unit 2 Roadmap

- [**L01 - Dot Product, Vector Norms, and Orthogonality**](L01%20-%20Dot%20Product,%20Vector%20Norms,%20and%20Orthogonality.md) — Inner products in $\mathbb{R}^n$, dot product algebraic properties, vector norms ($L_1, L_2, L_\infty$), distance metrics, angles between vectors, Cauchy-Schwarz inequality, and orthogonal vectors.
- [**L02 - Orthogonal Complements and Fundamental Subspaces**](L02%20-%20Orthogonal%20Complements%20and%20Fundamental%20Subspaces.md) — Orthogonal subspace complements $V^\perp$, geometric proof that Row Space is orthogonal to Null Space ($C(A^T) \perp N(A)$), and Column Space is orthogonal to Left Null Space ($C(A) \perp N(A^T)$).
- [**L03 - Projections onto Lines and Subspaces**](L03%20-%20Projections%20onto%20Lines%20and%20Subspaces.md) — 1D scalar and vector projections, projection matrices for lines, general subspace projection matrix $P = A(A^T A)^{-1}A^T$, and idempotent/symmetric properties ($P^2 = P, P^T = P$).
- [**L04 - Least Squares Approximations**](L04%20-%20Least%20Squares%20Approximations.md) — Solving inconsistent overdetermined systems $A\mathbf{x} = \mathbf{b}$, normal equations $A^T A \hat{\mathbf{x}} = A^T \mathbf{b}$, error vector orthogonality, and fitting linear models to noisy empirical data.
- [**L05 - The Gram-Schmidt Process and QR Factorization**](L05%20-%20The%20Gram-Schmidt%20Process%20and%20QR%20Factorization.md) — Gram-Schmidt orthogonalization algorithm, converting an arbitrary basis into an orthonormal basis, standardizing coordinates, and the $A = QR$ matrix decomposition.
- [**L06 - Introduction to Eigenvalues and Eigenvectors**](L06%20-%20Introduction%20to%20Eigenvalues%20and%20Eigenvectors.md) — The fundamental eigenvalue equation $A\mathbf{x} = \lambda\mathbf{x}$, characteristic polynomial $\det(A - \lambda I) = 0$, trace and determinant theorems, and algebraic vs. geometric multiplicity.
- [**L07 - Diagonalization of a Matrix**](L07%20-%20Diagonalization%20of%20a%20Matrix.md) — Diagonalizability conditions, matrix powers $A^k$, constructing the eigenvector matrix $X$ and eigenvalue matrix $\Lambda$, the similarity transformation $A = X \Lambda X^{-1}$, and applications in discrete dynamical systems.
- [**L08 - Symmetric Matrices and the Spectral Theorem**](L08%20-%20Symmetric%20Matrices%20and%20the%20Spectral%20Theorem.md) — Real eigenvalues of symmetric matrices, orthogonal eigenvectors, the Spectral Decomposition $A = Q \Lambda Q^T = \sum \lambda_i \mathbf{q}_i \mathbf{q}_i^T$, and positive definite matrices.
- [**L09 - Singular Value Decomposition and PCA Foundations**](L09%20-%20Singular%20Value%20Decomposition%20and%20PCA%20Foundations.md) — Limitations of diagonalization for non-square matrices, geometry of SVD ($A = U \Sigma V^T$), singular values $\sigma_i$, low-rank matrix approximation, and the mathematical foundations of Principal Component Analysis (PCA).

---

## Objectives

- Compute dot products, vector norms ($L_1, L_2$), angles, and verify orthogonality.
- Prove the orthogonality of the Four Fundamental Subspaces.
- Derive and construct projection matrices onto arbitrary subspaces.
- Solve inconsistent linear systems using the method of least squares and formulate normal equations.
- Apply the Gram-Schmidt process to generate orthonormal bases and compute $QR$ factorizations.
- Calculate eigenvalues and eigenvectors of square matrices using characteristic equations.
- Diagonalize matrices ($A = X \Lambda X^{-1}$) and compute matrix powers $A^k$.
- Apply the Spectral Theorem to decompose symmetric matrices into orthogonal rank-1 matrices.
- Formulate the Singular Value Decomposition (SVD) and explain its connection to Principal Component Analysis (PCA).

---

Let's begin by measuring vectors: inner products, norms, and the geometry of orthogonality. Read [**L01 - Dot Product, Vector Norms, and Orthogonality**](L01%20-%20Dot%20Product,%20Vector%20Norms,%20and%20Orthogonality.md).
