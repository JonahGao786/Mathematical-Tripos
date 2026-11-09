---
title: Direct Products of Groups
course: Part IA Groups
material_type: concept note
tags: [concept, groups]
---

# Direct Products of Groups

> [!abstract] In one paragraph
> $G\times H$ is the set of pairs with componentwise multiplication, of order $|G||H|$. It builds new groups from old, e.g. the Klein four-group $C_2\times C_2$, which is not cyclic. Conversely, the direct product theorem recognises $G\cong H_1\times H_2$ from two commuting subgroups that meet only in $e$ and together give all of $G$.

## Definitions

- **Direct product** $G\times H$: $(g_1,h_1)(g_2,h_2)=(g_1g_2,h_1h_2)$, identity $(e_G,e_H)$, inverse $(g^{-1},h^{-1})$. → [[Groups - Chapter 5 Finite Groups#Definition — Direct product|lecture]]
- **Klein four-group** $K_4=C_2\times C_2$: every element has order dividing $2$, so $K_4\not\cong C_4$. → [[Groups - Chapter 5 Finite Groups#Example — Klein four-group|lecture]]

## Key results

- **Theorem 5.1 — Direct product theorem.** If $H_1\cap H_2=\{e\}$, elements of $H_1$ and $H_2$ commute, and $G=H_1H_2$, then $G\cong H_1\times H_2$. *Idea:* $(h_1,h_2)\mapsto h_1h_2$ is a homomorphism (commuting), onto ($G=H_1H_2$), with trivial kernel ($H_1\cap H_2=\{e\}$). → [[Groups - Chapter 5 Finite Groups#Theorem 5.1 — Direct product theorem|proof]]
- Groups of order $1$, $2$, $3$ are $\{e\}$, $C_2$, $C_3$ (prime order ⇒ cyclic). → [[Cosets and Lagrange's Theorem]]

## Small groups

- **Lemma 5.2.** Order $4$: $C_4$ or $K_4$ (if no element of order $4$, all elements square to $e$, so the group is abelian and $\langle a\rangle\times\langle b\rangle$). → [[Groups - Chapter 5 Finite Groups#Lemma 5.2 — Groups of order 4|proof]]
- **Theorem 5.3 — CRT.** $\gcd(m,n)=1\Rightarrow C_m\times C_n\cong C_{mn}$, via $H_1=\langle g^n\rangle$, $H_2=\langle g^m\rangle$ and Bézout. → [[Groups - Chapter 5 Finite Groups#Theorem 5.3 — Chinese remainder theorem|proof]]
- **Lemma 5.4.** Order $6$: $C_6$ or $D_6$ ($\cong S_3$); Cauchy gives $r,s$ of orders $3,2$, and $sr=r^is$ with $i=1$ (cyclic) or $i=2$ (dihedral). → [[Groups - Chapter 5 Finite Groups#Lemma 5.4 — Groups of order 6|proof]]
- **Quaternion group** $Q_8=\{\pm1,\pm i,\pm j,\pm k\}$, $i^2=j^2=k^2=-1$, $ij=k=-ji$; one element of order $2$, so $Q_8\not\cong D_8$. → [[Groups - Chapter 5 Finite Groups#Definition — Quaternion group|lecture]]
- **Lemma 5.6.** Order $8$: $C_2^3$, $C_2\times C_4$, $C_8$, $D_8$ or $Q_8$. → [[Groups - Chapter 5 Finite Groups#Lemma 5.6 — Groups of order 8|lecture]]

## Related

[[Groups]] · [[Cyclic Groups and Element Orders]] · [[Homomorphisms and Isomorphisms]] · [[Subgroups and Generated Subgroups]]
