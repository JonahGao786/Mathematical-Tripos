---
title: Groups - Chapter 8 Matrices
course: Part IA Groups
material_type: lecture notes
chapter: 8
source_file: Ch.8 Matrices.pdf
drive_file_id: 1XxBpA9U3bz8YfjiNl7RA1eBM7EG7LTjG
source_url: https://drive.google.com/file/d/1XxBpA9U3bz8YfjiNl7RA1eBM7EG7LTjG/view
source_pages: 3
tags: [lecture, groups]
---

# Groups — Chapter 8: Matrices

> [!abstract] Overview
> Invertible matrices form a group, the general linear group $GL_n(\mathbb R)$. The determinant is a homomorphism onto $\mathbb R^\times$, and its kernel is the special linear group $SL_n(\mathbb R)$. The isomorphism theorem gives $GL_n/SL_n\cong\mathbb R^\times$, and the same holds over $\mathbb C$. $GL_n(\mathbb R)$ acts on matrices by conjugation, and the orbit of a matrix representing a linear map consists exactly of its representations in all possible bases.
> Prerequisites: [[Groups - Chapter 3 Group Actions]] (actions, orbits); [[Groups - Chapter 6 Quotients]] (normal subgroups, isomorphism theorem); [[Vectors and Matrices - Chapter 3 Matrices]] (determinants).

## Results index

