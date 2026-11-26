---
title: Countable Sets
course: Part IA Numbers and Sets
material_type: concept note
tags: [concept, numbers-and-sets]
---

# Countable Sets

> [!abstract] In one paragraph
> A set is countable if it is finite or there is a bijection with $\mathbb N$, which means its elements can be listed $x_1,x_2,\dots$. It is countably infinite if it is countable but not finite. Listing cleverly, or injecting into $\mathbb N$, shows that sets which "look bigger" than $\mathbb N$, such as $\mathbb Z$, $\mathbb N\times\mathbb N$, $\mathbb Q$ and the algebraic numbers, are still countable. Diagonal arguments show that $\mathbb R$ and $\mathcal P(\mathbb N)$ are not.

## Definitions

- **Countable / countably infinite.** → [[Numbers and Sets - Chapter 4 Countability#Definition — Countable and countably infinite|lecture]]

## Key results

- **Lemma 1.** Every subset of $\mathbb N$ is countable. *Idea:* list it in increasing order using WOP. → [[Numbers and Sets - Chapter 4 Countability#Lemma 1 — Subsets of N are countable|proof]]
- **Theorem 2.** $X$ countable $\iff$ there is an injection $X\to\mathbb N$ $\iff$ $X=\varnothing$ or there is a surjection $\mathbb N\to X$. So subsets of countable sets are countable (Cor 3). → [[Numbers and Sets - Chapter 4 Countability#Theorem 2 — Characterisations of countability|proof]] · [[Numbers and Sets - Chapter 4 Countability#Corollary 3 — Subsets of countable sets|proof]]
- **Theorem 4 / Corollary 5.** $\mathbb N\times\mathbb N$ is countable (diagonal list, or $2^x3^y$), hence so are $\mathbb Z\times\mathbb Z$ and $\mathbb Z^k$. → [[Numbers and Sets - Chapter 4 Countability#Theorem 4 — N × N is countable|proof]] · [[Numbers and Sets - Chapter 4 Countability#Corollary 5 — Z × Z is countable|proof]]
- **Theorem 6.** A countable union of countable sets is countable ($a_j^{(i)}\mapsto2^i3^j$); so $\mathbb Q$ is countable. → [[Numbers and Sets - Chapter 4 Countability#Theorem 6 — Countable unions of countable sets|proof]]
- **Theorem 7.** The algebraic numbers are countable (countably many integer polynomials, each with finitely many roots). → [[Numbers and Sets - Chapter 4 Countability#Theorem 7 — Algebraic numbers are countable|proof]]
- **Theorem 8.** $\mathbb R$ (indeed $(0,1)$) is uncountable: the diagonal argument builds a real differing from the $n$th listed real in the $n$th decimal place. **Cor 9:** so the transcendental numbers are uncountable. → [[Numbers and Sets - Chapter 4 Countability#Theorem 8 — R is uncountable|proof]] · [[Numbers and Sets - Chapter 4 Countability#Corollary 9 — Transcendental numbers|proof]]
- **Theorems 10–11.** $\mathcal P(\mathbb N)$ is uncountable, and no $f:X\to\mathcal P(X)$ is onto: $\{x:x\notin f(x)\}$ is missed. Hence there is no universal set. → [[Numbers and Sets - Chapter 4 Countability#Theorem 10 — P(N) is uncountable|proof]] · [[Numbers and Sets - Chapter 4 Countability#Theorem 11 — No bijection between X and P(X)|proof]]

## Examples

- Finite sets and $\mathbb N$ are countable. $\mathbb Z$ is countable via the list $0,1,-1,2,-2,\dots$ → [[Numbers and Sets - Chapter 4 Countability#Examples — countable sets|lecture]]

## Related

[[Bijections and Permutations]] · [[Sets and Set Operations]]
