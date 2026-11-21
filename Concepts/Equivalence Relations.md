---
title: Equivalence Relations
course: Part IA Numbers and Sets
material_type: concept note
tags: [concept, numbers-and-sets]
---

# Equivalence Relations

> [!abstract] In one paragraph
> A relation on $X$ is a subset $R\subseteq X\times X$. It is an equivalence relation if it is reflexive, symmetric and transitive. Then the equivalence classes $[x]=\{y:y\sim x\}$ are pairwise disjoint or equal and cover $X$, so they form a partition. Conversely every partition comes from an equivalence relation. The set of classes is the quotient $X/R$, and the quotient map $q:x\mapsto[x]$ sends each element to its class.

## Definitions

- **Relation** $R\subseteq X\times X$, written $aRb$. → [[Numbers and Sets - Chapter 3 Sets, Functions and Relations#Definition — Relation|lecture]]
- **Reflexive, symmetric, transitive.** → [[Numbers and Sets - Chapter 3 Sets, Functions and Relations#Definition — Reflexive, symmetric, transitive|lecture]]
- **Equivalence relation** (all three), **equivalence class** $[x]$, **partition** (pairwise disjoint parts with union $X$). → [[Numbers and Sets - Chapter 3 Sets, Functions and Relations#Definition — Equivalence relation and equivalence class|lecture]]
- **Quotient** $X/R=\{[x]:x\in X\}$ and **quotient map** $q:X\to X/R$. → [[Numbers and Sets - Chapter 3 Sets, Functions and Relations#Definition — Quotient and quotient map|lecture]]

## Key results

- **Theorem 5.** The equivalence classes partition $X$. *Idea:* $x\in[x]$ by reflexivity; if $z\in[x]\cap[y]$ then $x\sim y$ by symmetry and transitivity, and then $[x]=[y]$. Conversely, "lying in the same part" is an equivalence relation. → [[Numbers and Sets - Chapter 3 Sets, Functions and Relations#Theorem 5 — Equivalence classes partition X|proof]]

## Examples

- Same final digit on $\mathbb N$: $10$ classes. Congruence mod $5$ on $\mathbb Z$: $5$ classes, $\mathbb Z/5\mathbb Z$. $(a,b)\sim(c,d)\iff ad=bc$ on $\mathbb Z\times\mathbb N$: the classes are the rationals $\frac ab$.
- Similarity of matrices is an equivalence relation. → [[Vectors and Matrices - Chapter 4 Eigenvalues and Eigenvectors#Proposition — Similarity is an equivalence relation|proof]]

## Related

[[Sets and Set Operations]] · [[Modular Arithmetic]] · [[Normal Subgroups and Quotients]] · [[Cosets and Lagrange's Theorem]]
