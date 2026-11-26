---
title: Eigenvalues and Eigenvectors
course: Part IA Vectors and Matrices
material_type: concept note
tags: [concept, vectors-and-matrices]
---

# Eigenvalues and Eigenvectors

> [!abstract] In one paragraph
> $\mathbf v\ne\mathbf 0$ is an eigenvector of $A$ with eigenvalue $\lambda$ if $A\mathbf v=\lambda\mathbf v$, i.e. $\mathbf v\in\ker(A-\lambda I)$. Such $\mathbf v$ exists exactly when $\det(A-\lambda I)=0$, so the eigenvalues are the roots of the characteristic polynomial $\chi_A(t)=\det(A-tI)=\prod_j(\lambda_j-t)$. Comparing coefficients gives $\operatorname{tr}A=\sum\lambda_j$ and $\det A=\prod\lambda_j$.

## Definitions

- **Eigenvector / eigenvalue** $T\mathbf v=\lambda\mathbf v$, $\mathbf v\ne\mathbf 0$; $\lambda=0$ allowed. → [[Vectors and Matrices - Chapter 4 Eigenvalues and Eigenvectors#Definition — Eigenvector and eigenvalue|lecture]]
- **Characteristic polynomial** $\chi_A(t)=\det(A-tI)$, leading coefficient $(-1)^n$; roots and multiplicities. → [[Vectors and Matrices - Chapter 4 Eigenvalues and Eigenvectors#Definition — Characteristic polynomial|lecture]] · [[Vectors and Matrices - Chapter 4 Eigenvalues and Eigenvectors#Definition — Root and multiplicity|lecture]]
- **Eigenspace** $E_\lambda=\ker(A-\lambda I)$; its non-zero elements are the $\lambda$-eigenvectors. → [[Vectors and Matrices - Chapter 4 Eigenvalues and Eigenvectors#Definition — Eigenspace|lecture]]
- **Algebraic multiplicity** $M_\lambda$: multiplicity of $\lambda$ as a root of $\chi_A$. **Geometric multiplicity:** $m_\lambda=\dim E_\lambda=n-\operatorname{rank}(A-\lambda I)$. → [[Vectors and Matrices - Chapter 4 Eigenvalues and Eigenvectors#Definition — Algebraic and geometric multiplicity|lecture]]

## Key results

- **Trace and determinant** are the sum and product of the eigenvalues (with multiplicity); for real $A$, non-real eigenvalues come in conjugate pairs with equal multiplicity. → [[Vectors and Matrices - Chapter 4 Eigenvalues and Eigenvectors#Proposition — Trace and determinant from eigenvalues|proof]]
- **Triangular / diagonal** matrices: the eigenvalues are the diagonal entries; for $\operatorname{diag}(d_j)$ the $\lambda$-eigenvectors span $\{\mathbf e_j:d_j=\lambda\}$. → [[Vectors and Matrices - Chapter 4 Eigenvalues and Eigenvectors#Triangular and diagonal matrices|lecture]]
- **Defect** $\Delta_\lambda=M_\lambda-m_\lambda\ge0$, since $1\le m_\lambda\le M_\lambda$. → [[Vectors and Matrices - Chapter 4 Eigenvalues and Eigenvectors#Proposition — Geometric multiplicity is at most algebraic multiplicity|lecture]] · [[Vectors and Matrices - Chapter 4 Eigenvalues and Eigenvectors#Definition — Defect|lecture]]
- **Independence.** Eigenvectors for distinct eigenvalues are linearly independent; bases of distinct eigenspaces together stay independent. *Idea:* apply $A-\lambda_1I$ to a dependence. → [[Vectors and Matrices - Chapter 4 Eigenvalues and Eigenvectors#Theorem — Eigenvectors for distinct eigenvalues are independent|proof]]

## Change of basis and similarity

- A map with matrix $A$ in one basis has matrix $P^{-1}AP$ in another, where $P$ has the new basis vectors (in old coordinates) as columns and $[\mathbf v]_{\text{old}}=P[\mathbf v]_{\text{new}}$. → [[Vectors and Matrices - Chapter 4 Eigenvalues and Eigenvectors#Definition — Change of basis matrix|lecture]] · [[Vectors and Matrices - Chapter 4 Eigenvalues and Eigenvectors#Change between two arbitrary bases|lecture]]
- $A$ and $B$ are **similar** if $B=P^{-1}AP$ with $P$ invertible; similarity is an equivalence relation. → [[Vectors and Matrices - Chapter 4 Eigenvalues and Eigenvectors#Definition — Similar matrices|lecture]] · [[Vectors and Matrices - Chapter 4 Eigenvalues and Eigenvectors#Proposition — Similarity is an equivalence relation|proof]]
- Similar matrices share $\chi$, trace, det, $M_\lambda$ and $m_\lambda$. Equal characteristic polynomials alone do not imply similarity: $I_2$ and a shear share $\chi=(1-t)^2$ but have $m_1=2$ and $m_1=1$. → [[Vectors and Matrices - Chapter 4 Eigenvalues and Eigenvectors#Proposition — Quantities preserved by similarity|lecture]]

## Diagonalisation

- $A$ is **diagonalisable** if $P^{-1}AP=D$ is diagonal, i.e. $\mathbb F^n$ has a basis of eigenvectors (the columns of $P$, in the order of the eigenvalues in $D$). → [[Vectors and Matrices - Chapter 4 Eigenvalues and Eigenvectors#Proposition — Diagonalisable matrices|lecture]]
- **Criterion:** diagonalisable iff $\chi_A$ splits over $\mathbb F$ and $m_\lambda=M_\lambda$ for every $\lambda$. $n$ distinct eigenvalues suffice; a diagonalisable matrix with one eigenvalue $\lambda$ is $\lambda I$. → [[Vectors and Matrices - Chapter 4 Eigenvalues and Eigenvectors#Theorem — Criterion for diagonalisation|lecture]]
- **Building $P$:** eigenvectors as columns, eigenvalues in the same order in $D$; check $AP=PD$. **Powers:** $A^k=PD^kP^{-1}$ and $p(A)=P\,p(D)P^{-1}$. → [[Vectors and Matrices - Chapter 4 Eigenvalues and Eigenvectors#4.4.1 Constructing a diagonalising matrix|lecture]] · [[Vectors and Matrices - Chapter 4 Eigenvalues and Eigenvectors#4.4.2 Powers and polynomials of a matrix|lecture]]

## Jordan canonical form

- Every complex $2\times2$ matrix is similar to $\operatorname{diag}(\lambda_1,\lambda_2)$, $\lambda I$ or $\begin{pmatrix}\lambda&1\\0&\lambda\end{pmatrix}$. → [[Vectors and Matrices - Chapter 4 Eigenvalues and Eigenvectors#Proposition — Jordan forms in dimension 2|proof]]
- **Jordan canonical form:** every $A\in\mathbb C^{n\times n}$ is similar to $\operatorname{diag}(J_{p_1}(\lambda_1),\dots,J_{p_s}(\lambda_s))$. For each $\lambda$ the block sizes add up to $M_\lambda$ and the number of blocks is $m_\lambda$; the columns of $P$ form chains $(A-\lambda I)\mathbf v_j=\mathbf v_{j-1}$ of generalised eigenvectors. → [[Vectors and Matrices - Chapter 4 Eigenvalues and Eigenvectors#Definition — Jordan block|lecture]] · [[Vectors and Matrices - Chapter 4 Eigenvalues and Eigenvectors#Theorem — Jordan canonical form|lecture]]
- **Hermitian matrices** have real eigenvalues, and eigenvectors for distinct eigenvalues are orthogonal (evaluate $\mathbf v^\dagger A\mathbf w$ two ways); real symmetric matrices have real eigenvectors. → [[Vectors and Matrices - Chapter 4 Eigenvalues and Eigenvectors#Theorem — Eigenvalues of Hermitian matrices|proof]]
- **Spectral theorem:** a Hermitian $A$ has an orthonormal eigenbasis, $U^\dagger AU=D$ real (Gram–Schmidt inside each eigenspace); real symmetric: $Q^{\mathsf T}AQ=D$. → [[Vectors and Matrices - Chapter 4 Eigenvalues and Eigenvectors#Proposition — Gram–Schmidt orthonormalisation|lecture]] · [[Vectors and Matrices - Chapter 4 Eigenvalues and Eigenvectors#Theorem — Spectral theorem|lecture]]
- **Quadratic forms** $q=\mathbf x^{\mathsf T}A\mathbf x$ become $\sum\lambda_jy_j^2$ along the principal axes; definiteness is read off the eigenvalue signs; level sets give ellipses, hyperbolas, ellipsoids, hyperboloids and cones. → [[Vectors and Matrices - Chapter 4 Eigenvalues and Eigenvectors#Principal axes|lecture]] · [[Vectors and Matrices - Chapter 4 Eigenvalues and Eigenvectors#Examples in 2D and 3D|examples]]

## Examples

- $\begin{pmatrix}2&i\\-i&2\end{pmatrix}$: $\lambda=1$ with $(1,i)^{\mathsf T}$, $\lambda=3$ with $(1,-i)^{\mathsf T}$. → [[Vectors and Matrices - Chapter 4 Eigenvalues and Eigenvectors#Example — a complex matrix with real eigenvalues|lecture]]
- Defects $0$, $1$, $2$: a $3\times3$ matrix with $E_{-3}$ a plane; $B$ with $\chi_B=-(t+2)^3$, $m=2$; $J$ with $m_4=1$. → [[Vectors and Matrices - Chapter 4 Eigenvalues and Eigenvectors#4.3.2 Examples and geometric interpretations|lecture]]

## Related

[[Linear Maps and Matrices]] · [[Fundamental Theorem of Algebra]] · [[Complex Numbers]]
