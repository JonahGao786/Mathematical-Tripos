---
title: Groups - Chapter 8 Matrices
course: Part IA Groups
material_type: lecture notes
chapter: 8
source_file: Ch.8 Matrices.pdf
drive_file_id: 1XxBpA9U3bz8YfjiNl7RA1eBM7EG7LTjG
source_url: https://drive.google.com/file/d/1XxBpA9U3bz8YfjiNl7RA1eBM7EG7LTjG/view
source_pages: 12
tags: [lecture, groups]
---

# Groups — Chapter 8: Matrices

> [!abstract] Overview
> Invertible matrices form a group, the general linear group $GL_n(\mathbb R)$. The determinant is a homomorphism onto $\mathbb R^\times$, and its kernel is the special linear group $SL_n(\mathbb R)$. The isomorphism theorem gives $GL_n/SL_n\cong\mathbb R^\times$, and the same holds over $\mathbb C$. $GL_n(\mathbb R)$ acts on matrices by conjugation, and the orbit of a matrix representing a linear map consists exactly of its representations in all possible bases. The Möbius group is $GL_2(\mathbb C)$ modulo scalar matrices. The orthogonal group $O(n)$ of distance-preserving matrices is characterised by $A^{\mathsf T}A=I$; its determinant-one part is $SO(n)$, and reflections lie in $O(n)$ but not in $SO(n)$. Every orthogonal matrix is a product of at most $n$ reflections; hence $SO(2)$ and $SO(3)$ consist of rotations.
> Prerequisites: [[Groups - Chapter 3 Group Actions]] (actions, orbits); [[Groups - Chapter 4 The Möbius Group]]; [[Groups - Chapter 6 Quotients]] (normal subgroups, isomorphism theorem); [[Vectors and Matrices - Chapter 3 Matrices]] (determinants).

## Results index

