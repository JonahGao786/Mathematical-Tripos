---
title: Groups - Chapter 6 Quotients
course: Part IA Groups
material_type: lecture notes
chapter: 6
source_file: Ch.6 Quotients.pdf
drive_file_id: 11gqJN6VS81G3Kao-rsFYc2Js9IRJra8O
source_url: https://drive.google.com/file/d/11gqJN6VS81G3Kao-rsFYc2Js9IRJra8O/view
source_pages: 7
tags: [lecture, groups]
---

# Groups — Chapter 6: Quotients

> [!abstract] Overview
> Normal subgroups are the subgroups closed under conjugation, e.g. kernels of homomorphisms. A subgroup is normal exactly when its left and right cosets agree, and then the cosets themselves form a group, the quotient $G/H$. The isomorphism theorem identifies quotients with images of homomorphisms, $G/\ker\varphi\cong\operatorname{Im}\varphi$; simple groups have no normal subgroups other than $1$ and $G$.
> Prerequisites: [[Groups - Chapter 2 Lagrange's Theorem]] (cosets); [[Groups - Chapter 3 Group Actions]] (conjugation); [[Groups - Chapter 1 Examples and Definitions]] (homomorphisms, kernels).

## Results index

| Result | Statement in brief | Page |
| --- | --- | --- |
| [[#Definition 6.1 — Normal subgroup]] | $ghg^{-1}\in H$ for all $h\in H$, $g\in G$; $H\trianglelefteq G$; kernels are normal | 1 |
| [[#Lemma 6.2 — Normal iff left and right cosets agree]] | $H\trianglelefteq G\iff gH=Hg$ for all $g$ | 1–2 |
| [[#Theorem 6.3 — Quotient group]] | $G/H$ is a group under $(g_1H)(g_2H)=(g_1g_2)H$ | 2–3 |
| [[#Definition 6.4 — Quotient of G by H]] | the group $G/H$; examples $\mathbb Z/n\mathbb Z$, index $2$, $Q_8/\langle\pm1\rangle$ | 3–5 |
| [[#Theorem 6.5 — Isomorphism theorem]] | $G/\ker\varphi\cong\operatorname{Im}\varphi$ | 5–6 |
| [[#Definition 6.6 — Simple group]] | only normal subgroups $1$ and $G$; $C_p$ is simple | 7 |

## 6.1 Normal subgroups

Let $\varphi:G\to H$ be a homomorphism. We know that $\ker\varphi\le G$.

### Definition 6.1 — Normal subgroup

$H\le G$ is called **normal** if $ghg^{-1}\in H$ for every $h\in H$, $g\in G$. We write $H\trianglelefteq G$.

**Examples.**
1. $1\trianglelefteq G$ and $G\trianglelefteq G$, for any $G$.
2. If $G$ is abelian, then $H\trianglelefteq G$ for every $H\le G$.
3. $\langle r\rangle\trianglelefteq D_{2n}$, because $sr^ks^{-1}=r^{-k}$. But $\langle s\rangle$ is **not** normal: $rsr^{-1}=sr^{-2}\notin\langle s\rangle$.
4. $-\mathbf 1\in Q_8$ is the only element of order $2$. As conjugation preserves order, $\langle-\mathbf 1\rangle\trianglelefteq Q_8$.
5. Suppose $\varphi:G\to G'$ is a homomorphism. If $h\in\ker\varphi$ and $g\in G$, then
$$\varphi(ghg^{-1})=\varphi(g)\varphi(h)\varphi(g^{-1})=\varphi(g)\cdot e\cdot\varphi(g)^{-1}=e,$$
so $ghg^{-1}\in\ker\varphi$. Thus $\ker\varphi\trianglelefteq G$.

> [!note] Explanation
> In Example 3, $sr^ks^{-1}=r^{-k}$ is the dihedral relation $sr=r^{-1}s$ used $k$ times; and $rs=sr^{-1}$ (the same relation rearranged) gives $rsr^{-1}=sr^{-2}$, which is a reflection other than $s$ when $n\ge3$. In Example 4, $g(-\mathbf 1)g^{-1}$ has order $2$, so it must be $-\mathbf 1$ again.

### Lemma 6.2 — Normal iff left and right cosets agree

If $H\le G$, then $H\trianglelefteq G$ if and only if $gH=Hg$ for all $g\in G$.

**Proof.** ($\Rightarrow$) For any $h\in H$, $h'=ghg^{-1}\in H$ as $H\trianglelefteq G$. Thus
$$gh=ghg^{-1}g=h'g\in Hg.$$
So $gH\subseteq Hg$. Similarly $g^{-1}H\subseteq Hg^{-1}$, so $gH=Hg$.

($\Leftarrow$) Suppose $gH=Hg$. For any $h\in H$, $gh\in Hg$, so $gh=h'g$ for some $h'\in H$, so $ghg^{-1}=h'\in H$.

> [!note] Explanation
> The step "$g^{-1}H\subseteq Hg^{-1}$, so $gH=Hg$": take inverses of every element of both sides. The inverses of the elements of $g^{-1}H$ form $Hg$, and those of $Hg^{-1}$ form $gH$, so $Hg\subseteq gH$. Together with $gH\subseteq Hg$ this gives equality.

## 6.2 Quotient groups

### Theorem 6.3 — Quotient group

If $H\trianglelefteq G$, the set of left cosets $G/H$ is a group with
- operation $(g_1H)\cdot(g_2H)=(g_1g_2)H$;
- identity $H$.

**Proof.** We need to check that the operation is well defined, and that the group axioms hold.

*Well defined?* Suppose $g_1H=g_1'H$ and $g_2H=g_2'H$. So there exist $h_1,h_2\in H$ with
$$g_1=g_1'h_1,\qquad g_2=g_2'h_2.$$
As $H\trianglelefteq G$, $(g_2')^{-1}h_1g_2'=h_1'\in H$, so $h_1g_2'=g_2'h_1'$. Then
$$g_1g_2=g_1'h_1g_2'h_2=g_1'g_2'\underbrace{h_1'h_2}_{\in H},$$
so $g_1g_2H=g_1'g_2'H$. ✓
- *Associative?* Yes, from associativity of $G$.
- *Identity?* $H=eH$ works, by the identity of $G$.
- *Inverse?* $(gH)\cdot(g^{-1}H)=(gg^{-1})H=H$, so $(gH)^{-1}=g^{-1}H$.

> [!note] Explanation
> "Well defined" means the product does not depend on which representatives $g_1,g_2$ we pick for the two cosets. Normality is exactly what lets the stray $h_1$ move past $g_2'$; without it, different choices could give different cosets (e.g. with $H=\langle s\rangle\le D_{2n}$).

### Definition 6.4 — Quotient of G by H

If $H\trianglelefteq G$, the group $G/H$ of Theorem 6.3 is called the **quotient** of $G$ by $H$.

**Slogan #1.** $G/H$ is "$G$ with $H$ set to be equal to the identity".

**Examples.**
1. $G/1\cong G$ and $G/G\cong1$ for any $G$.
2. $n\mathbb Z\trianglelefteq\mathbb Z$ because $\mathbb Z$ is abelian. $\mathbb Z/n\mathbb Z$ is cyclic of order $n$, with generator $1+n\mathbb Z$. We have $\mathbb Z/n\mathbb Z\cong C_n\cong\mathbb Z_n$.

```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}
  \draw[thick] (0,0) ellipse (3 and 1.3);
  \draw (0,0) -- (0,1.3); \draw (0,0) -- (-2.4,-0.78); \draw (0,0) -- (2.4,-0.78);
  \node at (-1.15,0.45) {\small$0,\pm3,\pm6,\dots$};
  \node at (1.3,0.3) {\small$1,4,7,\dots$};
  \node at (0,-0.75) {\small$2,5,8,\dots$};
  \node at (-1.6,1.55) {$0+3Z$};
  \node at (2.9,1.2) {$1+3Z$};
  \node at (0,-1.65) {$2+3Z$};
\end{tikzpicture}
\end{document}
```
*$n=3$: the three cosets of $3\mathbb Z$ in $\mathbb Z$ (with negatives filling in each class, e.g. $-1\in2+3\mathbb Z$), the three elements of $\mathbb Z/3\mathbb Z$.*

3. If $|G:H|=2$, then $gH=G\setminus H=Hg$ for $g\notin H$ (any such $g$). So $H\trianglelefteq G$ automatically! And $G/H\cong C_2$ because $|G:H|=2$.

```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}
  \draw[thick] (0,0) ellipse (2 and 1);
  \draw (0,1) -- (0,-1);
  \node at (-1,0) {$H$}; \node at (1,0) {$gH$};
\end{tikzpicture}
\end{document}
```
*A subgroup of index $2$: the only other coset, on either side, is the complement $G\setminus H$.*

4. A special case of (3): $C_n=\langle r\rangle\trianglelefteq D_{2n}$, with $|D_{2n}:\langle r\rangle|=\frac{2n}n=2$. So $D_{2n}/C_n\cong C_2$.
5. $\langle\pm\mathbf 1\rangle\trianglelefteq Q_8$, with $|Q_8:\langle\pm\mathbf 1\rangle|=\frac82=4$, so $Q_8/\langle\pm\mathbf 1\rangle$ is either $C_4$ or $C_2\times C_2$. The four cosets are

| $\pm\mathbf 1$ | $\pm\mathbf i$ |
| --- | --- |
| $\pm\mathbf j$ | $\pm\mathbf k$ |

Notice that $\mathbf i^2=-\mathbf 1$, and similarly for $\mathbf j,\mathbf k$, so every element of $Q_8/\langle\pm\mathbf 1\rangle$ has order dividing $2$. So, with $H=\langle\pm\mathbf 1\rangle$,
$$Q_8/\langle\pm\mathbf 1\rangle\cong C_2\times C_2\cong\langle\mathbf iH\rangle\times\langle\mathbf jH\rangle.$$

**Warning.**
- $C_2=\langle g^2\rangle\trianglelefteq C_4=\langle g\rangle$, with $C_4/C_2\cong C_2$.
- $C_2=\langle a\rangle\trianglelefteq K_4\cong\langle a\rangle\times\langle b\rangle$, with $K_4/C_2\cong C_2$.
- But $C_4\not\cong K_4$. In particular, $A/B\cong C$ does **not** imply $A\cong B\times C$.

### Theorem 6.5 — Isomorphism theorem

If $\varphi:G\to H$ is a homomorphism, then
$$G/\ker\varphi\cong\operatorname{Im}\varphi.$$

**Proof.** As $\ker\varphi\trianglelefteq G$ ([[#Definition 6.1 — Normal subgroup|Example 5]]), $G/\ker\varphi$ is a group. Define
$$\bar\varphi:G/\ker\varphi\to\operatorname{Im}\varphi,\qquad g\ker\varphi\mapsto\varphi(g).$$
We need $\bar\varphi$ to be well defined, and an isomorphism.
- *Well defined?* Suppose $g_1\ker\varphi=g_2\ker\varphi$, i.e. $g_1=g_2k$ for some $k\in\ker\varphi$. Then
$$\varphi(g_1)=\varphi(g_2k)=\varphi(g_2)\varphi(k)=\varphi(g_2),\qquad\text{i.e.}\qquad\bar\varphi(g_1\ker\varphi)=\bar\varphi(g_2\ker\varphi).$$
- *Homomorphism?* For $g_1,g_2\in G$,
$$\begin{aligned}
\bar\varphi\big((g_1\ker\varphi)(g_2\ker\varphi)\big)&=\bar\varphi\big((g_1g_2)\ker\varphi\big)\\
&=\varphi(g_1g_2)=\varphi(g_1)\varphi(g_2)\\
&=\bar\varphi(g_1\ker\varphi)\,\bar\varphi(g_2\ker\varphi).
\end{aligned}$$
- *Surjective?* Any element of $\operatorname{Im}\varphi$ is $\varphi(g)=\bar\varphi(g\ker\varphi)$ for some $g\in G$.
- *Injective?* Suppose $\bar\varphi(g\ker\varphi)=e$. Then $\varphi(g)=e$, i.e. $g\in\ker\varphi$, so $g\ker\varphi=\ker\varphi$. So $\ker\bar\varphi=\{\ker\varphi\}=\{\operatorname{id}_{G/\ker\varphi}\}$, and $\bar\varphi$ is injective.

**Slogan #2.** "Quotient groups are images."

**Examples.**
1. $\varphi:\mathbb Z\to\mathbb C^\times=(\mathbb C\setminus\{0\},\times,1)$, $k\mapsto e^{2\pi ik/n}$, is a homomorphism with image $C_n$ (the $n$th roots of unity) and kernel $n\mathbb Z$. This re-proves $\mathbb Z/n\mathbb Z\cong C_n$.
2. $\varphi:\mathbb R\to\mathbb C^\times$, $t\mapsto e^{2\pi it}$, is a homomorphism with $\ker\varphi=\mathbb Z$ and
$$\operatorname{Im}\varphi=\{z\in\mathbb C^\times:|z|=1\}=U(1),$$
so $\mathbb R/\mathbb Z\cong U(1)$.

> [!note] Explanation
> The isomorphism theorem says: to understand $G/H$, find a homomorphism out of $G$ whose kernel is exactly $H$; then $G/H$ "is" its image. In Example 2, adding an integer to $t$ does not change $e^{2\pi it}$, so $\mathbb R/\mathbb Z$ is the real line wrapped around the unit circle.

### Definition 6.6 — Simple group

A group $G$ is **simple** if its only normal subgroups are $1$ and $G$.

In particular, every homomorphism $G\to H$ from a simple group is either trivial or injective.

**Example.** $C_p$ is simple for every prime $p$. Why? Every non-trivial element is a generator. Later we'll get our first example of a non-abelian simple group.

A cyclic group of composite order is not simple: e.g. $C_{132}=\langle g\rangle$ has $C_{22}\trianglelefteq C_{132}$, with $C_{132}/C_{22}\cong C_6$.

> [!note] Explanation
> The kernel of a homomorphism is a normal subgroup, so in a simple group it is $1$ (the map is injective) or $G$ (the map is trivial). For $C_p$: any subgroup containing an element $x\ne e$ contains $\langle x\rangle=C_p$, so the only subgroups at all are $1$ and $C_p$.
