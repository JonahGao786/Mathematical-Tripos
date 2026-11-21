---
title: Vectors and Matrices - Chapter 4 Eigenvalues and Eigenvectors
course: Part IA Vectors and Matrices
material_type: lecture notes
chapter: 4
source_file: Ch.4 Eigenvalues and Eigenvectors.pdf
drive_file_id: 1u6v1qK4liyDt8u40qnzJ_DjJnNAgfXE6
source_url: https://drive.google.com/file/d/1u6v1qK4liyDt8u40qnzJ_DjJnNAgfXE6/view
source_pages: 14
tags: [lecture, vectors-and-matrices]
---

# Vectors and Matrices — Chapter 4: Eigenvalues and Eigenvectors

> [!abstract] Overview
> An eigenvector of $T$ is a non-zero vector that $T$ only rescales. For a matrix $A$, the eigenvalues are the roots of the characteristic polynomial $\chi_A(t)=\det(A-tI)$; their sum is $\operatorname{tr}A$ and their product is $\det A$, and for real $A$ the non-real ones come in conjugate pairs. Triangular and diagonal matrices show their eigenvalues on the diagonal. Then change of basis: a map with matrix $A$ in one basis has matrix $P^{-1}AP$ in another, which leads to similar matrices. Then eigenspaces $E_\lambda$, algebraic and geometric multiplicities $M_\lambda\ge m_\lambda$, and the independence of eigenvectors for distinct eigenvalues. Finally diagonalisation: $A$ is diagonalisable iff $\chi_A$ splits and $m_\lambda=M_\lambda$ for every eigenvalue.
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
| [[#Definition — Change of basis matrix]] | columns $\mathbf p_j$; $[\mathbf v]_{\mathcal E}=P[\mathbf v]_{\mathcal P}$; $B=P^{-1}AP$ | 6–7 |
| [[#Change between two arbitrary bases]] | $[\mathbf v]_{\mathcal B}=P[\mathbf v]_{\mathcal C}$, $P=S_{\mathcal B}^{-1}S_{\mathcal C}$, $A_{\mathcal C}=P^{-1}A_{\mathcal B}P$ | 8–9 |
| [[#Definition — Similar matrices]] | $B=P^{-1}AP$, $P$ invertible | 9 |
| [[#Proposition — Similarity is an equivalence relation]] | reflexive, symmetric, transitive | 9 |
| [[#Definition — Eigenspace]] | $E_\lambda=\ker(A-\lambda I)$ | 10 |
| [[#Definition — Algebraic and geometric multiplicity]] | $M_\lambda$: root multiplicity in $\chi_A$; $m_\lambda=\dim E_\lambda=n-\operatorname{rank}(A-\lambda I)$ | 10 |
| [[#Proposition — Quantities preserved by similarity]] | same $\chi$, trace, det, $M_\lambda$, $m_\lambda$; converse false ($I_2$ vs shear) | 10–11 |
| [[#Proposition — Geometric multiplicity is at most algebraic multiplicity]] | $1\le m_\lambda\le M_\lambda$ | 11 |
| [[#Definition — Defect]] | $\Delta_\lambda=M_\lambda-m_\lambda\ge0$ | 11 |
| [[#Theorem — Eigenvectors for distinct eigenvalues are independent]] | bases of distinct eigenspaces together are independent | 11–12 |
| [[#4.3.2 Examples and geometric interpretations]] | $\Delta=0$, $\Delta_{-2}=1$, $\Delta_4=2$ examples | 12–13 |
| [[#Proposition — Diagonalisable matrices]] | basis of eigenvectors $\iff P^{-1}AP=D$ | 14 |
| [[#Theorem — Criterion for diagonalisation]] | $\chi_A$ splits and $m_\lambda=M_\lambda$ for all $\lambda$ | 14 |

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

## 4.2 Similarity and change of basis

### Definition — Change of basis matrix

Let $T$ be a linear map represented by $A$ in the standard basis $\mathcal E=\{\mathbf e_1,\dots,\mathbf e_n\}$, and choose a new basis $\mathcal P=\{\mathbf p_1,\dots,\mathbf p_n\}$. The **change of basis matrix** $P$ has as its columns the coordinates of the new basis vectors in the original basis:
$$\mathbf p_j=\sum_{i=1}^nP_{ij}\mathbf e_i,\qquad P=\begin{pmatrix}|&|&&|\\\mathbf p_1&\mathbf p_2&\cdots&\mathbf p_n\\|&|&&|\end{pmatrix},\qquad(P)_{ij}=P_{ij}.\tag{$*$}$$
Conversely, $\mathbf e_j=\sum_i(P^{-1})_{ij}\mathbf p_i$.

Write a vector $\mathbf v$ in both bases:
$$\mathbf v=\underbrace{\sum_{i=1}^nx_i\mathbf e_i}_{\text{basis }\mathcal E}=\underbrace{\sum_{j=1}^ny_j\mathbf p_j}_{\text{basis }\mathcal P}\overset{(*)}=\sum_{i=1}^n\Big(\sum_{j=1}^nP_{ij}y_j\Big)\mathbf e_i.$$
Comparing coefficients in $\mathcal E$,
$$\mathbf x=P\mathbf y\iff\mathbf y=P^{-1}\mathbf x,\qquad\text{where }\mathbf x=[\mathbf v]_{\mathcal E},\ \mathbf y=[\mathbf v]_{\mathcal P}.$$
So $P$ converts **new coordinates to original coordinates**, and $P^{-1}$ converts **original to new**.

> [!note] Explanation
> The formula for $\mathbf e_j$: substituting $(*)$, $\sum_i(P^{-1})_{ij}\mathbf p_i=\sum_k\big(\sum_iP_{ki}(P^{-1})_{ij}\big)\mathbf e_k=\sum_k(PP^{-1})_{kj}\mathbf e_k=\mathbf e_j$. $P$ is invertible because its columns $\mathbf p_1,\dots,\mathbf p_n$ form a basis.

**Example.** $\mathbf v=(3,1)^T$, with new basis $\mathbf p_1=(1,1)^T=\mathbf e_1+\mathbf e_2$ and $\mathbf p_2=(1,-1)^T=\mathbf e_1-\mathbf e_2$.

```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[>=latex,scale=0.9]
  \draw[->] (-0.5,0) -- (3.6,0); \draw[->] (0,-0.5) -- (0,2.2);
  \draw[->,very thick,red] (0,0) -- (1,0) node[below] {$e_1$};
  \draw[->,very thick,red] (0,0) -- (0,1) node[left] {$e_2$};
  \draw[->,thick,blue] (0,0) -- (3,1) node[above] {$v$};
  \node at (1.8,-1.9) {original basis $\mathcal{E}$};
  \begin{scope}[xshift=5.5cm]
  \draw[->] (-0.5,0) -- (3.6,0); \draw[->] (0,-1.4) -- (0,2.2);
  \draw[->,very thick,red] (0,0) -- (1,1) node[above left] {$p_1$};
  \draw[->,very thick,red] (0,0) -- (1,-1) node[below right] {$p_2$};
  \draw[->,thick,blue] (0,0) -- (3,1) node[above] {$v$};
  \node at (1.8,-1.9) {new basis $\mathcal{P}$};
  \end{scope}
\end{tikzpicture}
\end{document}
```
*The same vector $\mathbf v$ against the standard basis and against the new basis $\mathbf p_1,\mathbf p_2$.*

Here
$$P=\begin{pmatrix}1&1\\1&-1\end{pmatrix},\qquad\mathbf v=3\mathbf e_1+\mathbf e_2=2\mathbf p_1+\mathbf p_2,\qquad\underbrace{\begin{pmatrix}3\\1\end{pmatrix}}_{[\mathbf v]_{\mathcal E}}=P\underbrace{\begin{pmatrix}2\\1\end{pmatrix}}_{[\mathbf v]_{\mathcal P}}.$$

**The matrix of $T$ in the new basis.** To apply $T$ when the input is in new coordinates, convert to original coordinates, apply $A$, and convert back:
$$\mathbf y\ \xrightarrow{\;P\;}\ \mathbf x=P\mathbf y\ \xrightarrow{\;A\;}\ A\mathbf x=AP\mathbf y\ \xrightarrow{\;P^{-1}\;}\ P^{-1}AP\mathbf y.$$
So
$$[T(\mathbf v)]_{\mathcal P}=B[\mathbf v]_{\mathcal P},\qquad B=P^{-1}AP\iff PB=AP.$$
$A$ and $B$ describe the same map; the $j$th column of $B$ contains the coefficients of $T(\mathbf p_j)$ in the new basis.

### Change between two arbitrary bases

Let $\mathcal B=\{\mathbf b_1,\dots,\mathbf b_n\}$ and $\mathcal C=\{\mathbf c_1,\dots,\mathbf c_n\}$ be bases. The change of basis matrix is defined by
$$\mathbf c_j=\sum_{i=1}^nP_{ij}\mathbf b_i,\qquad P=\begin{pmatrix}|&&|\\{[\mathbf c_1]_{\mathcal B}}&\cdots&{[\mathbf c_n]_{\mathcal B}}\\|&&|\end{pmatrix}:$$
the columns of $P$ are the coordinates of the $\mathbf c_j$ relative to $\mathcal B$. For $\mathbf v\in V$,
$$\mathbf v=\sum_{j=1}^ny_j\mathbf c_j=\sum_{i=1}^n\Big(\sum_{j=1}^nP_{ij}y_j\Big)\mathbf b_i,$$
so
$$[\mathbf v]_{\mathcal B}=P[\mathbf v]_{\mathcal C},\qquad[\mathbf v]_{\mathcal C}=P^{-1}[\mathbf v]_{\mathcal B}.\tag{2}$$

Now represent $\mathcal B$ and $\mathcal C$ in terms of the standard basis $\mathcal E$:
$$S_{\mathcal B}=\begin{pmatrix}|&&|\\\mathbf b_1&\cdots&\mathbf b_n\\|&&|\end{pmatrix},\qquad S_{\mathcal C}=\begin{pmatrix}|&&|\\\mathbf c_1&\cdots&\mathbf c_n\\|&&|\end{pmatrix},\qquad S_{\mathcal B}[\mathbf v]_{\mathcal B}=S_{\mathcal C}[\mathbf v]_{\mathcal C}.\tag{1}$$
Comparing (1) and (2),
$$P=S_{\mathcal B}^{-1}S_{\mathcal C}.$$

> [!note] Explanation
> Both sides of (1) equal $\mathbf v$ in standard coordinates. Substituting (2) into (1) gives $S_{\mathcal B}P[\mathbf v]_{\mathcal C}=S_{\mathcal C}[\mathbf v]_{\mathcal C}$ for every $\mathbf v$, so $S_{\mathcal B}P=S_{\mathcal C}$.

**Example.**
$$\mathcal B=\Big(\underbrace{\begin{pmatrix}1\\1\end{pmatrix}}_{\mathbf b_1},\underbrace{\begin{pmatrix}1\\-1\end{pmatrix}}_{\mathbf b_2}\Big),\qquad\mathcal C=\Big(\underbrace{\begin{pmatrix}2\\0\end{pmatrix}}_{\mathbf c_1},\underbrace{\begin{pmatrix}1\\3\end{pmatrix}}_{\mathbf c_2}\Big).$$
Then $\mathbf c_1=\mathbf b_1+\mathbf b_2$ and $\mathbf c_2=2\mathbf b_1-\mathbf b_2$, so
$$P=\begin{pmatrix}1&2\\1&-1\end{pmatrix}.$$
Take $\mathbf v=(3,3)^T=\mathbf c_1+\mathbf c_2=3\mathbf b_1$: $\mathbf v$ has coordinates $(1,1)^T$ in $\mathcal C$ and $(3,0)^T$ in $\mathcal B$. Indeed
$$P\begin{pmatrix}1\\1\end{pmatrix}=\begin{pmatrix}3\\0\end{pmatrix},$$
and in standard coordinates $\mathbf v=(3,3)^T$.

**Matrices of a map.** If $T:V\to V$ is represented by $A_{\mathcal B}$ in $\mathcal B$ and by $A_{\mathcal C}$ in $\mathcal C$, then
$$[T(\mathbf v)]_{\mathcal C}=P^{-1}A_{\mathcal B}P[\mathbf v]_{\mathcal C},\qquad A_{\mathcal C}=P^{-1}A_{\mathcal B}P.$$

### Definition — Similar matrices

$A,B\in\mathbb F^{n\times n}$ are **similar** over $\mathbb F$ if $B=P^{-1}AP$ for some invertible $P\in\mathbb F^{n\times n}$.

### Proposition — Similarity is an equivalence relation

Similarity of matrices is reflexive, symmetric and transitive.

**Proof.**
- *Reflexivity:* $I^{-1}AI=A$.
- *Symmetry:* if $A$ is similar to $B$, then $B=P^{-1}AP$, so $A=PBP^{-1}$. With $Q=P^{-1}$ this is $A=Q^{-1}BQ$ ($P,Q$ invertible).
- *Transitivity:* if $A$ is similar to $B$, $B=P^{-1}AP$; if $B$ is similar to $C$, $C=Q^{-1}BQ$. Then
$$C=Q^{-1}BQ=\underbrace{Q^{-1}P^{-1}}_{(PQ)^{-1}}APQ=(PQ)^{-1}A(PQ).$$

## 4.3 Eigenspaces, multiplicity and independence

### Definition — Eigenspace

For $\lambda\in\mathbb F$ an eigenvalue of $A\in\mathbb F^{n\times n}$, define the **eigenspace** associated with $\lambda$:
$$E_\lambda:=\ker(A-\lambda I)\subseteq\mathbb F^n.$$
The non-zero elements of $E_\lambda$ are the eigenvectors of $\lambda$.

### Definition — Algebraic and geometric multiplicity

- The **algebraic multiplicity** $M_\lambda$ of $\lambda$ is the multiplicity of $\lambda$ as a root of $\chi_A$.
- The **geometric multiplicity** of $\lambda$ is the dimension of $E_\lambda$:
$$m_\lambda:=\dim E_\lambda=n-\operatorname{rank}(A-\lambda I).$$

> [!note] Explanation
> The second equality is the rank–nullity theorem applied to $A-\lambda I$: $\dim\ker+\operatorname{rank}=n$.

### Proposition — Quantities preserved by similarity

Similar matrices have the same characteristic polynomial, trace and determinant. For each eigenvalue, they also have the same algebraic and geometric multiplicities.

**Proof (idea).** If $B=P^{-1}AP$, then
$$B-tI=P^{-1}AP-tP^{-1}P=P^{-1}(A-tI)P,$$
so
$$\underbrace{\det(B-tI)}_{\chi_B(t)}=\det\big(P^{-1}(A-tI)P\big)=\det(P^{-1})\underbrace{\det(A-tI)}_{\chi_A(t)}\det(P)=\chi_A(t).$$

> [!note] Explanation
> The rest follows from $\chi_B=\chi_A$ and $B-\lambda I=P^{-1}(A-\lambda I)P$. The trace and determinant are, up to sign, coefficients of $\chi$ (they are the sum and product of its roots, by the [[#Proposition — Trace and determinant from eigenvalues|earlier proposition]]), and the algebraic multiplicities are multiplicities of its roots. For the geometric multiplicity: $(B-\lambda I)\mathbf v=\mathbf 0\iff(A-\lambda I)P\mathbf v=\mathbf 0$, so $\mathbf v\mapsto P\mathbf v$ maps $E_\lambda(B)$ bijectively onto $E_\lambda(A)$ ($P$ is invertible), and the two eigenspaces have the same dimension.

**Remark.** The converse is false: equality of the characteristic polynomials does not imply similarity.

**Example ($\mathbb R^{2\times2}$): identity and shear.**
$$I_2=\begin{pmatrix}1&0\\0&1\end{pmatrix},\qquad S_\lambda=\begin{pmatrix}1&\lambda\\0&1\end{pmatrix},\quad\lambda\ne0.$$
Both have characteristic polynomial $(1-t)^2$, but they are not similar: $P^{-1}I_2P=M\Rightarrow M=I_2$ for any invertible $P$.

**Remark.** The sum of the algebraic multiplicities is $n$ over $\mathbb C$, by the [[Fundamental Theorem of Algebra]]; also over $\mathbb R$ if all roots of $\chi_A$ are real.

### Proposition — Geometric multiplicity is at most algebraic multiplicity

For every eigenvalue $\lambda\in\mathbb F$,
$$1\le m_\lambda\le M_\lambda.$$

### Definition — Defect

The **defect** of an eigenvalue $\lambda$ is
$$\Delta_\lambda:=M_\lambda-m_\lambda\ge0.$$
An eigenvalue with algebraic multiplicity $1$ necessarily has a one-dimensional eigenspace.

### 4.3.1 Independent eigenvectors from different eigenspaces

### Theorem — Eigenvectors for distinct eigenvalues are independent

Eigenvectors corresponding to distinct eigenvalues are linearly independent. More generally, the union of a basis from each of several distinct eigenspaces is linearly independent.

**Proof (idea, two eigenvectors).** Let $\lambda_1\ne\lambda_2$, and let $\mathbf v_1,\mathbf v_2\ne\mathbf 0$ be eigenvectors associated to $\lambda_1,\lambda_2$ respectively. Suppose $\mathbf v_1,\mathbf v_2$ are linearly dependent:
$$a_1\mathbf v_1+a_2\mathbf v_2=\mathbf 0\qquad\text{for some }a_1,a_2\text{ not both }0.$$
Then $a_2\ne0$ (otherwise $a_1\mathbf v_1=\mathbf 0$ with $a_1\ne0$). Apply $A-\lambda_1I$:
$$(A-\lambda_1I)(a_1\mathbf v_1+a_2\mathbf v_2)=a_2(\lambda_2-\lambda_1)\mathbf v_2=\mathbf 0\ \Rightarrow\ \lambda_1=\lambda_2,$$
a contradiction.

> [!note] Explanation
> For $k$ eigenvectors with distinct eigenvalues, the same idea works by induction on $k$. Take a shortest dependence $\sum_ia_i\mathbf v_i=\mathbf 0$ with every $a_i\ne0$ and apply $A-\lambda_1I$. This kills the $\mathbf v_1$ term and leaves $\sum_{i\ge2}a_i(\lambda_i-\lambda_1)\mathbf v_i=\mathbf 0$, a shorter dependence with non-zero coefficients, which contradicts minimality. For the version with bases: in a dependence among the basis vectors, group the terms by eigenspace. Each group is a vector in $E_{\lambda_i}$, and these vectors sum to $\mathbf 0$. By the first part, every group is $\mathbf 0$, and then each group's coefficients vanish because they come from a basis.

Consequently,
$$\dim\operatorname{span}(\text{all eigenvectors})=\sum_\lambda m_\lambda,$$
and each vector in the span has a unique decomposition as a sum of vectors from the distinct eigenspaces.

### 4.3.2 Examples and geometric interpretations

**Example.**
$$A=\begin{pmatrix}-2&2&-3\\2&1&-6\\-1&-2&0\end{pmatrix},\qquad\chi_A(t)=\det(A-tI)=(5-t)(t+3)^2.$$
- $\lambda=5$: $M_5=1=m_5$. Solving $(A-5I)\mathbf v=\mathbf 0$,
$$\begin{pmatrix}-7&2&-3\\2&-4&-6\\-1&-2&-5\end{pmatrix}\begin{pmatrix}x\\y\\z\end{pmatrix}=\begin{pmatrix}0\\0\\0\end{pmatrix}\ \Rightarrow\ \begin{cases}y=2x,\\x=-z,\end{cases}\qquad E_5=\operatorname{span}\{(1,2,-1)^{\mathsf T}\}.$$
- $\lambda=-3$: $M_{-3}=2$, so $m_{-3}$ is $1$ or $2$. Solving
$$\begin{pmatrix}1&2&-3\\2&4&-6\\-1&-2&3\end{pmatrix}\begin{pmatrix}x\\y\\z\end{pmatrix}=\begin{pmatrix}0\\0\\0\end{pmatrix}\ \Rightarrow\ x+2y-3z=0,$$
$$E_{-3}=\operatorname{span}\{(3,0,1)^{\mathsf T},(-2,1,0)^{\mathsf T}\},$$
so $m_{-3}=2$: the eigenspace is the plane $x+2y-3z=0$.

**Example.**
$$B=\begin{pmatrix}-3&-1&1\\-1&-3&1\\-2&-2&0\end{pmatrix},\qquad\chi_B(t)=-(t+2)^3.$$
For $\lambda=-2$, every row of $B+2I$ reduces to $z=x+y$, so
$$E_{-2}=\operatorname{span}\{(1,0,1)^{\mathsf T},(0,1,1)^{\mathsf T}\},\qquad M_{-2}=3,\ m_{-2}=2,\ \Delta_{-2}=1.$$

**Example.**
$$J=\begin{pmatrix}4&1&0\\0&4&1\\0&0&4\end{pmatrix},\qquad\chi_J(t)=(4-t)^3.$$
$(J-4I)\mathbf v=\mathbf 0\Rightarrow y=0,\ z=0$, so $E_4=\operatorname{span}\{\mathbf e_1\}$ and
$$M_4=3,\qquad m_4=1,\qquad\Delta_4=2.$$

## 4.4 Diagonalisation

### Proposition — Diagonalisable matrices

For $A\in\mathbb F^{n\times n}$, the following are equivalent:
1. $\mathbb F^n$ has a basis of eigenvectors $\{\mathbf v_1,\dots,\mathbf v_n\}$ of $A$;
2. there is an invertible $P\in\mathbb F^{n\times n}$ such that $P^{-1}AP=D=\operatorname{diag}(\lambda_1,\dots,\lambda_n)$.

If these hold, $A$ is **diagonalisable** over $\mathbb F$.

**Remark.** In
$$D=\begin{pmatrix}\lambda_1&\cdots&0\\\vdots&\ddots&\vdots\\0&\cdots&\lambda_n\end{pmatrix},$$
$\lambda_1,\dots,\lambda_n$ are the eigenvalues of $A$. The order of the columns of $P$ must agree with the order of the corresponding eigenvalues in $D$.

> [!note] Explanation
> $P^{-1}AP=D\iff AP=PD$. The $j$th column of $AP$ is $A\mathbf v_j$ and the $j$th column of $PD$ is $\lambda_j\mathbf v_j$, where $\mathbf v_j$ is the $j$th column of $P$. So $P^{-1}AP=D$ says exactly that each column $\mathbf v_j$ is an eigenvector with eigenvalue $\lambda_j$. $P$ is invertible exactly when its columns form a basis.

### Theorem — Criterion for diagonalisation

A matrix $A\in\mathbb F^{n\times n}$ is diagonalisable over $\mathbb F$ if and only if $\chi_A$ splits into linear factors over $\mathbb F$ and $m_\lambda=M_\lambda$ for every eigenvalue $\lambda$.

**Remarks.**
- Over $\mathbb C$ the splitting condition is automatic; over $\mathbb R$ we need the roots to be real.
- If $A$ has $n$ distinct eigenvalues, then $A$ is diagonalisable.
- If a diagonalisable matrix $A$ has only one eigenvalue $\lambda$, then $A=\lambda I$.

> [!note] Explanation
> Why the criterion holds: by the [[#Theorem — Eigenvectors for distinct eigenvalues are independent|theorem above]], joining bases of the eigenspaces gives $\sum_\lambda m_\lambda$ independent eigenvectors. Also $\sum_\lambda m_\lambda\le\sum_\lambda M_\lambda\le n$, with equality throughout exactly when $\chi_A$ splits and $m_\lambda=M_\lambda$ for every $\lambda$. With $n$ distinct eigenvalues, every $M_\lambda=1$, which forces $m_\lambda=1$. With a single eigenvalue, $P^{-1}AP=\lambda I$ gives $A=P(\lambda I)P^{-1}=\lambda I$. So the shear $S_\lambda$ and $J$ above are not diagonalisable, and neither is $B$.
