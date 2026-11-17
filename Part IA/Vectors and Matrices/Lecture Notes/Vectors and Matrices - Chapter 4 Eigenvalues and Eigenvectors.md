---
title: Vectors and Matrices - Chapter 4 Eigenvalues and Eigenvectors
course: Part IA Vectors and Matrices
material_type: lecture notes
chapter: 4
source_file: Ch.4 Eigenvalues and Eigenvectors.pdf
drive_file_id: 1u6v1qK4liyDt8u40qnzJ_DjJnNAgfXE6
source_url: https://drive.google.com/file/d/1u6v1qK4liyDt8u40qnzJ_DjJnNAgfXE6/view
source_pages: 5
tags: [lecture, vectors-and-matrices]
---

# Vectors and Matrices — Chapter 4: Eigenvalues and Eigenvectors

> [!abstract] Overview
> An eigenvector of $T$ is a non-zero vector that $T$ only rescales. For a matrix $A$, the eigenvalues are the roots of the characteristic polynomial $\chi_A(t)=\det(A-tI)$; their sum is $\operatorname{tr}A$ and their product is $\det A$, and for real $A$ the non-real ones come in conjugate pairs. Triangular and diagonal matrices show their eigenvalues on the diagonal.
> Prerequisite: [[Vectors and Matrices - Chapter 3 Matrices]] (determinants, trace, kernels).

## Results index

