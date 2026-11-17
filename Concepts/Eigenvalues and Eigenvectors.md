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

## Key results

- **Trace and determinant** are the sum and product of the eigenvalues (with multiplicity); for real $A$, non-real eigenvalues come in conjugate pairs with equal multiplicity. → [[Vectors and Matrices - Chapter 4 Eigenvalues and Eigenvectors#Proposition — Trace and determinant from eigenvalues|proof]]
- **Triangular / diagonal** matrices: the eigenvalues are the diagonal entries; for $\operatorname{diag}(d_j)$ the $\lambda$-eigenvectors span $\{\mathbf e_j:d_j=\lambda\}$. → [[Vectors and Matrices - Chapter 4 Eigenvalues and Eigenvectors#Triangular and diagonal matrices|lecture]]

## Examples

- $\begin{pmatrix}2&i\\-i&2\end{pmatrix}$: $\lambda=1$ with $(1,i)^{\mathsf T}$, $\lambda=3$ with $(1,-i)^{\mathsf T}$. → [[Vectors and Matrices - Chapter 4 Eigenvalues and Eigenvectors#Example — a complex matrix with real eigenvalues|lecture]]

## Related

[[Linear Maps and Matrices]] · [[Fundamental Theorem of Algebra]] · [[Complex Numbers]]
