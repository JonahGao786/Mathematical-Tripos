---
title: Numbers and Sets - Chapter 3 Sets, Functions and Relations
course: Part IA Numbers and Sets
material_type: lecture notes
chapter: 3
source_file: Ch.3 Sets, Functions - Relations.pdf
drive_file_id: 1iMCFeTADIaJQqZXQzoe5nH-xhyhu1dEZ
source_url: https://drive.google.com/file/d/1iMCFeTADIaJQqZXQzoe5nH-xhyhu1dEZ/view
source_pages: 15
tags: [lecture, numbers-and-sets]
---

# Numbers and Sets — Chapter 3: Sets, Functions and Relations

> [!abstract] Overview
> The basic language of sets: membership, equality, subsets, set-builder notation, union, intersection and difference, the distributive laws, unions and intersections of families of sets, ordered pairs and Cartesian products, and power sets. Russell's paradox shows why sets must be built from known sets. Then finite sets: a set of size $n$ has $2^n$ subsets, binomial coefficients, Pascal's triangle and the binomial theorem, and the inclusion–exclusion principle. Then functions: injective, surjective and bijective maps, image and preimage, composition, and inverses (invertible $\iff$ bijective). Finally, relations.
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
| [[#Theorem 3 — Binomial theorem]] | $(a+b)^n=\sum_k\binom nka^{n-k}b^k$; $(1+x)^n\approx1+nx$ | 7 |
| [[#Theorem 4 — Inclusion–exclusion principle]] | $\lvert\bigcup S_i\rvert=\sum_r(-1)^{r+1}\sum_{\lvert A\rvert=r}\lvert S_A\rvert$ | 7–9 |
| [[#Definition — Function]] | a subset $f\subseteq A\times B$ with a unique $y$ for each $x$ | 9–10 |
| [[#Definition — Injective, surjective, bijective]] | one-to-one, onto, both | 10 |
| [[#Definition — Domain, codomain, image, preimage]] | $f(A)$, $f^{-1}(Y)$ | 10 |
| [[#Observations on finite sets]] | no surjection if $\lvert B\rvert>\lvert A\rvert$; injective $\iff$ surjective for $f:A\to A$; fails for infinite sets | 11 |
| [[#Further examples — identity and indicator functions]] | $\mathrm{id}_X$, indicator $i_A$, sequences, $+$, size via bijection | 12 |
| [[#Definition — Composition]] | $g\circ f:a\mapsto g(f(a))$; not commutative | 12 |
| [[#Proposition — Composition is associative]] | $h\circ(g\circ f)=(h\circ g)\circ f$ | 13 |
| [[#Definition — Invertible function]] | $g\circ f=\mathrm{id}_A$ and $f\circ g=\mathrm{id}_B$; inverse $f^{-1}$ | 13–14 |
| [[#Theorem — Left and right inverses]] | left inverse $\iff$ injective, right inverse $\iff$ surjective; invertible $\iff$ bijective | 13–14 |
| [[#Definition — Relation]] | $R\subseteq X\times X$, $aRb$ | 15 |

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

**Example.**
$$(1+x)^n=1+nx+\frac{n(n-1)}2x^2+\dots+\binom n{n-1}x^{n-1}+x^n.$$
For small $x$, a good approximation to $(1+x)^n$ is $1+nx$; a better approximation is $1+nx+\frac{n(n-1)}2x^2$.

## 3.3 Inclusion–exclusion

What can we say about the relationship between the sizes of unions and intersections of finite sets? For example,
$$|A\cup B|=|A|+|B|-|A\cap B|$$
(the elements in $A\cap B$ are counted twice in $|A|+|B|$), and
$$|A\cup B\cup C|=|A|+|B|+|C|-|A\cap B|-|A\cap C|-|B\cap C|+|A\cap B\cap C|.$$

### Theorem 4 — Inclusion–exclusion principle

Let $S_1,S_2,\dots,S_n$ be finite sets. Then
$$|S_1\cup S_2\cup\dots\cup S_n|=\sum_{|A|=1}|S_A|-\sum_{|A|=2}|S_A|+\sum_{|A|=3}|S_A|-\dots+(-1)^{n+1}\sum_{|A|=n}|S_A|,$$
where $S_A=\bigcap_{i\in A}S_i$ and $\sum_{|A|=k}$ is taken over all $A\subseteq\{1,2,\dots,n\}$ of size $k$. Equivalently,
$$\Big|\bigcup_{i=1}^nS_i\Big|=\sum_{r=1}^n(-1)^{r+1}\sum_{\substack{A\subseteq\{1,\dots,n\}\\|A|=r}}\Big|\bigcap_{i\in A}S_i\Big|.$$

**Proof.** Let $x\in S_1\cup S_2\cup\dots\cup S_n$, say $x\in S_i$ for $k$ of the $S_i$ ($k\ge1$). We want $x$ to be counted exactly once on the right-hand side. Indeed,
$$\#\{A:|A|=1,\ x\in S_A\}=k,\qquad\#\{A:|A|=2,\ x\in S_A\}=\binom k2,$$
and in general $\#\{A:|A|=r,\ x\in S_A\}=\binom kr$ for $r\le k$, and $0$ for $r>k$. Thus the number of times $x$ is counted on the RHS is
$$\begin{aligned}
k-\binom k2+\binom k3-\dots+(-1)^{k+1}\binom kk&=1-\Big(1-k+\binom k2-\binom k3+\dots+(-1)^k\binom kk\Big)\\
&=1-\big(1+(-1)\big)^k &&(\text{binomial theorem})\\
&=1\qquad\text{for }k\ge1.
\end{aligned}$$

> [!note] Explanation
> $x\in S_A$ exactly when every $S_i$ with $i\in A$ contains $x$, i.e. when $A$ is a subset of the $k$ indices whose sets contain $x$; there are $\binom kr$ such $A$ of size $r$. The alternating sum $\sum_{r=0}^k(-1)^r\binom kr$ is $(1-1)^k=0$, so leaving out the $r=0$ term (which is $1$) gives exactly $1$.

**Remark.** One can also prove this using the **indicator function**: if $A\subseteq X$, then
$$i_A:X\to\{0,1\},\qquad x\mapsto\begin{cases}1,&x\in A,\\0,&x\notin A.\end{cases}$$
Note that $|A|=\sum_{x\in X}i_A(x)$. One uses identities such as $i_{A\cap B}=i_A\cdot i_B$.

## 3.4 Functions

### Definition — Function

Given sets $A$ and $B$, a **function** $f$ from $A$ to $B$ is a "rule" that assigns to every $x\in A$ a unique element $f(x)\in B$.

More formally, a function from $A$ to $B$ is a subset $f\subseteq A\times B$ such that for all $x\in A$ there is a unique $y\in B$ with $(x,y)\in f$. If $f$ is a function from $A$ to $B$, we write $f:A\to B$; if $(x,y)\in f$, we write $f(x)=y$, or $x\mapsto y$.

**Examples.**
1. $f:\mathbb R\to\mathbb R$, $x\mapsto x^2$ is a function.
2. $f:\mathbb R\to\mathbb R$, $x\mapsto\frac1x$ is not a function: $f(0)=\ ?$
3. $f:\mathbb R\to\mathbb R$, $x\mapsto\pm\sqrt{|x|}$ is not a function (the value is not unique).
4. $f:\mathbb R\to\mathbb R$, $x\mapsto\begin{cases}1&\text{if }x\in\mathbb Q,\\0&\text{otherwise}\end{cases}$ is a function.
5. A function $f:\{1,2,3,4,5\}\to\{1,2,3,4\}$:

```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[>=latex]
  \draw (0,0) ellipse (0.6 and 1.5); \draw (3,0) ellipse (0.6 and 1.3);
  \foreach \i in {1,...,5} {\fill (0,{1.2-0.6*(\i-1)}) circle (1.5pt) node[left] {\small$\i$};}
  \foreach \j in {1,...,4} {\fill (3,{0.9-0.6*(\j-1)}) circle (1.5pt) node[right] {\small$\j$};}
  \foreach \i/\j in {1/2,2/1,3/4,4/3,5/3} {\draw[blue,->,shorten >=2pt] (0,{1.2-0.6*(\i-1)}) -- (3,{0.9-0.6*(\j-1)});}
\end{tikzpicture}
\end{document}
```
*A function from a $5$-element set to a $4$-element set: every point on the left sends exactly one arrow (here $4$ and $5$ both go to $3$).*

### Definition — Injective, surjective, bijective

- $f:A\to B$ is **injective** if for all $a,a'\in A$, $a\ne a'\Rightarrow f(a)\ne f(a')$. Equivalently, $f(a)=f(a')\Rightarrow a=a'$.
- $f:A\to B$ is **surjective** if for all $b\in B$ there is $a\in A$ with $f(a)=b$.
- $f:A\to B$ is **bijective** if it is both injective and surjective.

If $f:A\to B$ is a bijection, then everything in $B$ is "hit" exactly once (i.e. $f$ pairs up the elements of $A$ and $B$). A **permutation** of $A$ is a bijection $A\to A$.

### Definition — Domain, codomain, image, preimage

Given $f:A\to B$, $A$ is the **domain** of $f$ and $B$ is the **range** (or **codomain**). The **image** of $f$ is the set
$$f(A)=\{f(a):a\in A\}=\{b\in B:f(a)=b\text{ for some }a\in A\},$$
often denoted $\operatorname{im}(f)$. If $Y\subseteq B$, the **preimage** of $Y$ under $f$ is $f^{-1}(Y)=\{a\in A:f(a)\in Y\}$.

E.g. if $f:\mathbb R\to\mathbb R$, $x\mapsto x^2$, then $\operatorname{im}(f)=\{y\in\mathbb R:y\ge0\}$ and $f^{-1}(\{1\})=\{1,-1\}$.

**Warning.** When specifying a function we must specify its domain and codomain. E.g. "Is the function $f(x)=x^2$ injective?" is meaningless, as $f:\mathbb N\to\mathbb N$, $x\mapsto x^2$ is injective but $f:\mathbb Z\to\mathbb Z$, $x\mapsto x^2$ is not.

### Observations on finite sets

For finite sets $A$ and $B$:
1. $f$ is surjective if and only if $f(A)=B$. In particular, if $|B|>|A|$, there can be no surjective functions from $A$ to $B$.
2. There is no injection from $A$ to $B$ if $|A|>|B|$.
3. If $f:A\to A$, then $f$ is injective $\iff$ $f$ is surjective.
4. There is no bijection from $A$ to any proper subset of $A$.

**(3) and (4) fail for infinite sets.**
1. $f:\mathbb N\to\mathbb N$, $x\mapsto x+1$ is injective but not surjective.
2. $g:\mathbb N\to\mathbb N$, $x\mapsto\begin{cases}x-1&\text{if }x\ne1,\\1&\text{if }x=1\end{cases}$ is surjective but not injective.
3. $h:\mathbb N\to\mathbb N\setminus\{1\}$, $x\mapsto x+1$ is a bijection from $\mathbb N$ to a proper subset.

> [!note] Explanation
> The observations rely on $A$ being finite: $|f(A)|\le|A|$, with equality exactly when $f$ is injective. In example 2, $g(1)=g(2)=1$, and every $n$ is hit since $n=g(n+1)$.

### Further examples — identity and indicator functions

1. For any set $X$, the **identity function** on $X$ is $\mathrm{id}_X:X\to X$, $x\mapsto x$.
2. Given a set $X$ and $A\subseteq X$, the **indicator function** (or **characteristic function**) of $A$ is
$$i_A:X\to\{0,1\},\qquad x\mapsto\begin{cases}1&\text{if }x\in A,\\0&\text{otherwise.}\end{cases}$$
3. A sequence of reals $x_1,x_2,\dots$ is a function $\mathbb N\to\mathbb R$, $n\mapsto x_n$.
4. The operation $+$ on $\mathbb N$ is a function $\mathbb N\times\mathbb N\to\mathbb N$, sending $(a,b)\mapsto a+b$.
5. A set $X$ has size $n$ if and only if there is a bijection $\{1,2,\dots,n\}\to X=\{a_1,a_2,\dots,a_n\}$, $i\mapsto a_i$.

### Definition — Composition

Given $f:A\to B$ and $g:B\to C$, the **composition** is
$$g\circ f:A\to C,\qquad a\mapsto g(f(a)).$$

**Example.** If $f:\mathbb R\to\mathbb R$, $x\mapsto2x$ and $g:\mathbb R\to\mathbb R$, $x\mapsto x+1$, then
$$g\circ f(x)=g(f(x))=2x+1,\qquad f\circ g(x)=f(g(x))=2x+2.$$
So in general $\circ$ is not commutative: here $f\circ g\ne g\circ f$, since $f\circ g(1)=4\ne3=g\circ f(1)$.

### Proposition — Composition is associative

Given $f:A\to B$, $g:B\to C$ and $h:C\to D$,
$$h\circ(g\circ f)=(h\circ g)\circ f.$$

**Proof.** For every $x\in A$,
$$\begin{aligned}
\big(h\circ(g\circ f)\big)(x)&=h\big((g\circ f)(x)\big)=h\big(g(f(x))\big),\\
\big((h\circ g)\circ f\big)(x)&=(h\circ g)\big(f(x)\big)=h\big(g(f(x))\big).
\end{aligned}$$

We may therefore drop the brackets and write $h\circ g\circ f$ without ambiguity.

### Definition — Invertible function

$f:A\to B$ is **invertible** if there exists $g:B\to A$ such that $g\circ f=\mathrm{id}_A$ and $f\circ g=\mathrm{id}_B$. We write $f^{-1}:B\to A$ for the inverse of $f$ when it exists.

**Example.** $f:\mathbb R\to\mathbb R$, $x\mapsto2x+1$ and $g:\mathbb R\to\mathbb R$, $x\mapsto\frac{x-1}2$. For all $x\in\mathbb R$,
$$(g\circ f)(x)=g(2x+1)=x,\qquad(f\circ g)(x)=f\Big(\frac{x-1}2\Big)=x,$$
so $g\circ f=\mathrm{id}_{\mathbb R}$ and $f\circ g=\mathrm{id}_{\mathbb R}$. Hence $f$ is invertible with inverse $g$.

**Warning.** Both conditions are needed. For $f:\mathbb N\to\mathbb N$, $x\mapsto x+1$ and $g:\mathbb N\to\mathbb N$, $x\mapsto\begin{cases}x-1&\text{if }x\ne1,\\1&\text{if }x=1,\end{cases}$ we have $g\circ f=\mathrm{id}_{\mathbb N}$ but $f\circ g\ne\mathrm{id}_{\mathbb N}$, because $f\circ g(1)=2\ne1$.

**Warning.** The preimage $f^{-1}(Y)$ of a set always exists, but the inverse function $f^{-1}$ may not.

### Theorem — Left and right inverses

Let $f:A\to B$.
1. There is $g:B\to A$ with $g\circ f=\mathrm{id}_A$ if and only if $f$ is injective.
2. There is $g:B\to A$ with $f\circ g=\mathrm{id}_B$ if and only if $f$ is surjective.

It follows that $f:A\to B$ is invertible if and only if $f$ is bijective.

```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[>=latex]
  \draw (0,0) ellipse (0.5 and 0.9); \draw (2.6,0) ellipse (0.5 and 0.9);
  \node at (0,1.2) {$A$}; \node at (2.6,1.2) {$B$};
  \draw[red] (2.6,0.25) circle (0.32); \fill (2.5,0.25) circle (1.3pt) node[right=0pt] {\scriptsize$b$};
  \draw[red,<-] (2.92,0.32) -- (3.5,0.5) node[right] {\small$f(A)$};
  \draw[blue,->] (0.7,0.9) to[bend left=20] node[above] {\small$f$} (1.9,0.9);
  \draw[blue,->] (1.9,-0.9) to[bend left=20] node[below] {\small$g\,?$} (0.7,-0.9);
  \node at (1.3,-1.8) {\small $g\circ f=\mathrm{id}_A$};
  \begin{scope}[xshift=6cm]
  \draw (0,0) ellipse (0.5 and 0.9); \draw (2.6,0) ellipse (0.5 and 0.9);
  \node at (0,1.2) {$A$}; \node at (2.6,1.2) {$B$};
  \draw[blue,->] (0.7,0.9) to[bend left=20] node[above] {\small$f$} (1.9,0.9);
  \draw[blue,->] (1.9,-0.9) to[bend left=20] node[below] {\small$g\,?$} (0.7,-0.9);
  \node at (1.3,-1.8) {\small $f\circ g=\mathrm{id}_B$};
  \end{scope}
\end{tikzpicture}
\end{document}
```
*Left: a left inverse must send each $b\in f(A)$ back to the point it came from. Right: a right inverse must pick, for each $b\in B$, a point of $A$ mapping to it.*

**Proof.**
1. ($\Rightarrow$) If such a $g$ exists and $a,a'\in A$ with $f(a)=f(a')$, then $g(f(a))=g(f(a'))$, so $a=a'$. Thus $f$ must be injective.
   ($\Leftarrow$) If $f$ is injective, define $g$ as follows. If $b\in f(A)$, let $g(b)=a$, where $a$ is the unique element of $A$ with $f(a)=b$. If $b\notin f(A)$, let $g(b)$ be anything you like.
2. ($\Rightarrow$) We need $f(g(B))=B$, so $f$ must be surjective.
   ($\Leftarrow$) If $f$ is surjective, then for each $b\in B$ pick some $a\in A$ with $f(a)=b$ and put $g(b)=a$. Then $f\circ g=\mathrm{id}_B$.

For the last statement: if $f$ is bijective, the $g$ from 1 sends each $b$ to its unique preimage, so it also satisfies $f\circ g=\mathrm{id}_B$; conversely an inverse is both a left and a right inverse, so $f$ is injective and surjective.

> [!note] Explanation
> In 1, "anything you like" needs $A$ to have at least one element: if $A=\varnothing$ and $B\ne\varnothing$ there is no function $B\to A$ at all. In 2, $f(g(B))\subseteq f(A)$, so $f(g(B))=B$ forces $f(A)=B$.

## 3.5 Relations

### Definition — Relation

A **relation** on a set $X$ is a subset $R\subseteq X\times X$. We usually write $aRb$ ("$a$ is related to $b$") for $(a,b)\in R$.

**Examples of relations on $\mathbb N$.**
1. $aRb$ if $a,b$ have the same final digit.
2. $aRb$ if $a\mid b$.
3. $aRb$ if $a\ne b$.
4. $aRb$ if $a=b=1$.
5. $aRb$ if $|a-b|\le3$.