| Result | Statement in brief | Page |
| --- | --- | --- |
| [[#Definition — Eigenvector and eigenvalue]] | $T(\mathbf v)=\lambda\mathbf v$, $\mathbf v\ne\mathbf 0$ | 1 |
| [[#Definition — Characteristic polynomial]] | $\chi_A(t)=\det(A-tI)$; eigenvalues are its roots | 1 |
| [[#Definition — Root and multiplicity]] | $(t-\lambda)^k\mid p$ but $(t-\lambda)^{k+1}\nmid p$ | 1 |
| [[#Proposition — Trace and determinant from eigenvalues]] | $\operatorname{tr}A=\sum\lambda_j$, $\det A=\prod\lambda_j$; conjugate pairs for real $A$ | 2–4 |
| [[#Triangular and diagonal matrices]] | eigenvalues are the diagonal entries | 4–5 |
| [[#Example — a complex matrix with real eigenvalues]] | $\begin{pmatrix}2&i\\-i&2\end{pmatrix}$: $\lambda=1,3$ | 5 |

## 4.1 Eigenvalues and the characteristic polynomial

### Definition — Eigenvector and eigenvalue

Let $T:V\to V$ be a linear map on a vector space over $\mathbb F$. A non-zero vector $\mathbf v\in V$ is an **eigenvector** if
$$T(\mathbf v)=\lambda\mathbf v$$
for some $\lambda\in\mathbb F$, called the **eigenvalue**.

**Remarks.**
- $\mathbf v$ must be non-zero (otherwise the equation is satisfied for every scalar).
- $\lambda$ may be $0$ (in that case $\mathbf v\in\ker T$).

For a matrix $A\in\mathbb F^{n\times n}$ ($=\operatorname{Mat}_{n\times n}(\mathbb F)$),
$$A\mathbf v=\lambda\mathbf v\iff(A-\lambda I)\mathbf v=\mathbf 0.$$
A non-zero solution exists $\iff$ $A-\lambda I$ is singular $\iff$ $\det(A-\lambda I)=0$.

### Definition — Characteristic polynomial

The **characteristic polynomial** of $A$ is
$$\chi_A(t):=\det(A-tI),$$
and the **characteristic equation** is $\chi_A(t)=0$. To find the eigenvectors of $A$ for an eigenvalue $\lambda$, solve $(A-\lambda I)\mathbf v=\mathbf 0$.

### 4.1.1 Roots, trace and determinant

### Definition — Root and multiplicity

For a polynomial $p(t)$:
- a **root** is $\lambda\in\mathbb F$ with $p(\lambda)=0$;
- its **multiplicity** is the $k\in\mathbb N$ such that $(t-\lambda)^k\mid p(t)$ but $(t-\lambda)^{k+1}\nmid p(t)$.

**Remark.** For $A=(A_{ij})$,
$$A-tI=\begin{pmatrix}A_{11}-t&A_{12}&\cdots&A_{1n}\\A_{21}&A_{22}-t&&\vdots\\\vdots&&\ddots&\\A_{n1}&\cdots&&A_{nn}-t\end{pmatrix}.$$
In $\det(A-tI)$, the only term of degree $n$ in $t$ comes from the product of the $n$ diagonal terms $-t$, so the leading coefficient is $(-1)^n$. By the [[Fundamental Theorem of Algebra]],
$$\chi_A(t)=\prod_{j=1}^n(\lambda_j-t),$$
with $\lambda_1,\dots,\lambda_n\in\mathbb C$ listed with multiplicity.

### Proposition — Trace and determinant from eigenvalues

Let $A$ be an $n\times n$ real or complex matrix with complex eigenvalues $\lambda_1,\dots,\lambda_n$ (with multiplicity). Then
$$\operatorname{tr}A=\sum_{j=1}^n\lambda_j,\qquad\det A=\prod_{j=1}^n\lambda_j.$$
If $A$ is real, its non-real eigenvalues occur in conjugate pairs.

**Proof.** Throughout, $\chi_A(t)=\det(A-tI)=\prod_{j=1}^n(\lambda_j-t)$.

*Example, $n=2$.* For $A=\begin{pmatrix}A_{11}&A_{12}\\A_{21}&A_{22}\end{pmatrix}$,
$$\begin{aligned}
\det(A-tI)&=(A_{11}-t)(A_{22}-t)-A_{21}A_{12}\\
&=t^2-\underbrace{(A_{11}+A_{22})}_{\operatorname{tr}A}t+\underbrace{(A_{11}A_{22}-A_{12}A_{21})}_{\det A},
\end{aligned}$$
while $(\lambda_1-t)(\lambda_2-t)=\lambda_1\lambda_2-(\lambda_1+\lambda_2)t+t^2$. Comparing coefficients, $\operatorname{tr}A=\lambda_1+\lambda_2$ and $\det A=\lambda_1\lambda_2$.

*Trace (general $n$).* In $A-tI$ the diagonal entries are $A_{ii}-t$, giving the diagonal product $(A_{11}-t)(A_{22}-t)\cdots(A_{nn}-t)$ in the determinant expansion; no other term of the expansion has degree $n-1$ in $t$. To obtain a term of degree $n-1$, pick $A_{11}$ and $(-t)$ from all other factors, or $A_{22}$ and $(-t)$ from all others, and so on:
$$(A_{11}+A_{22}+\dots+A_{nn})(-t)^{n-1}=(-1)^{n-1}\operatorname{tr}A\,t^{n-1}.\tag{1}$$
Similarly, in $\prod_{j=1}^n(\lambda_j-t)=(\lambda_1-t)(\lambda_2-t)\cdots(\lambda_n-t)$, the term in $t^{n-1}$ has coefficient
$$(-1)^{n-1}(\lambda_1+\dots+\lambda_n).\tag{2}$$
Comparing (1) and (2), $\operatorname{tr}A=\sum_{j=1}^n\lambda_j$.

*Determinant.*
$$\det A=\det(A-0I)=\chi_A(0)=\prod_{j=1}^n(\lambda_j-0)=\prod_{j=1}^n\lambda_j.$$

*$A$ real.* Then $\chi_A$ has real coefficients, so $\chi_A(\bar t)=\overline{\chi_A(t)}$, and $\chi_A(\lambda)=0\Rightarrow\chi_A(\bar\lambda)=0$. With multiplicities: write $\chi_A(t)=(t-\lambda)^kq(t)$ with $q(\lambda)\ne0$, so $\lambda$ has multiplicity $k$. Then
$$\chi_A(t)=\overline{\chi_A(\bar t)}=(t-\bar\lambda)^k\,\overline{q(\bar t)},$$
and at $t=\bar\lambda$ the second factor is $\overline{q(\lambda)}\ne0$, so $\bar\lambda$ also has multiplicity $k$. For eigenvectors: $A\mathbf v=\lambda\mathbf v$ gives $A\bar{\mathbf v}=\bar\lambda\bar{\mathbf v}$, since $\bar A=A$.

> [!note] Explanation
> Why no other term has degree $n-1$: any other term of the Leibniz expansion leaves out at least two diagonal entries, so it contains at most $n-2$ factors of the form $(A_{ii}-t)$ and has degree at most $n-2$ in $t$.

### 4.1.2 First examples

### Triangular and diagonal matrices

If $A$ is upper triangular, then $A-tI$ is also upper triangular, so
$$\chi_A(t)=\det\begin{pmatrix}A_{11}-t&A_{12}&\cdots&A_{1n}\\0&A_{22}-t&&\vdots\\\vdots&&\ddots&\\0&\cdots&&A_{nn}-t\end{pmatrix}=\prod_{j=1}^n(A_{jj}-t).$$
So the diagonal entries of $A$ are its eigenvalues, with possible repetitions.

For a diagonal matrix $D=\operatorname{diag}(d_1,\dots,d_n)$, the equation $(D-\lambda I)\mathbf v=\mathbf 0$ reads
$$(d_j-\lambda)v_j=0\qquad\text{for every }j,$$
so the solutions span $\{\mathbf e_j:d_j=\lambda\}$.

### Example — a complex matrix with real eigenvalues

$$A=\begin{pmatrix}2&i\\-i&2\end{pmatrix},\qquad\chi_A(t)=\det(A-tI)=\det\begin{pmatrix}2-t&i\\-i&2-t\end{pmatrix}=(2-t)^2-1=(t-1)(t-3).$$
So $A\mathbf v_1=\lambda_1\mathbf v_1$ with $\lambda_1=1$, and $A\mathbf v_2=\lambda_2\mathbf v_2$ with $\lambda_2=3$.
- $A\mathbf v_1=\mathbf v_1\iff(A-I)\mathbf v_1=\mathbf 0$, i.e. $\begin{pmatrix}1&i\\-i&1\end{pmatrix}\mathbf v_1=\mathbf 0$, so $\mathbf v_1=\alpha\begin{pmatrix}1\\i\end{pmatrix}$.
- $A\mathbf v_2=3\mathbf v_2\iff\mathbf v_2=\beta\begin{pmatrix}1\\-i\end{pmatrix}$.

> [!note] Explanation
> $A$ is Hermitian ($A^\dagger=A$), which is why its eigenvalues come out real even though its entries are complex. Check: $\operatorname{tr}A=4=1+3$ and $\det A=4-1=3=1\cdot3$, as the Proposition predicts.
