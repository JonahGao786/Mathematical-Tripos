---
title: Numbers and Sets - Chapter 3 Sets, Functions and Relations
course: Part IA Numbers and Sets
material_type: lecture notes
chapter: 3
source_file: Ch.3 Sets, Functions - Relations.pdf
drive_file_id: 1iMCFeTADIaJQqZXQzoe5nH-xhyhu1dEZ
source_url: https://drive.google.com/file/d/1iMCFeTADIaJQqZXQzoe5nH-xhyhu1dEZ/view
source_pages: 3
tags: [lecture, numbers-and-sets]
---

# Numbers and Sets — Chapter 3: Sets, Functions and Relations

> [!abstract] Overview
> The basic language of sets: membership, equality, subsets, set-builder notation, union, intersection and difference, the distributive laws, unions and intersections of families of sets, ordered pairs and Cartesian products, and power sets.
> Prerequisite: [[Logical Connectives and Quantifiers]].

## Results index

| Result | Statement in brief | Page |
| --- | --- | --- |
| [[#Definition — Set, membership and equality]] | $A=B\iff(x\in A\Leftrightarrow x\in B)$; one empty set | 1 |
| [[#Definition — Subset]] | $B\subseteq A$; proper subset; $A=B\iff A\subseteq B$ and $B\subseteq A$ | 1 |
| [[#Definition — Union, intersection and difference]] | $A\cup B$, $A\cap B$, $A\setminus B$; disjoint | 1–2 |
| [[#Distributive laws]] | $A\cap(B\cup C)=(A\cap B)\cup(A\cap C)$ and dually | 2 |
| [[#Definition — Unions and intersections of families]] | $\bigcap_{n}A_n$, $\bigcup_{n}A_n$, $\bigcap_{i\in I}A_i$, $\bigcup_{i\in I}A_i$ | 2–3 |
| [[#Definition — Cartesian product]] | $A\times B=\{(a,b):a\in A,\ b\in B\}$ | 3 |
| [[#Definition — Power set]] | $\mathcal P(X)=\{Y:Y\subseteq X\}$ | 3 |

## 3.1 Sets

### Definition — Set, membership and equality

A **set** is a collection of mathematical objects, e.g. $\mathbb R$, $\mathbb N$, $\{1,5,9\}$, $[-2,3]$. The order of the elements in a set is immaterial, and elements are counted only once, e.g.
$$\{1,3,7\}=\{1,7,3\},\qquad\{3,4,4,8\}=\{3,4,8\}.$$
We write $x\in A$ if $x$ is an element of the set $A$, and $x\notin A$ if not.

Two sets are **equal** if they have the same elements, that is,
$$A=B\iff(x\in A\Leftrightarrow x\in B).$$
In particular, there is only one empty set $\varnothing$.

### Definition — Subset

A set $B$ is a **subset** of $A$, written "$B\subseteq A$" or "$B\subset A$", if every element of $B$ is an element of $A$. $B$ is a **proper subset** of $A$ if $B\subseteq A$ and $B\ne A$ (also written "$B\subsetneq A$").

Note that $A=B$ if and only if $A\subseteq B$ and $B\subseteq A$.

**Set-builder notation.** If $A$ is a set and $P$ is a property of (some) elements of $A$, we write $\{x\in A:P(x)\}$ for the subset of $A$ comprising those elements for which $P(x)$ holds, e.g.
$$\{n\in\mathbb N:n\text{ is prime}\}=\{2,3,5,7,\dots\}\subseteq\mathbb N.$$

### Definition — Union, intersection and difference

If $A$ and $B$ are sets, their **union** is $A\cup B=\{x:x\in A\text{ or }x\in B\}$, and their **intersection** is $A\cap B=\{x:x\in A\text{ and }x\in B\}$. We say $A$ and $B$ are **disjoint** if $A\cap B=\varnothing$.

Note that we can view intersection as a special case of subset selection, $A\cap B=\{x\in A:x\in B\}$. Similarly we have the **set difference**
$$A\setminus B=\{x\in A:x\notin B\}.$$

```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}
  \begin{scope}[xshift=0cm]
    \fill[blue!25] (0,0) circle (1); \fill[blue!25] (1.2,0) circle (1);
    \draw (0,0) circle (1) (1.2,0) circle (1);
    \node at (-0.45,0.75) {$A$}; \node at (1.65,0.75) {$B$};
    \node at (0.6,-1.35) {$A\cup B$};
  \end{scope}
  \begin{scope}[xshift=4.2cm]
    \begin{scope} \clip (0,0) circle (1); \fill[blue!25] (1.2,0) circle (1); \end{scope}
    \draw (0,0) circle (1) (1.2,0) circle (1);
    \node at (-0.45,0.75) {$A$}; \node at (1.65,0.75) {$B$};
    \node at (0.6,-1.35) {$A\cap B$};
  \end{scope}
  \begin{scope}[xshift=8.4cm]
    \fill[blue!25] (0,0) circle (1); \fill[white] (1.2,0) circle (1);
    \draw (0,0) circle (1) (1.2,0) circle (1);
    \node at (-0.45,0.75) {$A$}; \node at (1.65,0.75) {$B$};
    \node at (0.6,-1.35) {$A\setminus B$};
  \end{scope}
\end{tikzpicture}
\end{document}
```
*Union, intersection and difference of two sets (shaded).*

Note that $\cup$ and $\cap$ are commutative and associative.

### Distributive laws

$\cup$ is distributive over $\cap$, and $\cap$ is distributive over $\cup$:
$$A\cup(B\cap C)=(A\cup B)\cap(A\cup C),\qquad A\cap(B\cup C)=(A\cap B)\cup(A\cap C).$$

**Proof** (of the second). To prove $A\cap(B\cup C)=(A\cap B)\cup(A\cap C)$, show that LHS $\subseteq$ RHS and RHS $\subseteq$ LHS.
- If $x\in A\cap(B\cup C)$, then $x\in A$ and $x\in B\cup C$, so $x\in A$ and ($x\in B$ or $x\in C$). If $x\in B$, then $x\in A\cap B$; or if $x\in C$, then $x\in A\cap C$. In any case, $x\in(A\cap B)\cup(A\cap C)$.
- Conversely, if $x\in(A\cap B)\cup(A\cap C)$, then $x\in A\cap B$ or $x\in A\cap C$. If $x\in A\cap B$, then $x\in A$ and $x\in B\cup C$. If $x\in A\cap C$, then $x\in A$ and $x\in B\cup C$. So in any case $x\in A\cap(B\cup C)$.

### Definition — Unions and intersections of families

If $A_1,A_2,\dots$ are sets, then
$$\bigcap_{n=1}^\infty A_n=A_1\cap A_2\cap A_3\cap\cdots=\{x:x\in A_n\ \forall n\in\mathbb N\},$$
$$\bigcup_{n=1}^\infty A_n=A_1\cup A_2\cup\cdots=\{x:x\in A_n\text{ for some }n\in\mathbb N\}.$$
**Warning:** $\bigcup_{n=1}^\infty A_n$ is **not** the "limit" of anything.

More generally, given an index set $I$ and a collection of sets $A_i$ indexed by $i\in I$, we write
$$\bigcap_{i\in I}A_i=\{x:x\in A_i\ \forall i\in I\},\qquad\bigcup_{i\in I}A_i=\{x:x\in A_i\text{ for some }i\in I\}.$$

### Definition — Cartesian product

Given sets $A$ and $B$, we can form their **Cartesian product**
$$A\times B=\{(a,b):a\in A\text{ and }b\in B\},$$
the set of ordered pairs $(a,b)$ with $a\in A$, $b\in B$. Note that we can define $(a,b)=\{\{a\},\{a,b\}\}$.

We can extend to ordered triples and so on, e.g.
$$\mathbb R^3=\mathbb R\times\mathbb R\times\mathbb R=\{(x,y,z):x\in\mathbb R,\ y\in\mathbb R,\ z\in\mathbb R\}.$$

> [!note] Explanation
> The point of defining $(a,b)$ as a set is to get the key property of ordered pairs from set equality alone: $(a,b)=(c,d)\iff a=c$ and $b=d$. With $\{\{a\},\{a,b\}\}$, the element $a$ is the one lying in both members, and $b$ is the other element of the two-element member (or $b=a$ if there is only one member).

### Definition — Power set

For any set $X$, we can form the **power set** $\mathcal P(X)$ consisting of all subsets of $X$, i.e.
$$\mathcal P(X)=\{Y:Y\subseteq X\}.$$
E.g. if $X=\{1,2\}$, then $\mathcal P(X)=\{\varnothing,\{1\},\{2\},\{1,2\}\}$.