| Result | Statement in brief | Page |
| --- | --- | --- |
| [[#Lemma 8.1 — Invertible iff non-zero determinant]] | $A$ has an inverse iff $\det A\ne0$ | 1 |
| [[#Definition 8.2 — General linear group]] | $GL_n(\mathbb R)=\{A:\det A\ne0\}$ | 1 |
| [[#Lemma 8.3 — Determinant is a homomorphism]] | $\det(AB)=\det A\det B$; $\det:GL_n(\mathbb R)\to\mathbb R^\times$ | 1 |
| [[#Definition 8.4 — Special linear group]] | $SL_n(\mathbb R)=\ker(\det)$; $GL_n/SL_n\cong\mathbb R^\times$ | 2 |
| [[#Proposition 8.5 — Orbits under conjugation are changes of basis]] | $GL_n(\mathbb R)\cdot A$ = all matrices representing $\alpha$ | 2–3 |

## 8.1 The general and special linear groups

Let $M_n(\mathbb R)=\{n\times n\text{ matrices with entries in }\mathbb R\}$.
- Matrix multiplication is associative.
- The identity matrix $I=\begin{pmatrix}1&0&\cdots&0\\0&1&&\vdots\\\vdots&&\ddots&\\0&\cdots&&1\end{pmatrix}$ provides an identity.

But not all matrices have inverses. Recall:

### Lemma 8.1 — Invertible iff non-zero determinant

$A\in M_n(\mathbb R)$ has an inverse if and only if $\det A\ne0$. (See [[Vectors and Matrices - Chapter 3 Matrices#Invertibility and special matrices|Vectors and Matrices]].)

### Definition 8.2 — General linear group

$$GL_n(\mathbb R)=\{A\in M_n(\mathbb R):\det A\ne0\}.$$
This is a group with matrix multiplication and the identity matrix, called the **general linear group** (over $\mathbb R$ in dimension $n$).

### Lemma 8.3 — Determinant is a homomorphism

For $A,B\in M_n(\mathbb R)$,
$$\det(AB)=\det A\det B.$$
In other words,
$$\det:GL_n(\mathbb R)\to\mathbb R^\times=(\mathbb R\setminus\{0\},\times,1),\qquad A\mapsto\det A$$
is a group [[Homomorphisms and Isomorphisms|homomorphism]].

> [!note] Explanation
> Lemma 8.3 also shows that $GL_n(\mathbb R)$ is closed under products, since $\det(AB)=\det A\det B\ne0$. It is closed under inverses too, since $\det(A^{-1})=1/\det A\ne0$. That is what makes it a group.

### Definition 8.4 — Special linear group

$$SL_n(\mathbb R)=\{A\in M_n(\mathbb R):\det A=1\}=\ker(\det).$$
This is called the **special linear group** (over $\mathbb R$ in dimension $n$).

**Remark.** $SL_n(\mathbb R)\trianglelefteq GL_n(\mathbb R)$, as a kernel. Also
$$\det\begin{pmatrix}x_1&&&0\\&1&&\\&&\ddots&\\0&&&1\end{pmatrix}=x_1\in\mathbb R^\times,$$
so $\operatorname{Im}(\det)=\mathbb R^\times$. Then by the [[Groups - Chapter 6 Quotients#Theorem 6.5 — Isomorphism theorem|isomorphism theorem]],
$$GL_n(\mathbb R)/SL_n(\mathbb R)\cong\mathbb R^\times.$$

Everything above also works with $\mathbb R$ replaced by $\mathbb C$: we get, similarly, $GL_n(\mathbb C)$, $SL_n(\mathbb C)$ and
$$GL_n(\mathbb C)/SL_n(\mathbb C)\cong\mathbb C^\times.$$

## 8.2 Change of basis

There is a natural [[Groups - Chapter 3 Group Actions#Definition 3.1 — Group action|action]] by matrix conjugation:
$$GL_n(\mathbb R)\curvearrowright M_n(\mathbb R),\qquad P\cdot A=PAP^{-1}.$$

### Proposition 8.5 — Orbits under conjugation are changes of basis

Let $V$ be an $n$-dimensional vector space and $\alpha:V\to V$ a linear map. If $A\in M_n(\mathbb R)$ represents $\alpha$ in some basis, then the orbit
$$GL_n(\mathbb R)\cdot A=\{PAP^{-1}:P\in GL_n(\mathbb R)\}$$
consists of the matrix representations of $\alpha$ in all possible bases.

**Proof.** Recall that a basis $(\mathbf v_1,\dots,\mathbf v_n)$ for $V$ defines an isomorphism of vector spaces
$$\varphi:\mathbb R^n\to V,\qquad(\lambda_1,\dots,\lambda_n)\mapsto\sum_{i=1}^n\lambda_i\mathbf v_i.$$
The fact that $A$ represents $\alpha$ with respect to this basis means that the square

```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[>=latex]
  \node (A) at (0,1.6) {$R^n$}; \node (B) at (2.4,1.6) {$V$};
  \node (C) at (0,0) {$R^n$}; \node (D) at (2.4,0) {$V$};
  \draw[->] (A) -- node[above] {$\varphi$} (B);
  \draw[->] (C) -- node[below] {$\varphi$} (D);
  \draw[->] (A) -- node[left] {$A$} (C);
  \draw[->] (B) -- node[right] {$\alpha$} (D);
  \draw[->,blue] (1.45,0.95) arc (60:330:0.3);
\end{tikzpicture}
\end{document}
```
*The square commutes: going across by $\varphi$ then down by $\alpha$ is the same as going down by $A$ then across by $\varphi$.*

commutes, i.e.
$$A=\varphi^{-1}\circ\alpha\circ\varphi\iff\alpha=\varphi\circ A\circ\varphi^{-1}.$$

1. Suppose we have another basis $(\mathbf w_1,\dots,\mathbf w_n)$, corresponding to $\psi:\mathbb R^n\xrightarrow{\ \cong\ }V$. Say $B\in M_n(\mathbb R)$ represents $\alpha$ with respect to this basis, so $\alpha=\psi\circ B\circ\psi^{-1}$. Now $\varphi\circ A\circ\varphi^{-1}=\psi\circ B\circ\psi^{-1}$, so
$$B=\underbrace{(\psi^{-1}\circ\varphi)}_{\in GL_n(\mathbb R)}\circ A\circ(\psi^{-1}\circ\varphi)^{-1},$$
and $B$ is in the orbit of $A$.
2. Suppose we know $B$ is in the orbit of $A$: $B=PAP^{-1}$ with $P\in GL_n(\mathbb R)$. Set $\psi=\varphi\circ P^{-1}:\mathbb R^n\to V$. This defines a basis $(\mathbf u_i=\psi(\mathbf e_i))$ for $V$, and $B$ represents $\alpha$ with respect to that basis.

> [!note] Explanation
> In 1, $\psi^{-1}\circ\varphi$ is an invertible linear map $\mathbb R^n\to\mathbb R^n$, i.e. an invertible matrix. In 2, check: $\psi\circ B\circ\psi^{-1}=\varphi P^{-1}(PAP^{-1})P\varphi^{-1}=\varphi A\varphi^{-1}=\alpha$. Compare the change-of-basis formula $A_{\mathcal C}=P^{-1}A_{\mathcal B}P$ in [[Vectors and Matrices - Chapter 4 Eigenvalues and Eigenvectors#Change between two arbitrary bases|Vectors and Matrices]]: there $P$ is the change of basis matrix itself, here it is its inverse, which does not change the set of matrices obtained.
