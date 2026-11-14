---
title: Numbers and Sets - Chapter 3 Sets, Functions and Relations
course: Part IA Numbers and Sets
material_type: lecture notes
chapter: 3
source_file: Ch.3 Sets, Functions - Relations.pdf
drive_file_id: 1iMCFeTADIaJQqZXQzoe5nH-xhyhu1dEZ
source_url: https://drive.google.com/file/d/1iMCFeTADIaJQqZXQzoe5nH-xhyhu1dEZ/view
source_pages: 7
tags: [lecture, numbers-and-sets]
---

# Numbers and Sets — Chapter 3: Sets, Functions and Relations

> [!abstract] Overview
> The basic language of sets: membership, equality, subsets, set-builder notation, union, intersection and difference, the distributive laws, unions and intersections of families of sets, ordered pairs and Cartesian products, and power sets. Russell's paradox shows why sets must be built from known sets. Then finite sets: a set of size $n$ has $2^n$ subsets, binomial coefficients, Pascal's triangle and the binomial theorem.
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
| [[#Russell's paradox]] | $\{x:x\notin x\}$ is not a set; no universal set | 3–4 |
| [[#Definition — Finite set and size]] | size $n$, $\lvert A\rvert$; finite / infinite | 4 |
| [[#Proposition 1 — Number of subsets]] | $\lvert A\rvert=n\Rightarrow\lvert\mathcal P(A)\rvert=2^n$ (two proofs) | 4–5 |
| [[#Definition — Binomial coefficient]] | $\binom nk$ = number of $k$-subsets; symmetry; Pascal's rule | 5–6 |
| [[#Proposition 2 — Formula for binomial coefficients]] | $\binom nk=\frac{n!}{k!(n-k)!}$ | 6–7 |
| [[#Theorem 3 — Binomial theorem]] | $(a+b)^n=\sum_k\binom nka^{n-k}b^k$ | 7 |

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

### Russell's paradox

**Warning.** Given a set $A$, we can form $\{x\in A:P(x)\}$ for any property $P$. But we cannot form $\{x:P(x)\}$. Indeed, suppose
$$X=\{x:x\text{ is a set and }x\notin x\}$$
were a set. Then $X\in X$ implies $X\notin X$, a contradiction; on the other hand, $X\notin X$ implies $X\in X$. This is known as **Russell's paradox**.

Similarly, there is no "universal" set $Y$, meaning a set $Y$ with $x\in Y$ for all $x$: otherwise we could form $X$ above by subset selection, $X=\{x\in Y:x\notin x\}$.

**Moral.** To guarantee that a set exists, it should be obtained from known sets (e.g. $\mathbb N$, $\mathbb R$) in one of the ways discussed.

## 3.2 Finite sets

### Definition — Finite set and size

Write $\mathbb N_0=\mathbb N\cup\{0\}=\{0,1,2,3,\dots\}$. Given $n\in\mathbb N_0$, a set $A$ has **size** $n$ if we can write $A=\{a_1,a_2,\dots,a_n\}$ with the elements $a_i$ distinct. E.g. $\{1,3,7\}$ has size $3$, and $\varnothing$ has size $0$.

$A$ is **finite** if there is $n\in\mathbb N_0$ such that $A$ has size $n$, and **infinite** otherwise. If $A$ has size $n$ we write $|A|=n$ or $\#A=n$.

### Proposition 1 — Number of subsets

A set of size $n$ has exactly $2^n$ subsets, i.e. $|A|=n\Rightarrow|\mathcal P(A)|=2^n$.

**Proof 1.** We may assume that our set is $\{1,2,\dots,n\}$. To choose a subset $S$, we must specify whether $1\in S$ or $1\notin S$, then whether $2\in S$ or $2\notin S$, and so on. Hence the number of choices for $S$ is
$$\underbrace{2}_{1\in S?}\cdot\underbrace{2}_{2\in S?}\cdot\underbrace{2}_{3\in S?}\cdots=2^n.$$

**Proof 2.** By induction on $n$; clearly true for $n=0$. Given $n>0$ and $T\subseteq\{1,2,\dots,n-1\}$, how many $S\subseteq\{1,2,\dots,n\}$ are there with $S\cap\{1,2,\dots,n-1\}=T$? There are exactly $2$, namely $T$ and $T\cup\{n\}$. Hence
$$\begin{aligned}
\#\{\text{subsets of }\{1,\dots,n\}\}&=2\times\#\{\text{subsets of }\{1,\dots,n-1\}\}\\
&=2\cdot2^{n-1} &&(\text{induction hypothesis})\\
&=2^n.
\end{aligned}$$

### Definition — Binomial coefficient

Given $n\in\mathbb N_0$ and $0\le k\le n$, write $\binom nk$ for the number of subsets of an $n$-element set that are of size $k$. In other words,
$$\binom nk=\big|\{S\subseteq\{1,2,\dots,n\}:|S|=k\}\big|.$$
$\binom nk$ is called a **binomial coefficient**. By definition
$$\binom n0=1,\qquad\binom nn=1,\qquad\binom n1=n\ \ (n>0),$$
and, counting the subsets by size,
$$\underbrace{\binom n0}_{\text{size }0}+\underbrace{\binom n1}_{\text{size }1}+\dots+\underbrace{\binom n{n-1}}_{\text{size }n-1}+\underbrace{\binom nn}_{\text{size }n}=2^n.$$

**Symmetry.** $\binom nk=\binom n{n-k}$ for all $n\in\mathbb N$, $0\le k\le n$; e.g. $\binom83=\binom85$. Indeed, specifying which $k$ elements to pick is the same as specifying which $n-k$ elements **not** to pick.

**Pascal's rule.**
$$\binom nk=\binom{n-1}{k-1}+\binom{n-1}k\qquad\text{for all }n\in\mathbb N,\ 1\le k\le n-1,$$
e.g. $\binom83=\binom72+\binom73$. Indeed, the number of subsets of $\{1,2,\dots,n\}$ of size $k$ that do not include $n$ is $\binom{n-1}k$, while the number that do include $n$ is $\binom{n-1}{k-1}$.

This gives **Pascal's triangle**:

```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[x=0.75cm,y=0.6cm]
  \foreach \n/\row in {0/{1},1/{1,1},2/{1,2,1},3/{1,3,3,1},4/{1,4,6,4,1},5/{1,5,10,10,5,1}} {
    \foreach \v [count=\k from 0] in \row {
      \node at ({\k-\n/2},{-\n}) {$\v$};
    }
  }
  \draw[->,red,thick] (-1.35,-3.35) -- (-1.1,-3.7);
  \draw[->,red,thick] (-0.65,-3.35) -- (-0.9,-3.7);
\end{tikzpicture}
\end{document}
```
*Pascal's triangle (rows $n=0$ to $5$): each row starts and ends with $1$, and each other entry is the sum of the two entries immediately above (e.g. $4=1+3$).*

### Proposition 2 — Formula for binomial coefficients

$$\binom nk=\frac{n(n-1)\cdots(n-k+1)}{k(k-1)\cdots2\cdot1}=\frac{n!}{k!\,(n-k)!}.$$

**Proof.** Given a set of size $n$, there are $n(n-1)(n-2)\cdots(n-k+1)$ ways to pick $k$ elements in order, one by one. But each subset of size $k$ is picked in $k(k-1)(k-2)\cdots2\cdot1$ ways by this method. Hence the number of subsets of size $k$ in $\{1,2,\dots,n\}$ is $\frac{n(n-1)\cdots(n-k+1)}{k(k-1)\cdots2\cdot1}$.

Note that the formula tells us, for example, that for large $n$
$$\binom n2=\frac{n(n-1)}{2!}\sim\frac{n^2}2,\qquad\binom n3=\frac{n(n-1)(n-2)}{3\cdot2\cdot1}\sim\frac{n^3}6.$$

### Theorem 3 — Binomial theorem

For all $a,b\in\mathbb R$ and $n\in\mathbb N$,
$$(a+b)^n=\binom n0a^n+\binom n1a^{n-1}b+\dots+\binom n{n-1}ab^{n-1}+\binom nnb^n.$$

**Proof.** When we expand $(a+b)^n=(a+b)(a+b)\cdots(a+b)$, we obtain terms of the form $a^{n-k}b^k$, $0\le k\le n$, and the number of terms of the form $a^{n-k}b^k$ is $\binom nk$, as we must specify the $k$ brackets from which to pick $b$. Hence
$$(a+b)^n=\sum_{k=0}^n\binom nka^{n-k}b^k.$$
