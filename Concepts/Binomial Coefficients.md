---
title: Binomial Coefficients
course: Part IA Numbers and Sets
material_type: concept note
tags: [concept, numbers-and-sets]
---

# Binomial Coefficients

> [!abstract] In one paragraph
> $\binom nk$ counts the $k$-element subsets of an $n$-element set. Counting arguments give its properties directly: summing over all sizes gives $2^n$, choosing what to leave out gives symmetry, splitting on whether $n$ is chosen gives Pascal's rule, and choosing in order then forgetting the order gives $\frac{n!}{k!(n-k)!}$. Counting brackets gives the binomial theorem.

## Definitions

- **Size** $|A|$ of a finite set; $|\mathcal P(A)|=2^{|A|}$. → [[Numbers and Sets - Chapter 3 Sets, Functions and Relations#Proposition 1 — Number of subsets|proof]]
- **Binomial coefficient** $\binom nk=|\{S\subseteq\{1,\dots,n\}:|S|=k\}|$. → [[Numbers and Sets - Chapter 3 Sets, Functions and Relations#Definition — Binomial coefficient|lecture]]

## Key results

- $\sum_k\binom nk=2^n$; $\binom nk=\binom n{n-k}$; $\binom nk=\binom{n-1}{k-1}+\binom{n-1}k$ (Pascal's triangle). → [[Numbers and Sets - Chapter 3 Sets, Functions and Relations#Definition — Binomial coefficient|lecture]]
- **Proposition 2.** $\binom nk=\frac{n(n-1)\cdots(n-k+1)}{k!}=\frac{n!}{k!(n-k)!}$; e.g. $\binom n2\sim\frac{n^2}2$. → [[Numbers and Sets - Chapter 3 Sets, Functions and Relations#Proposition 2 — Formula for binomial coefficients|proof]]
- **Theorem 3 — Binomial theorem.** $(a+b)^n=\sum_{k=0}^n\binom nka^{n-k}b^k$: choose the $k$ brackets that contribute $b$. → [[Numbers and Sets - Chapter 3 Sets, Functions and Relations#Theorem 3 — Binomial theorem|proof]]

## Related

[[Sets and Set Operations]] · [[Natural Numbers and Mathematical Induction]] · [[Bijections and Permutations]]
