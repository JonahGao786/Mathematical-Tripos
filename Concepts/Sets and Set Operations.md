---
title: Sets and Set Operations
course: Part IA Numbers and Sets
material_type: concept note
tags: [concept, numbers-and-sets]
---

# Sets and Set Operations

> [!abstract] In one paragraph
> A set is determined by its elements alone (order and repetition don't matter), so two sets are equal exactly when each is a subset of the other. New sets are built by union, intersection, difference, Cartesian product and power set; identities between them are proved by showing inclusion both ways.

## Definitions

- **Equality, subset, proper subset:** $A=B\iff(x\in A\Leftrightarrow x\in B)$; $B\subseteq A$ if every element of $B$ is in $A$. → [[Numbers and Sets - Chapter 3 Sets, Functions and Relations#Definition — Set, membership and equality|lecture]] · [[Numbers and Sets - Chapter 3 Sets, Functions and Relations#Definition — Subset|lecture]]
- **Union, intersection, difference:** $A\cup B$, $A\cap B=\{x\in A:x\in B\}$, $A\setminus B=\{x\in A:x\notin B\}$; disjoint if $A\cap B=\varnothing$. → [[Numbers and Sets - Chapter 3 Sets, Functions and Relations#Definition — Union, intersection and difference|lecture]]
- **Families:** $\bigcap_{i\in I}A_i$, $\bigcup_{i\in I}A_i$ (an infinite union is not a "limit"). → [[Numbers and Sets - Chapter 3 Sets, Functions and Relations#Definition — Unions and intersections of families|lecture]]
- **Cartesian product** $A\times B$ of ordered pairs, with $(a,b)=\{\{a\},\{a,b\}\}$; **power set** $\mathcal P(X)$ of all subsets. → [[Numbers and Sets - Chapter 3 Sets, Functions and Relations#Definition — Cartesian product|lecture]] · [[Numbers and Sets - Chapter 3 Sets, Functions and Relations#Definition — Power set|lecture]]

## Key results

- **Distributive laws** $A\cap(B\cup C)=(A\cap B)\cup(A\cap C)$, $A\cup(B\cap C)=(A\cup B)\cap(A\cup C)$. *Idea:* LHS $\subseteq$ RHS and RHS $\subseteq$ LHS, element by element. → [[Numbers and Sets - Chapter 3 Sets, Functions and Relations#Distributive laws|proof]]

- **Russell's paradox.** $\{x:x\notin x\}$ cannot be a set, so there is no universal set; build sets from known sets by subset selection and the constructions above. → [[Numbers and Sets - Chapter 3 Sets, Functions and Relations#Russell's paradox|lecture]]
- **Finite sets** and counting subsets: see [[Binomial Coefficients]].

## Related

[[Logical Connectives and Quantifiers]] · [[Bijections and Permutations]] · [[Real Numbers and the Least Upper Bound Axiom]]
