---
title: Bijections and Permutations
course: Part IA Groups
material_type: concept note
tags: [concept, groups]
---

# Bijections and Permutations

> [!abstract] In one paragraph
> A bijection is a function with a two-sided inverse; a permutation is a bijection from a set to itself. Under composition, the permutations of $X$ form the symmetric group $\operatorname{Sym}(X)$; for $X=\{1,\dots,n\}$ this is $S_n$.

## Definitions

- **Bijection** $f:X\to Y$: there is $g:Y\to X$ with $f\circ g=\operatorname{id}_Y$, $g\circ f=\operatorname{id}_X$. Equivalently $f$ is **injective** and **surjective**.
- **Permutation**: a bijection $X\to X$; $\operatorname{Sym}(X)$ = all permutations of $X$; $S_n=\operatorname{Sym}\{1,\dots,n\}$.

→ [[Groups - Chapter 1 Examples and Definitions#Definition 1.9 — Bijection and permutation|lecture]]

## Key results

- **Lemma 1.11.** Composition of functions is associative. → [[Groups - Chapter 1 Examples and Definitions#Lemma 1.11 — Composition is associative|proof]]
- **Lemma 1.12.** $f,f'\in\operatorname{Sym}(X)\Rightarrow f\circ f'\in\operatorname{Sym}(X)$, with inverse $g'\circ g$. → [[Groups - Chapter 1 Examples and Definitions#Lemma 1.12 — Composites of permutations|proof]]
- **Proposition 1.13.** $(\operatorname{Sym}(X),\circ,\operatorname{id}_X)$ is a group.
- **Finite sets.** If $|X|=|Y|<\infty$: bijective $\iff$ injective $\iff$ surjective.

## Pitfalls

- $f\circ g$ means "first $g$, then $f$".
- $f^{-1}$ (inverse function) needs $f$ bijective; it is not $1/f$.

## Cycles (Groups Ch.7)

- **$k$-cycle** $(a_1\,\cdots\,a_k)$; multiply "from the right". Disjoint cycles commute. → [[Groups - Chapter 7 Permutations#Definition 7.1 — k-cycle|lecture]]
- **Theorem 7.3.** Every $\sigma\in S_n$ is a product of disjoint cycles (the orbits of $\langle\sigma\rangle$), unique up to shifting, reordering and singletons; cycle type $\{k_1,\dots,k_\ell\}$, $\operatorname{ord}\sigma=\operatorname{lcm}(k_i)$. → [[Groups - Chapter 7 Permutations#Theorem 7.3 — Disjoint cycle decomposition|proof]]
- **Theorem 7.6 / Lemma 7.8.** Transpositions generate $S_n$; adjacent ones $(i\ i{+}1)$ suffice, via $(i\,j)=(j{-}1\ j)(i\ j{-}1)(j{-}1\ j)$. → [[Groups - Chapter 7 Permutations#Theorem 7.6 — Transpositions generate S_n|proof]] · [[Groups - Chapter 7 Permutations#Lemma 7.8 — Adjacent transpositions suffice|proof]]

## Functions (Numbers and Sets Ch.3)

- A function $f:A\to B$ is a subset of $A\times B$ with exactly one $(x,y)$ for each $x$; injective, surjective, bijective; image $f(A)$, preimage $f^{-1}(Y)$; domain and codomain matter. For finite sets: no surjection onto a bigger set, no injection into a smaller one, and for $f:A\to A$ injective $\iff$ surjective. → [[Numbers and Sets - Chapter 3 Sets, Functions and Relations#Definition — Injective, surjective, bijective|lecture]] · [[Numbers and Sets - Chapter 3 Sets, Functions and Relations#Observations on finite sets|lecture]]

## Related

[[Groups]] · [[Isometries and Dihedral Groups]] · [[Homomorphisms and Isomorphisms]]