| Result | Statement in brief | Page |
| --- | --- | --- |
| [[#Lemma 8.1 — Invertible iff non-zero determinant]] | $A$ has an inverse iff $\det A\ne0$ | 1 |
| [[#Definition 8.2 — General linear group]] | $GL_n(\mathbb R)=\{A:\det A\ne0\}$ | 1 |
| [[#Lemma 8.3 — Determinant is a homomorphism]] | $\det(AB)=\det A\det B$; $\det:GL_n(\mathbb R)\to\mathbb R^\times$ | 1 |
| [[#Definition 8.4 — Special linear group]] | $SL_n(\mathbb R)=\ker(\det)$; $GL_n/SL_n\cong\mathbb R^\times$ | 2 |
| [[#Proposition 8.5 — Orbits under conjugation are changes of basis]] | $GL_n(\mathbb R)\cdot A$ = all matrices representing $\alpha$ | 2–3 |
| [[#Proposition 8.6 — M is a quotient of GL_2(C)]] | $\mathcal M\cong GL_2(\mathbb C)/D$, $D$ = scalar matrices | 4 |
| [[#Definition 8.7 — Orthogonal group]] | $O(n)=\{A:\lVert A\mathbf v\rVert=\lVert\mathbf v\rVert\}$ | 5 |
| [[#Lemma 8.8 — Polarisation identity]] | $\mathbf u\cdot\mathbf v=\frac12(\lVert\mathbf u\rVert^2+\lVert\mathbf v\rVert^2-\lVert\mathbf u-\mathbf v\rVert^2)$ | 5 |
| [[#Lemma 8.9 — O(n) preserves the dot product]] | $A\in O(n)\iff A\mathbf x\cdot A\mathbf y=\mathbf x\cdot\mathbf y$ | 5 |
| [[#Lemma 8.10 — Characterisations of orthogonal matrices]] | $O(n)$ $\iff$ orthonormal columns $\iff A^{\mathsf T}A=I$; $\det A=\pm1$ | 6–7 |
| [[#Definition 8.11 — Special orthogonal group]] | $SO(n)=\ker\det$, index $2$ in $O(n)$ | 7 |
| [[#Definition 8.12 — Reflection]] | $S_{\mathbf v}(\mathbf x)=\mathbf x-2\frac{\mathbf x\cdot\mathbf v}{\lVert\mathbf v\rVert^2}\mathbf v$ | 7–8 |
| [[#Lemma 8.13 — Reflections are orthogonal involutions]] | $S_{\mathbf v}^2=I$, $S_{\mathbf v}\in O(n)$, $\det S_{\mathbf v}=-1$ | 8–9 |
| [[#Theorem 8.14 — Orthogonal matrices are products of reflections]] | every $A\in O(n)$ is a product of $\le n$ reflections | 9–10 |
| [[#Lemma 8.15 — O(2): reflections and rotations]] | $O(2)\setminus SO(2)$ reflections; $SO(2)$ rotations, $S_{\mathbf w}S_{\mathbf v}=\operatorname{Rot}(2\theta)$ | 10–11 |
| [[#Lemma 8.16 — SO(3) consists of rotations]] | $A\in SO(3)$ rotates about $\ell=P_{\mathbf u}\cap P_{\mathbf v}$ by $2\theta$ | 11–12 |

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

## 8.3 Möbius transformations revisited

Recall: composition in the [[Groups - Chapter 4 The Möbius Group#Theorem 4.3 — The Möbius group|Möbius group]] $\mathcal M$ looked similar to multiplication of $2\times2$ matrices.

### Proposition 8.6 — M is a quotient of GL_2(C)

Let
$$D=\Big\{\begin{pmatrix}\lambda&0\\0&\lambda\end{pmatrix}\in GL_2(\mathbb C)\Big\}\cong\mathbb C^\times,\qquad\begin{pmatrix}\lambda&0\\0&\lambda\end{pmatrix}\mapsto\lambda.$$
Then $D\trianglelefteq GL_2(\mathbb C)$ and $\mathcal M\cong GL_2(\mathbb C)/D$.

**Proof.** Let
$$\Phi:GL_2(\mathbb C)\to\mathcal M,\qquad\begin{pmatrix}a&b\\c&d\end{pmatrix}\longmapsto\Big(z\mapsto\frac{az+b}{cz+d}\Big).$$
- $\Phi$ is a homomorphism, by our [[Groups - Chapter 4 The Möbius Group#Composition of Möbius transformations|computation of composition]] in $\mathcal M$.
- $\Phi$ is surjective by construction.
- Kernel: $\begin{pmatrix}a&b\\c&d\end{pmatrix}\in\ker\Phi$ iff its image fixes $0$, $1$ and $\infty$, i.e. $b=c=0$ and $a=d$. So $\ker\Phi=D$.

The result then follows by the [[Groups - Chapter 6 Quotients#Theorem 6.5 — Isomorphism theorem|isomorphism theorem]].

> [!note] Explanation
> A Möbius map fixing three points is the identity (by the [[Groups - Chapter 4 The Möbius Group#Lemma 4.5 — Three-point lemma|three-point lemma]]). Fixing $\infty$ forces $c=0$, fixing $0$ forces $b=0$, and then fixing $1$ gives $\frac ad=1$. $D$ is normal because it is a kernel.

## 8.4 Orthogonal groups

Write $\|\cdot\|$ for the usual notion of length in $\mathbb R^n$:
$$\|\mathbf u\|=\sqrt{\sum_{i=1}^nu_i^2}.$$

### Definition 8.7 — Orthogonal group

The $n$-dimensional **orthogonal group** is the subgroup of $GL_n(\mathbb R)$ that preserves distance in $\mathbb R^n$:
$$O(n)=\{A\in GL_n(\mathbb R):\|A\mathbf v\|=\|\mathbf v\|\text{ for all }\mathbf v\in\mathbb R^n\}.$$

To think about distance, it is often useful to use the dot product $\mathbf u\cdot\mathbf v=\sum_{i=1}^nu_iv_i$.

### Lemma 8.8 — Polarisation identity

For $\mathbf u,\mathbf v\in\mathbb R^n$,
$$\mathbf u\cdot\mathbf v=\tfrac12\big(\|\mathbf u\|^2+\|\mathbf v\|^2-\|\mathbf u-\mathbf v\|^2\big).$$

**Proof.**
$$\|\mathbf u-\mathbf v\|^2=(\mathbf u-\mathbf v)\cdot(\mathbf u-\mathbf v)=\|\mathbf u\|^2-2(\mathbf u\cdot\mathbf v)+\|\mathbf v\|^2,$$
and rearrange.

### Lemma 8.9 — O(n) preserves the dot product

$$O(n)=\{A\in GL_n(\mathbb R):A\mathbf x\cdot A\mathbf y=\mathbf x\cdot\mathbf y\text{ for all }\mathbf x,\mathbf y\in\mathbb R^n\}.$$

**Proof.** ($\supseteq$) If $A\mathbf x\cdot A\mathbf y=\mathbf x\cdot\mathbf y$ for all $\mathbf x,\mathbf y\in\mathbb R^n$, then for any $\mathbf v\in\mathbb R^n$,
$$\|A\mathbf v\|^2=(A\mathbf v)\cdot(A\mathbf v)=\mathbf v\cdot\mathbf v=\|\mathbf v\|^2,$$
so $A\in O(n)$.

($\subseteq$) Suppose $A\in O(n)$. Then for any $\mathbf x,\mathbf y\in\mathbb R^n$,
$$\begin{aligned}
2(A\mathbf x)\cdot(A\mathbf y)&=\|A\mathbf x\|^2+\|A\mathbf y\|^2-\|A\mathbf x-A\mathbf y\|^2\\
&=\|\mathbf x\|^2+\|\mathbf y\|^2-\|\mathbf x-\mathbf y\|^2&&\text{by assumption}\\
&=2\,\mathbf x\cdot\mathbf y&&\text{by polarisation.}
\end{aligned}$$

> [!note] Explanation
> The middle step uses $A\mathbf x-A\mathbf y=A(\mathbf x-\mathbf y)$, so $\|A\mathbf x-A\mathbf y\|=\|\mathbf x-\mathbf y\|$ as well.

### Lemma 8.10 — Characterisations of orthogonal matrices

Let $A\in M_n(\mathbb R)$. The following are equivalent:
1. $A\in O(n)$;
2. the columns of $A$ form an orthonormal basis;
3. $A^{\mathsf T}A=I$.

**Proof.** (1) $\Rightarrow$ (2): Let $A=(a_{ij})$ and let $(\mathbf e_1,\dots,\mathbf e_n)$ be the standard basis for $\mathbb R^n$. The $i$th column of $A$ is $A\mathbf e_i$. Now
$$A\mathbf e_i\cdot A\mathbf e_j=\mathbf e_i\cdot\mathbf e_j=\begin{cases}1&i=j\\0&\text{otherwise}\end{cases}=\delta_{ij},$$
so the columns form an orthonormal basis.

(2) $\Rightarrow$ (3): As explained above, (2) means that $\delta_{ij}=A\mathbf e_i\cdot A\mathbf e_j$. Since $\mathbf u\cdot\mathbf v=\mathbf u^{\mathsf T}\mathbf v$, (2) means that
$$\delta_{ij}=(A\mathbf e_i)^{\mathsf T}(A\mathbf e_j)=\mathbf e_i^{\mathsf T}A^{\mathsf T}A\,\mathbf e_j.$$
Now for any $n\times n$ matrix $M$, $\mathbf e_i^{\mathsf T}M\mathbf e_j=M_{ij}$. So $A^{\mathsf T}A=I$.

(3) $\Rightarrow$ (1): Suppose $\mathbf u,\mathbf v\in\mathbb R^n$. Then
$$A\mathbf u\cdot A\mathbf v=(A\mathbf u)^{\mathsf T}(A\mathbf v)=\mathbf u^{\mathsf T}A^{\mathsf T}A\mathbf v=\mathbf u^{\mathsf T}\mathbf v=\mathbf u\cdot\mathbf v$$
by assumption (3).

> [!note] Explanation
> To finish (3) $\Rightarrow$ (1): $A^{\mathsf T}A=I$ shows that $A$ is invertible, with $A^{-1}=A^{\mathsf T}$, so $A\in GL_n(\mathbb R)$, and it preserves dot products, so $A\in O(n)$ by Lemma 8.9.

**Determinants.** Recall from Vectors and Matrices that $\det A^{\mathsf T}=\det A$ (see [[Vectors and Matrices - Chapter 3 Matrices#Rows and columns give the same determinant|here]]). So for any $A\in O(n)$,
$$1=\det I=\det(A^{\mathsf T}A)=\det(A^{\mathsf T})\det A=(\det A)^2,$$
so $\det A=\pm1$.

### Definition 8.11 — Special orthogonal group

$$SO(n)=O(n)\cap SL_n(\mathbb R)=\{A\in O(n):\det A=1\}.$$
This is called the **special orthogonal group** in dimension $n$.

**Remark.** $SO(n)=\ker\big(\det:O(n)\to\{\pm1\}\big)$. So $SO(n)\trianglelefteq O(n)$ and $|O(n):SO(n)|=2$.

> [!note] Explanation
> The index is $2$ because $\det$ is onto $\{\pm1\}$ (a reflection, below, has determinant $-1$), so by the isomorphism theorem $O(n)/SO(n)\cong\{\pm1\}$.

### Definition 8.12 — Reflection

Any $\mathbf v\in\mathbb R^n\setminus\{\mathbf 0\}$ defines an orthogonal plane
$$P_{\mathbf v}=\{\mathbf x\in\mathbb R^n:\mathbf x\cdot\mathbf v=0\}.$$
The **reflection** in $P_{\mathbf v}$ is defined to be
$$S_{\mathbf v}:\mathbf x\longmapsto\mathbf x-2\frac{\mathbf x\cdot\mathbf v}{\|\mathbf v\|^2}\mathbf v.$$

```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[>=latex]
  \draw (-2.6,-0.95) -- (2.6,0.95) node[right] {$P_v$};
  \draw[->,thick] (-1.6,-0.58) -- ++(-0.34,0.94) node[above] {$v$};
  \fill[blue] (-0.25,1.4) circle (1.3pt) node[left] {$x$};
  \fill[blue] (0.71,-1.24) circle (1.3pt) node[right] {$S_v(x)$};
  \draw[blue,dashed,->] (-0.25,1.4) -- (0.69,-1.19);
\end{tikzpicture}
\end{document}
```
*$S_{\mathbf v}$ moves $\mathbf x$ along $\mathbf v$, to the mirror image on the other side of the plane $P_{\mathbf v}$.*

**Remark.** We may replace $\mathbf v$ by $\frac{\mathbf v}{\|\mathbf v\|}$ and assume that $\|\mathbf v\|=1$. In this case
$$S_{\mathbf v}(\mathbf x)=\mathbf x-2(\mathbf x\cdot\mathbf v)\mathbf v.$$

### Lemma 8.13 — Reflections are orthogonal involutions

$S_{\mathbf v}^2=I$ and $S_{\mathbf v}\in O(n)$.

**Proof.** We may assume $\|\mathbf v\|=1$.
- $S_{\mathbf v}$ is linear in $\mathbf x$, so $S_{\mathbf v}\in M_n(\mathbb R)$.
- $S_{\mathbf v}^2$: we have $S_{\mathbf v}(\mathbf x)\cdot\mathbf v=(\mathbf x\cdot\mathbf v)-2(\mathbf x\cdot\mathbf v)(\mathbf v\cdot\mathbf v)=-\mathbf x\cdot\mathbf v$, so
$$S_{\mathbf v}^2(\mathbf x)=S_{\mathbf v}(\mathbf x)-2\big(S_{\mathbf v}(\mathbf x)\cdot\mathbf v\big)\mathbf v=\mathbf x-2(\mathbf x\cdot\mathbf v)\mathbf v+2(\mathbf x\cdot\mathbf v)\mathbf v=\mathbf x.$$
So $S_{\mathbf v}^2=I$.
- For any $\mathbf x\in\mathbb R^n$,
$$\|S_{\mathbf v}(\mathbf x)\|^2=\big(\mathbf x-2(\mathbf x\cdot\mathbf v)\mathbf v\big)\cdot\big(\mathbf x-2(\mathbf x\cdot\mathbf v)\mathbf v\big)=\|\mathbf x\|^2-4(\mathbf x\cdot\mathbf v)^2+4(\mathbf x\cdot\mathbf v)^2\underbrace{\|\mathbf v\|^2}_{=1}=\|\mathbf x\|^2,$$
so $S_{\mathbf v}\in O(n)$ ($S_{\mathbf v}$ is invertible since $S_{\mathbf v}^2=I$).

**Remark.** Let $\sigma_{\mathbf v}$ be the abstract linear map represented by $S_{\mathbf v}$ (with respect to the standard basis). Let $\|\mathbf v\|=1$ and pick any basis $(\mathbf v_2,\dots,\mathbf v_n)$ for $P_{\mathbf v}$. Then $(\mathbf v,\mathbf v_2,\dots,\mathbf v_n)$ is a basis for $\mathbb R^n$. With respect to this basis, $\sigma_{\mathbf v}$ is represented by
$$\begin{pmatrix}-1&&&0\\&1&&\\&&\ddots&\\0&&&1\end{pmatrix},$$
so $\det S_{\mathbf v}=-1$ and $S_{\mathbf v}\notin SO(n)$ (the determinant is invariant under change of basis).

> [!note] Explanation
> $\sigma_{\mathbf v}(\mathbf v)=\mathbf v-2\mathbf v=-\mathbf v$, and $\sigma_{\mathbf v}(\mathbf v_i)=\mathbf v_i$ since $\mathbf v_i\cdot\mathbf v=0$. Two matrices of the same map are conjugate, $B=PAP^{-1}$ ([[#Proposition 8.5 — Orbits under conjugation are changes of basis|Prop 8.5]]), so $\det B=\det A$.

**Remark.** We have $O(n)\le O(n+1)$, by acting trivially on the final coordinate:
$$\left(\begin{array}{c|c}A&\begin{matrix}0\\\vdots\\0\end{matrix}\\\hline0\ \cdots\ 0&1\end{array}\right)\in O(n+1)\quad\text{for }A\in O(n).$$

### Theorem 8.14 — Orthogonal matrices are products of reflections

Every $A\in O(n)$ is the product of at most $n$ reflections.

**Proof.** Induction on $n$.
- *Base case* $n=1$: $O(1)=\{\pm1\}\cong C_2$.
- *Inductive step:* assume the result for $O(n-1)$, and let $(\mathbf e_1,\dots,\mathbf e_n)$ be the standard basis for $\mathbb R^n$.
  - If $A\mathbf e_n\ne\mathbf e_n$, let $\mathbf v=\mathbf e_n-A\mathbf e_n\ne\mathbf 0$. Calculate: $S_{\mathbf v}(A\mathbf e_n)=\mathbf e_n$.

```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[>=latex]
  \draw[->] (-0.3,0) -- (3.2,0); \draw[->] (0,-0.3) -- (0,2);
  \draw[blue] (-0.3,-0.45) -- (1.6,2.4) node[right] {$P_v$};
  \draw[red,thick] (0,1.5) -- (1.4,0.55);
  \fill[red] (0,1.5) circle (1.3pt) node[left] {$e_n$};
  \fill[red] (1.4,0.55) circle (1.3pt) node[right] {$Ae_n$};
  \node[red] at (0.9,1.25) {\small$v$};
\end{tikzpicture}
\end{document}
```
*$\mathbf e_n$ and $A\mathbf e_n$ have the same length, so the reflection in the plane $P_{\mathbf v}$ perpendicular to $\mathbf v=\mathbf e_n-A\mathbf e_n$ swaps them.*

  As $S_{\mathbf v}A\in O(n)$, it preserves the dot product. It fixes $\mathbf e_n$, so it preserves $\mathbb R^{n-1}\times\{0\}\le\mathbb R^n$ (i.e. all vectors orthogonal to $\mathbf e_n$). By the induction hypothesis there exist $\mathbf v_1,\dots,\mathbf v_j\in\mathbb R^{n-1}$ ($j\le n-1$) such that
$$S_{\mathbf v}A=S_{\mathbf v_1}\cdots S_{\mathbf v_j}\quad\text{on }\mathbb R^{n-1}.$$
  Each $S_{\mathbf v_i}$ fixes $\mathbf e_n$ (because $\mathbf v_i\cdot\mathbf e_n=0$). So $S_{\mathbf v}A=S_{\mathbf v_1}\cdots S_{\mathbf v_j}$ on all of $\mathbb R^n$, i.e.
$$A=S_{\mathbf v}S_{\mathbf v_1}\cdots S_{\mathbf v_j}.$$
  - If $A\mathbf e_n=\mathbf e_n$: similar, skipping the first step.

> [!note] Explanation
> Why $S_{\mathbf v}(A\mathbf e_n)=\mathbf e_n$: with $\mathbf a=A\mathbf e_n$, we have $\|\mathbf a\|=\|\mathbf e_n\|=1$. So $(\mathbf a-\mathbf e_n)\cdot\mathbf v=-\|\mathbf v\|^2$ and $(\mathbf a+\mathbf e_n)\cdot\mathbf v=\|\mathbf e_n\|^2-\|\mathbf a\|^2=0$. Then
> $$S_{\mathbf v}(\mathbf a)=S_{\mathbf v}\Big(\tfrac{\mathbf a+\mathbf e_n}2\Big)+S_{\mathbf v}\Big(\tfrac{\mathbf a-\mathbf e_n}2\Big)=\tfrac{\mathbf a+\mathbf e_n}2-\tfrac{\mathbf a-\mathbf e_n}2=\mathbf e_n.$$
> Other points: an orthogonal map fixing $\mathbf e_n$ sends each $\mathbf x\perp\mathbf e_n$ to a vector still perpendicular to $\mathbf e_n$, since $S_{\mathbf v}A\mathbf x\cdot\mathbf e_n=S_{\mathbf v}A\mathbf x\cdot S_{\mathbf v}A\mathbf e_n=\mathbf x\cdot\mathbf e_n=0$. In the base case, $-1$ is the one reflection of $\mathbb R$ and $1$ is the empty product. Counting reflections: $1+j\le n$.

### Lemma 8.15 — O(2): reflections and rotations

Let $A\in O(2)$.
1. If $A\notin SO(2)$, then $A$ is a reflection.
2. If $A\in SO(2)$, then $A$ is a rotation about $0$.

**Proof.** By Theorem 8.14, $A=S_{\mathbf v_1}\cdots S_{\mathbf v_k}$ with $k\le2$. Recall $\det S_{\mathbf v}=-1$, so $\det A=(-1)^k$.
1. If $A\notin SO(2)$, then $k=1$.
2. If $A\in SO(2)$, then $k$ is even, so $A=I$ or $A=S_{\mathbf w}S_{\mathbf v}$ with $\|\mathbf w\|=\|\mathbf v\|=1$. Then
$$S_{\mathbf w}S_{\mathbf v}=\operatorname{Rot}_0(2\theta),\qquad\text{where }\mathbf v\cdot\mathbf w=\cos(\pi-\theta)$$
(e.g. because it is an isometry, by the three-point lemma).

```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[>=latex]
  \draw (-1.0,-1.6) -- (1.0,1.6); \draw (1.0,-1.6) -- (-1.0,1.6);
  \draw[red] (0.33,0.53) arc (58:122:0.62); \node[red] at (0,0.85) {\small$\theta$};
  \draw[blue,->] (0,0) -- (-0.85,-0.53) node[left] {\small$w$};
  \draw[blue,->] (0,0) -- (0.85,-0.53) node[right] {\small$v$};
  \node at (1.25,1.75) {\small$P_v$}; \node at (-1.25,1.75) {\small$P_w$};
\end{tikzpicture}
\end{document}
```
*The mirror lines $P_{\mathbf v}$ and $P_{\mathbf w}$ meet at angle $\theta$, measured anticlockwise from $P_{\mathbf v}$ to $P_{\mathbf w}$, and their unit normals $\mathbf v,\mathbf w$ are at angle $\pi-\theta$. Reflecting first in $P_{\mathbf v}$ and then in $P_{\mathbf w}$ rotates anticlockwise by $2\theta$.*

> [!note] Explanation
> Here $\theta$ must be read as a directed angle, from the first mirror $P_{\mathbf v}$ to the second mirror $P_{\mathbf w}$. The dot product $\mathbf v\cdot\mathbf w$ only fixes its size, and swapping the order of the two reflections gives the inverse rotation $\operatorname{Rot}_0(-2\theta)$. "Three-point lemma": an isometry of the plane is determined by where it sends three non-collinear points (see [[Groups - Chapter 1 Examples and Definitions#Lemma 1.24 — Three point lemma|Lemma 1.24]]). $S_{\mathbf w}S_{\mathbf v}$ fixes $0$ and agrees with $\operatorname{Rot}_0(2\theta)$ on two more points, so the two maps are equal.

**Remark.** If $A\in SO(2)$, its columns form an orthonormal basis, so
$$A=\begin{pmatrix}a&b\\-b&a\end{pmatrix}\quad\text{with }a^2+b^2=1,$$
so $a=\cos\theta$, $b=\sin\theta$ for some $\theta\in[0,2\pi)$.

### Lemma 8.16 — SO(3) consists of rotations

If $A\in SO(3)$, then $A$ is a rotation.

**Proof.** As in Lemma 8.15, $A$ is a product of $k$ reflections with $k\le3$ and $k$ even, so either $A=I$ or $A=S_{\mathbf u}S_{\mathbf v}$. Assume $P_{\mathbf v}\ne P_{\mathbf u}$ (else $A=I$). Then $P_{\mathbf u}\cap P_{\mathbf v}=\ell$ is a line through $0$.

```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}
  \draw (0,0) -- (2,0.7) -- (2,2.9) -- (0,2.2) -- cycle;
  \draw (2.6,0.2) -- (0.6,1.0) -- (0.6,3.2) -- (2.6,2.4) -- cycle;
  \draw[red,thick] (1.25,0.45) -- (1.25,2.65) node[midway,right] {$\ell$};
\end{tikzpicture}
\end{document}
```
*The planes $P_{\mathbf u}$ and $P_{\mathbf v}$ meet in the line $\ell$; $A=S_{\mathbf u}S_{\mathbf v}$ fixes $\ell$ pointwise.*

$S_{\mathbf u}$ and $S_{\mathbf v}$ both preserve $\ell$ pointwise, so $A$ does also. Let $H$ be the plane spanned by $\mathbf u$ and $\mathbf v$. This is orthogonal to $\ell$, so $A(H)=H$, and by Lemma 8.15, $A$ acts on $H$ by a rotation through angle $2\theta$ (for $\cos(\pi-\theta)=\mathbf u\cdot\mathbf v$).

Upshot: by linearity, on $\mathbb R^3$, $A$ is a rotation with axis $\ell$ and angle $2\theta$.

> [!note] Explanation
> $k\le3$ by Theorem 8.14, and $\det A=1=(-1)^k$ forces $k$ even, so $k=0$ or $2$. Both reflections map $H$ to itself: $\mathbf u,\mathbf v\in H$ and $S_{\mathbf u}$ only changes a vector by a multiple of $\mathbf u$. On $H$ they act as the 2D reflections of Lemma 8.15. Every vector of $\mathbb R^3$ is (point of $\ell$) + (point of $H$), so knowing $A$ on $\ell$ and on $H$ determines it.

**Remark.** By the three-point lemma, every isometry of $X\subseteq\mathbb R^2$ (where $X$ contains $3$ non-collinear points) is of the form
$$\mathbf x\mapsto A\mathbf x+\mathbf b,\qquad A\in O(2),\ \mathbf b\in\mathbb R^2.$$
