---
title: Groups - Chapter 6 Quotients
course: Part IA Groups
material_type: lecture notes
chapter: 6
source_file: Ch.6 Quotients.pdf
drive_file_id: 11gqJN6VS81G3Kao-rsFYc2Js9IRJra8O
source_url: https://drive.google.com/file/d/11gqJN6VS81G3Kao-rsFYc2Js9IRJra8O/view
source_pages: 3
tags: [lecture, groups]
---

# Groups — Chapter 6: Quotients

> [!abstract] Overview
> Normal subgroups are the subgroups closed under conjugation, e.g. kernels of homomorphisms. A subgroup is normal exactly when its left and right cosets agree, and then the cosets themselves form a group, the quotient $G/H$.
> Prerequisites: [[Groups - Chapter 2 Lagrange's Theorem]] (cosets); [[Groups - Chapter 3 Group Actions]] (conjugation); [[Groups - Chapter 1 Examples and Definitions]] (homomorphisms, kernels).

## Results index

| Result | Statement in brief | Page |
| --- | --- | --- |
| [[#Definition 6.1 — Normal subgroup]] | $ghg^{-1}\in H$ for all $h\in H$, $g\in G$; $H\trianglelefteq G$; kernels are normal | 1 |
| [[#Lemma 6.2 — Normal iff left and right cosets agree]] | $H\trianglelefteq G\iff gH=Hg$ for all $g$ | 1–2 |
| [[#Theorem 6.3 — Quotient group]] | $G/H$ is a group under $(g_1H)(g_2H)=(g_1g_2)H$ | 2–3 |
| [[#Definition 6.4 — Quotient of G by H]] | the group $G/H$ | 3 |

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

($\Leftarrow$) Suppose $gH=Hg$. For any $h\in H$, $gh\in Hg$, so $gh=h'g$ for some $h'\in H$, so $ghg^{-1}=h'\in H$. $\square$

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
- *Inverse?* $(gH)\cdot(g^{-1}H)=(gg^{-1})H=H$, so $(gH)^{-1}=g^{-1}H$. $\square$

> [!note] Explanation
> "Well defined" means the product does not depend on which representatives $g_1,g_2$ we pick for the two cosets. Normality is exactly what lets the stray $h_1$ move past $g_2'$; without it, different choices could give different cosets (e.g. with $H=\langle s\rangle\le D_{2n}$).

### Definition 6.4 — Quotient of G by H

If $H\trianglelefteq G$, the group $G/H$ of Theorem 6.3 is called the **quotient** of $G$ by $H$.
