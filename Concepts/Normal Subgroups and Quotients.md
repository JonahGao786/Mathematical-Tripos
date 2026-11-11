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

## Related

[[Cosets and Lagrange's Theorem]] · [[Homomorphisms and Isomorphisms]] · [[Group Actions]] · [[Groups]]
