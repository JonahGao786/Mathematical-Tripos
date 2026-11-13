---
title: Normal Subgroups and Quotients
course: Part IA Groups
material_type: concept note
tags: [concept, groups]
---

# Normal Subgroups and Quotients

> [!abstract] In one paragraph
> A subgroup $H$ is normal ($H\trianglelefteq G$) when conjugating by any $g$ keeps it inside itself; equivalently, its left and right cosets agree. Kernels of homomorphisms are always normal. For normal $H$, multiplying cosets by representatives, $(g_1H)(g_2H)=(g_1g_2)H$, is well defined, and makes $G/H$ a group.

## Definitions

- **Normal subgroup** $H\trianglelefteq G$: $ghg^{-1}\in H$ for all $h\in H$, $g\in G$. Examples: $\{e\}$, $G$, any subgroup of an abelian group, $\langle r\rangle\trianglelefteq D_{2n}$ (but not $\langle s\rangle$), $\langle-1\rangle\trianglelefteq Q_8$, $\ker\varphi$. → [[Groups - Chapter 6 Quotients#Definition 6.1 — Normal subgroup|lecture]]
- **Quotient** $G/H$: the group of left cosets of a normal $H$. → [[Groups - Chapter 6 Quotients#Definition 6.4 — Quotient of G by H|lecture]]

## Key results

- **Lemma 6.2.** $H\trianglelefteq G\iff gH=Hg$ for all $g$ (from $gh=(ghg^{-1})g$). → [[Groups - Chapter 6 Quotients#Lemma 6.2 — Normal iff left and right cosets agree|proof]]
- **Theorem 6.3.** For $H\trianglelefteq G$, $G/H$ is a group with identity $H$ and $(gH)^{-1}=g^{-1}H$; normality makes the product independent of the representatives. → [[Groups - Chapter 6 Quotients#Theorem 6.3 — Quotient group|proof]]
- **Examples of quotients:** $\mathbb Z/n\mathbb Z\cong C_n$; an index-$2$ subgroup is automatically normal with quotient $C_2$ (e.g. $D_{2n}/C_n$); $Q_8/\langle\pm1\rangle\cong C_2\times C_2$. Warning: $A/B\cong C$ does not give $A\cong B\times C$ ($C_4$ vs $K_4$). → [[Groups - Chapter 6 Quotients#Definition 6.4 — Quotient of G by H|lecture]]
- **Theorem 6.5 — Isomorphism theorem.** $G/\ker\varphi\cong\operatorname{Im}\varphi$ via $g\ker\varphi\mapsto\varphi(g)$: "quotient groups are images", e.g. $\mathbb R/\mathbb Z\cong U(1)$. → [[Groups - Chapter 6 Quotients#Theorem 6.5 — Isomorphism theorem|proof]]
- **Simple groups** have no normal subgroups except $1$, $G$; every homomorphism out of one is trivial or injective; $C_p$ is simple. → [[Groups - Chapter 6 Quotients#Definition 6.6 — Simple group|lecture]]

## Related

[[Cosets and Lagrange's Theorem]] · [[Homomorphisms and Isomorphisms]] · [[Group Actions]] · [[Groups]]
