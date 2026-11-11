---
title: Groups - Chapter 5 Finite Groups
course: Part IA Groups
material_type: lecture notes
chapter: 5
source_file: Ch.5 Finite Groups.pdf
drive_file_id: 1ELnkPWzlB1-HPs9ERuMIKGAXEJi70axO
source_url: https://drive.google.com/file/d/1ELnkPWzlB1-HPs9ERuMIKGAXEJi70axO/view
source_pages: 9
tags: [lecture, groups]
---

# Groups — Chapter 5: Finite Groups

> [!abstract] Overview
> Towards listing groups by order. Groups of prime order are cyclic; order $4$ already allows something other than $C_4$, the Klein four-group $C_2\times C_2$. The direct product theorem recognises when a group is the direct product of two subgroups. With it: every group of order $4$ is $C_4$ or $K_4$, $C_m\times C_n\cong C_{mn}$ for coprime $m,n$, every group of order $6$ is $C_6$ or $D_6$, and order $8$ brings in the quaternion group $Q_8$.
> Prerequisites: [[Groups - Chapter 2 Lagrange's Theorem]] (groups of prime order); [[Groups - Chapter 1 Examples and Definitions]] (homomorphisms, kernels).

## Results index

| Result | Statement in brief | Page |
| --- | --- | --- |
| [[#Definition — Direct product]] | $G\times H$ with componentwise operation; $\lvert G\times H\rvert=\lvert G\rvert\lvert H\rvert$ | 1 |
| [[#Example — Klein four-group]] | $K_4=C_2\times C_2$, not cyclic | 1 |
| [[#Theorem 5.1 — Direct product theorem]] | $H_1\cap H_2=\{e\}$, commuting, $G=H_1H_2\Rightarrow G\cong H_1\times H_2$ | 2–3 |
| [[#Lemma 5.2 — Groups of order 4]] | $\lvert G\rvert=4\Rightarrow G\cong C_4$ or $K_4$ | 3 |
| [[#Theorem 5.3 — Chinese remainder theorem]] | $\gcd(m,n)=1\Rightarrow C_m\times C_n\cong C_{mn}$ | 4 |
| [[#Lemma 5.4 — Groups of order 6]] | $\lvert G\rvert=6\Rightarrow G\cong C_6$ or $D_6$ | 5–6 |
| [[#Definition — Quaternion group]] | $Q_8=\{\pm1,\pm i,\pm j,\pm k\}$, non-abelian, $Q_8\not\cong D_8$ | 6–7 |
| [[#Lemma 5.6 — Groups of order 8]] | $C_2^3$, $C_2\times C_4$, $C_8$, $D_8$ or $Q_8$ | 7–9 |

## 5.1 Groups of small order

Let's try to list groups by order.
- $|G|=1\Rightarrow G\cong\{e\}$.
- $|G|=2\Rightarrow G\cong C_2$ and $|G|=3\Rightarrow G\cong C_3$ (as $|G|$ is prime).
- $|G|=4$? There is $C_4$; anything else?

### Definition — Direct product

**Recall.** If $G,H$ are groups, their **product** (sometimes "**direct product**") is
$$G\times H=\{(g,h)\mid g\in G,\ h\in H\},$$
with
- operation $(g_1,h_1)\cdot(g_2,h_2)=(g_1\cdot g_2,\ h_1\cdot h_2)$;
- identity $(e_G,e_H)$;
- inverses $(g,h)^{-1}=(g^{-1},h^{-1})$.

Then $|G\times H|=|G||H|$.

### Example — Klein four-group

The group $K_4=C_2\times C_2$ is often called the **Klein four-group**.
- It has $4$ elements: $(1,1)$, $(-1,1)$, $(1,-1)$, $(-1,-1)$ (writing $C_2=\{1,-1\}$ under multiplication).
- Each element has order dividing $2$, so $K_4$ is **not** cyclic (no element of order $4$). So $K_4\not\cong C_4$.

### Theorem 5.1 — Direct product theorem

If $H_1,H_2\le G$ and
1. $H_1\cap H_2=\{e\}$,
2. $h_1h_2=h_2h_1$ whenever $h_1\in H_1$, $h_2\in H_2$,
3. for each $g\in G$ there exist $h_1\in H_1$ and $h_2\in H_2$ with $g=h_1h_2$ (write $G=H_1H_2$),

then $G\cong H_1\times H_2$.

**Proof.** Define
$$\varphi:H_1\times H_2\to G,\qquad(h_1,h_2)\mapsto h_1h_2.$$
We want $\varphi$ to be an isomorphism.
- *$\varphi$ is a homomorphism:*
$$\begin{aligned}
\varphi(h_1,h_2)\,\varphi(h_1',h_2')&=h_1h_2h_1'h_2'\\
&=h_1h_1'h_2h_2' &&\text{by (2)}\\
&=\varphi(h_1h_1',\ h_2h_2').
\end{aligned}$$
- *$\varphi$ is surjective:* yes, by (3).
- *$\varphi$ is injective:* we need $\ker\varphi=\{e\}$. Suppose $\varphi(h_1,h_2)=e$, i.e. $h_1h_2=e$. Then $h_1=h_2^{-1}\in H_1\cap H_2=\{e\}$ by (1). So $h_1=h_2^{-1}=e$, so $(h_1,h_2)=(e,e)$, i.e. $\varphi$ is injective. $\square$

> [!note] Explanation
> Each hypothesis is used once. (2) lets $h_2$ slide past $h_1'$, which is exactly what makes multiplying in $G$ look like multiplying componentwise. (3) says every element of $G$ is hit. (1) says the two subgroups overlap only in $e$, so $h_1h_2=e$ forces both factors to be $e$.

**Remarks.**
- If $|H_1|$ and $|H_2|$ are coprime, then $H_1\cap H_2=\{e\}$ automatically.
- If $H_1\cap H_2=\{e\}$, then $|H_1H_2|=|H_1|\cdot|H_2|$.
- In particular, if we know $|G|=|H_1|\cdot|H_2|$, then (3) follows automatically from (1).

> [!note] Explanation
> First remark: $H_1\cap H_2$ is a subgroup of both, so by Lagrange its order divides $|H_1|$ and $|H_2|$, hence divides their gcd $1$. Second remark: $h_1h_2=h_1'h_2'$ gives $h_1'^{-1}h_1=h_2'h_2^{-1}\in H_1\cap H_2=\{e\}$, so the $|H_1||H_2|$ products are all different. Third: then $H_1H_2$ is a subset of $G$ of the same size, so it is all of $G$.

### Lemma 5.2 — Groups of order 4

If $|G|=4$, then $G\cong C_4$ or $G\cong K_4$.

**Proof.** By Lagrange, every non-trivial element has order $2$ or $4$.
- If there is an element $g$ of order $4$: $C_4\cong\langle g\rangle\le G$ and $4=|C_4|=|G|$, so $C_4\cong G$.
- Otherwise every non-trivial element has order $2$. Let $a,b\in G$ be distinct and non-trivial. Then
  1. $\langle a\rangle\cap\langle b\rangle=\{e,a\}\cap\{e,b\}=\{e\}$;
  2. $ab=ba$ (by Example Sheet 1, Q11);
  3. $|\langle a\rangle\langle b\rangle|=4$: the elements $e,a,b,ab$ (immediate since $a,b$ are distinct and non-trivial).

  So by Theorem 5.1, $G\cong\langle a\rangle\times\langle b\rangle\cong C_2\times C_2\cong K_4$. $\square$

> [!note] Explanation
> Why $ab=ba$ when every element has order $2$: then each element is its own inverse, so $ab=(ab)^{-1}=b^{-1}a^{-1}=ba$.

### Theorem 5.3 — Chinese remainder theorem

If $\gcd(m,n)=1$, then $C_m\times C_n\cong C_{mn}$.

**Proof.** Say $C_{mn}=\langle g\rangle$. Let
$$H_1=\langle g^n\rangle\cong C_m,\qquad H_2=\langle g^m\rangle\cong C_n.$$
Let's check the hypotheses of Theorem 5.1.
1. For $0\le k\le mn-1$: $g^k\in H_1\iff n\mid k$, and $g^k\in H_2\iff m\mid k$. So
$$g^k\in H_1\cap H_2\iff\operatorname{lcm}(m,n)\mid k.$$
Now $\gcd(m,n)=1\iff\operatorname{lcm}(m,n)=mn$. Thus $k=0$ and $g^k=e$, so $H_1\cap H_2=\{e\}$.
2. Immediate, as $C_{mn}$ is abelian.
3. Fix $g^k\in C_{mn}$. By Bézout, $k=pm+qn$ for some $p,q\in\mathbb Z$, so
$$g^k=(g^n)^q\cdot(g^m)^p\in H_1H_2.$$

So by Theorem 5.1, $C_{mn}\cong C_m\times C_n$. $\square$

## 5.2 Groups of order 5 to 8

Let's continue trying to identify small-order groups.
- $|G|=5\Rightarrow G\cong C_5$, as $5$ is prime.
- $|G|=6$? We have $D_6$, $C_6$, $S_3$, …
  - $D_6$ and $C_6$ are not isomorphic (e.g. because $C_6$ is abelian and $D_6$ isn't).
  - $D_6\cong S_3$: symmetries of an equilateral triangle correspond one-to-one to permutations of the set of its $3$ vertices.

### Lemma 5.4 — Groups of order 6

If $|G|=6$, then $G\cong C_6$ or $G\cong D_6$.

**Proof.** By [[Groups - Chapter 3 Group Actions#Theorem 3.8 — Cauchy's theorem|Cauchy's theorem]], there are elements $r,s\in G$ with $\operatorname{ord}(r)=3$ and $\operatorname{ord}(s)=2$. By Lagrange,
$$|G:\langle r\rangle|=\frac63=2.$$
As $2$ and $3$ are coprime, $s\notin\langle r\rangle$. So
$$G=\langle r\rangle\sqcup s\langle r\rangle=\langle r\rangle\sqcup\langle r\rangle s,$$
so $s\langle r\rangle=\langle r\rangle s$. Thus $sr=r^is$ for some $i\in\{0,1,2\}$.
- $i=0$: $sr=s\Rightarrow r=e$, a contradiction.
- $i=1$: $sr=rs$, so $\langle r\rangle$ and $\langle s\rangle$ commute, and
$$G\cong\langle r\rangle\times\langle s\rangle\cong C_3\times C_2\cong C_6$$
by Theorem 5.1 and then Theorem 5.3.
- $i=2$: $sr=r^2s=r^{-1}s$. We recognise the dihedral relation! With $\operatorname{ord}(r)\mid3$, $\operatorname{ord}(s)\mid2$, $sr=r^{-1}s$ and $|G|=6$,
$$G\cong D_6$$
by [[Groups - Chapter 1 Examples and Definitions#Corollary 1.41 — Recognising dihedral groups|Corollary 1.41]]. $\square$

> [!note] Explanation
> The left cosets and the right cosets of $\langle r\rangle$ both split $G$ into $\langle r\rangle$ and "everything else", so $s\langle r\rangle$ and $\langle r\rangle s$ are the same set. Hence $sr$, which lies in $s\langle r\rangle$, can be written as $r^is$. For $i=1$, Theorem 5.1 applies by the Remarks: $|\langle r\rangle|=3$ and $|\langle s\rangle|=2$ are coprime and $|G|=3\cdot2$.

- $|G|=7\Rightarrow G\cong C_7$, because $7$ is prime.
- $|G|=8$? We already have:

| group | | orders of elements |
| --- | --- | --- |
| $D_8$ | non-abelian | $1,2,4$ |
| $C_8$ | abelian | $1,2,4,8$ |
| $C_4\times C_2$ | abelian | $1,2,4$ |
| $C_2\times C_2\times C_2$ | abelian | $1,2$ |

### Definition — Quaternion group

Consider the $2\times2$ matrices
$$\mathbf 1=\begin{pmatrix}1&0\\0&1\end{pmatrix},\quad\mathbf i=\begin{pmatrix}i&0\\0&-i\end{pmatrix},\quad\mathbf j=\begin{pmatrix}0&1\\-1&0\end{pmatrix},\quad\mathbf k=\begin{pmatrix}0&i\\i&0\end{pmatrix}.$$
Note that
$$\mathbf i^2=\mathbf j^2=\mathbf k^2=-\mathbf 1,\qquad\mathbf i\mathbf j=\mathbf k,\quad\mathbf j\mathbf k=\mathbf i,\quad\mathbf k\mathbf i=\mathbf j,\qquad(-\mathbf 1)\mathbf i=-\mathbf i,\ \text{etc.}$$
Altogether this implies that the set $\{\pm\mathbf 1,\pm\mathbf i,\pm\mathbf j,\pm\mathbf k\}$ is a group, with binary operation matrix multiplication and identity element $\mathbf 1$. This is called the **quaternion group** $Q_8$.

Observe that $\mathbf i\mathbf j=\mathbf k$ but $\mathbf j\mathbf i=-\mathbf k$, so $Q_8$ is non-abelian.
- $Q_8$ has $1$ element of order $2$ (namely $-\mathbf 1$).
- $D_8$ has $4+1$ elements of order $2$ (four reflections and the half-turn).

So $Q_8\not\cong D_8$.

### Lemma 5.6 — Groups of order 8

If $|G|=8$, then $G\cong C_2\times C_2\times C_2$, $C_2\times C_4$, $C_8$, $D_8$ or $Q_8$.

**Proof.** By Lagrange, every element has order $1$, $2$, $4$ or $8$.
- If there is an element of order $8$, $G\cong C_8$.
- Suppose every non-trivial element has order $2$.
  - Choose non-trivial elements $a$ and $b\ne a$. Then $\langle\{a,b\}\rangle=\langle a\rangle\times\langle b\rangle\cong C_2\times C_2$ by Theorem 5.1 (with $ab=ba$ by Example Sheet 1, Q11).
  - Choose $c\in G\setminus\langle\{a,b\}\rangle$; $c$ commutes with $a$ and $b$ (Example Sheet 1, Q11). So again by Theorem 5.1,
$$G\cong\langle\{a,b\}\rangle\times\langle c\rangle\cong C_2\times C_2\times C_2.$$
- Remaining cases: $G$ has an element of order $4$, say $a$ (and no elements of order $8$). Let $b\in G\setminus\langle a\rangle$; then $\operatorname{ord}(b)=2$ or $4$, and
$$G=\langle a\rangle\sqcup b\langle a\rangle=\langle a\rangle\sqcup\langle a\rangle b,$$
so $ba=a^ib$ for some $i\in\{0,1,2,3\}$.
  - **A) $i=0$:** $ba=b\Rightarrow a=e$, a contradiction.
  - **B) $i=1$:** $ba=ab$, so $G$ is abelian.
    - B1) $\operatorname{ord}(b)=2$: $\langle a\rangle\cap\underbrace{\langle b\rangle}_{\{e,b\}}=\{e\}$. By Theorem 5.1, $G\cong C_4\times C_2$.
    - B2) $\operatorname{ord}(b)=4$: $\langle a\rangle\cap\langle b\rangle\ne\{e\}$ (by counting, as $|G|=8$). Observe we must have $b^2=a^2$ (thinking about orders, and $b\notin\langle a\rangle$). Now $\operatorname{ord}(ba^{-1})=2$, $\langle ba^{-1}\rangle\cap\langle a\rangle=\{e\}$ and $G=\langle a\rangle\sqcup(ba^{-1})\langle a\rangle$. Similarly to B1, $G\cong\langle a\rangle\times\langle ba^{-1}\rangle\cong C_4\times C_2$.
  - **C) $i=2$:** $ba=a^2b\Rightarrow bab^{-1}=a^2$. But $a$ has order $4$ and $a^2$ has order $2$, so $a$ and $a^2$ can't be conjugate (Example Sheet 2, Q1): a contradiction.
  - **D) $i=3$:** $ba=a^3b=a^{-1}b$.
    - D1) $\operatorname{ord}(b)=2$: by [[Groups - Chapter 1 Examples and Definitions#Corollary 1.41 — Recognising dihedral groups|Corollary 1.41]], $G\cong D_8$.
    - D2) $\operatorname{ord}(b)=4$: as in B2, $a^2=b^2$. Set $\mathbf i=a$, $\mathbf j=b$, $\mathbf k=ab$, $-\mathbf 1=a^2=b^2$. The elements of $G$ are

      | $e$ | $a$ | $a^2$ | $a^3$ | $b$ | $ab$ | $a^2b$ | $a^3b$ |
      | --- | --- | --- | --- | --- | --- | --- | --- |
      | $\mathbf 1$ | $\mathbf i$ | $-\mathbf 1$ | $-\mathbf i$ | $\mathbf j$ | $\mathbf k$ | $-\mathbf j$ | $-\mathbf k$ |

      and one can check this gives an isomorphism $Q_8\to G$. $\square$

> [!note] Explanation
> Two steps in B2. *Why the intersection is non-trivial:* if $\langle a\rangle\cap\langle b\rangle=\{e\}$, then by the Remarks after Theorem 5.1, $|\langle a\rangle\langle b\rangle|=4\cdot4=16>8$. *Why $b^2=a^2$:* that intersection is a non-trivial subgroup of the cyclic group $\langle b\rangle\cong C_4$, so it contains $b^2$, the only element of order $2$ in $\langle b\rangle$; and it cannot contain $b$ or $b^3$, since then $b\in\langle a\rangle$. In the same way, the only element of order $2$ in $\langle a\rangle$ is $a^2$, so $b^2=a^2$. Then $(ba^{-1})^2=b^2a^{-2}=e$ ($G$ is abelian in case B), and $ba^{-1}\ne e$ because $b\notin\langle a\rangle$.
