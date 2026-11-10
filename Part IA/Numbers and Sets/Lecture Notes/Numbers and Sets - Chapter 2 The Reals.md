---
title: Numbers and Sets - Chapter 2 The Reals
course: Part IA Numbers and Sets
material_type: lecture notes
chapter: 2
source_file: Ch.2 The Reals.pdf
drive_file_id: 1NXO09JT735Tr2NnPTWDvsrkXBMYgGyrC
source_url: https://drive.google.com/file/d/1NXO09JT735Tr2NnPTWDvsrkXBMYgGyrC/view
source_pages: 20
tags: [lecture, numbers-and-sets]
---

# Numbers and Sets — Chapter 2: The Reals

> [!abstract] Overview
> The rationals have a "gap": $\sqrt2$ is not rational, and the set $\{x:x^2<2\}$ has no least upper bound in $\mathbb Q$. The real numbers are defined by field and order axioms together with the least upper bound axiom. Consequences: $\mathbb N$ is unbounded (Archimedes), infima exist, $\sqrt2$ exists in $\mathbb R$, and both the rationals and the irrationals are dense. Finally, sequences and their limits: the $\varepsilon$–$N$ definition, examples, divergence and uniqueness of limits; bounded and monotonic sequences and the monotone convergence theorem; limits of sums and inequalities; series (geometric, harmonic, $\sum\frac1{n^2}$); decimal expansions, and periodic decimals as exactly the rationals; Euler's number $e$ and its irrationality; algebraic and transcendental numbers, with Liouville's theorem.
> Prerequisite: [[Numbers and Sets - Chapter 1 Elementary Number Theory]] (unique factorization).

## Results index

| Result | Statement in brief | Page |
| --- | --- | --- |
| [[#Proposition 1 — No rational square root of 2]] | there is no $x\in\mathbb Q$ with $x^2=2$ (two proofs) | 1 |
| [[#Definition — The real numbers]] | axioms (1)–(6), including the least upper bound axiom | 2 |
| [[#Definition — Upper bound and least upper bound]] | $\sup S$ | 2 |
| [[#Proposition 2 — Axiom of Archimedes]] | $\mathbb N$ is not bounded above in $\mathbb R$ | 5 |
| [[#Corollary 3 — Arbitrarily small 1 over n]] | $t>0\Rightarrow\exists n\in\mathbb N,\ \frac1n<t$ | 5 |
| [[#Definition — Lower bound and greatest lower bound]] | $\inf S=-\sup(-S)$ | 5–6 |
| [[#Theorem 4 — Existence of square root of 2]] | there is $x\in\mathbb R$ with $x^2=2$; likewise $\sqrt[n]x$ | 6–7 |
| [[#Definition — Irrational numbers]] | reals that are not rational; e.g. $2+3\sqrt5$ | 7 |
| [[#Density of the rationals]] | $a<b\Rightarrow\exists c\in\mathbb Q,\ a<c<b$ | 7–8 |
| [[#Density of the irrationals]] | $a<b\Rightarrow\exists c\in\mathbb R\setminus\mathbb Q,\ a<c<b$ | 8 |
| [[#Definition — Sequence]] | $(a_n)_{n=1}^\infty$ | 8 |
| [[#Definition — Limit of a sequence]] | $\forall\varepsilon>0\ \exists N\ \forall n\ge N,\ \lvert a_n-\ell\rvert<\varepsilon$ | 8–9 |
| [[#Definition — Absolute value]] | $\lvert x\rvert$; triangle inequality $\lvert a-c\rvert\le\lvert a-b\rvert+\lvert b-c\rvert$ | 9 |
| [[#Definition — Convergence and divergence]] | $a_n\to\ell$, $\lim a_n=\ell$; $a_n\not\to\ell$ | 9–10 |
| [[#Examples of limits]] | $1-\frac1n\to1$; $0,\frac12,0,\frac14,\dots\to0$; $1-\frac1{2^n}\to1$; $(-1)^n$ diverges | 9–11 |
| [[#Proposition — Uniqueness of limits]] | a sequence has at most one limit | 11 |
| [[#Definition — Bounded sequence]] | $\lvert a_n\rvert\le B$; convergent $\Rightarrow$ bounded | 11 |
| [[#Definition — Monotonic sequence]] | increasing or decreasing | 11 |
| [[#Theorem 5 — Monotone convergence theorem]] | bounded monotonic $\Rightarrow$ convergent | 12 |
| [[#Proposition 6 — Limits preserve weak inequalities]] | $a_n\le d$, $a_n\to c\Rightarrow c\le d$ | 12 |
| [[#Proposition 7 — Limit of a sum]] | $a_n+b_n\to c+d$ | 13 |
| [[#Definition — Partial sums and series]] | $S_k=\sum_{n=1}^ka_n$, $\sum a_n=\lim S_k$ | 13 |
| [[#Examples of series]] | geometric $\sum r^n=\frac r{1-r}$; harmonic $\sum\frac1n$ diverges; $\sum\frac1{n^2}$ converges | 13–14 |
| [[#Definition — Decimal expansion]] | $x=\sum_{n\ge1}\frac{d_n}{10^n}=0.d_1d_2d_3\ldots$, $0\le x\le1$ | 15 |
| [[#Existence of decimal expansions]] | every $0\le x<1$ has a decimal expansion | 15 |
| [[#Non-uniqueness of decimal expansions]] | two expansions differ only as $0.\ldots a_k999\ldots=0.\ldots(a_k+1)000\ldots$ | 16 |
| [[#Periodic decimals are exactly the rationals]] | periodic $\iff$ rational | 16–17 |
| [[#Definition — Euler's number e]] | $e=\sum_{j\ge0}\frac1{j!}$, converges (bounded by $3$) | 17 |
| [[#Proposition 8 — e is irrational]] | $e\notin\mathbb Q$ | 17–18 |
| [[#Definition — Algebraic and transcendental numbers]] | root of a non-zero integer polynomial, or not | 18 |
| [[#Theorem 9 — Liouville's theorem]] | $\sum_{n\ge1}10^{-n!}$ is transcendental | 18–20 |

## 2.1 Why not stop at the rationals?

We have seen $\mathbb N\subset\mathbb Z\subset\mathbb Q$. Why not stop here?

### Proposition 1 — No rational square root of 2

There is no rational $x$ with $x^2=2$.

**Proof 1.** Suppose $x^2=2$. We may assume $x>0$, since $(-x)^2=x^2$. If $x$ is rational then $x=\frac ab$ for some $a,b\in\mathbb N$, so
$$\frac{a^2}{b^2}=2,\qquad\text{i.e.}\qquad a^2=2b^2.$$
But the exponent of $2$ in the prime factorization of $a^2$ is even, while the exponent of $2$ in that of $2b^2$ is odd, contradicting the Fundamental Theorem of Arithmetic.

**Note.** The same proof shows that if there is $x\in\mathbb Q$ with $x^2=n$ for some $n\in\mathbb N$, then $n$ is a square.

**Proof 2.** Suppose $x^2=2$ for some $x=\frac ab$ with $a,b\in\mathbb N$. Then for any $c,d\in\mathbb Z$, $cx+d$ has the form $\frac eb$ for some $e\in\mathbb Z$. Thus
$$cx+d>0\ \Longrightarrow\ cx+d\ge\frac1b.$$
But $1<x<2$, so $0<x-1<1$, and hence for $n$ sufficiently large
$$0<(x-1)^n<\frac1b.$$
Yet for every $n\in\mathbb N$, $(x-1)^n$ has the form $cx+d$ for some $c,d\in\mathbb Z$, because $x^2=2$. This is a contradiction.

So "$\mathbb Q$ has a gap". How do we express this fact making reference only to $\mathbb Q$? $2$ is an upper bound for the set of $x$ with $x^2<2$, but so is $1.5$, and $1.42,\dots$ The crucial point: **in $\mathbb Q$ there is no least upper bound** (the "gap").

```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[>=latex,scale=1.2]
  \draw[->] (-2.8,0) -- (2.9,0) node[right] {$Q$};
  \foreach \x in {-2,-1,0,1,2} {\draw (\x,0.07) -- (\x,-0.07) node[below] {$\x$};}
  \draw[red,thick] (-1.414,0.25) -- (-1.414,0.12) -- (1.414,0.12) -- (1.414,0.25);
  \node[red,above] at (0,0.25) {all $x$ with $x^2<2$};
\end{tikzpicture}
\end{document}
```
*The set of $x$ with $x^2<2$; $2$, $1.5$, $1.42,\dots$ are all upper bounds in $\mathbb Q$, but there is no least one.*


## 2.2 The real numbers

### Definition — The real numbers

The **real numbers**, written $\mathbb R$, are a set with elements $0$ and $1$ ($0\ne1$), equipped with operations $+$ and $\cdot$, and an ordering "$<$", satisfying:

1. $+$ is commutative and associative with identity $0$, and every $x$ has an inverse under $+$;
2. $\cdot$ is commutative and associative with identity $1$, and every $x\ne0$ has an inverse under $\cdot$;
3. $\cdot$ is distributive over $+$: $a\cdot(b+c)=a\cdot b+a\cdot c$ for all $a,b,c$;
4. for all $a,b$, exactly one of $a<b$, $a=b$, $b<a$ holds;
5. for all $a,b,c$: $a<b\Rightarrow a+c<b+c$, and $a<b\Rightarrow ac<bc$ if $c>0$;
6. (**least upper bound axiom**) every non-empty set $S$ of reals that is bounded above has a least upper bound.

### Definition — Upper bound and least upper bound

A set $S\subseteq\mathbb R$ is **bounded above** if there is $x\in\mathbb R$ with $x\ge y$ for all $y\in S$; such an $x$ is an **upper bound** for $S$. We say $x$ is the **least upper bound** for $S$ if $x$ is an upper bound for $S$ and every other upper bound $x'$ satisfies $x'\ge x$. Then we write $x=\operatorname{LUB}(S)$, "$x=$ supremum$(S)$" or $x=\sup(S)$.

**Remarks.**
1. From axioms (1)–(5) we can check, for example, that $0<1$. If not, then $1<0$ (as $0\ne1$), so $0=1-1<0-1=-1$, hence $0=0\times(-1)<(-1)\cdot(-1)=1$, a contradiction.
2. We may regard $\mathbb Q$ as contained in $\mathbb R$ by identifying $\frac ab\in\mathbb Q$ with $a\cdot b^{-1}\in\mathbb R$.
3. $\mathbb Q$ does not satisfy (6): e.g. the set of $x$ with $x^2<2$ has no supremum in $\mathbb Q$.
4. In (6) the words "non-empty" and "bounded above" are crucial. If $S$ is empty, every $x\in\mathbb R$ is an upper bound, so there is no *least* upper bound. If $S$ is not bounded above, it has no upper bound, and certainly no least upper bound.
5. It is possible to construct $\mathbb R$ "out of" $\mathbb Q$ and check that (1)–(6) hold, but it takes effort.

**Examples.**
1. $S=[0,1]=\{x\in\mathbb R:0\le x\le1\}$.
   - $2$ is an upper bound, since $x\le2$ for all $x\in S$.
   - $\frac34$ is not: $\frac78>\frac34$ and $\frac78\in S$.
   - $\sup S=1$: $1$ is an upper bound (all $x\in S$ satisfy $x\le1$), and every other upper bound $y$ satisfies $y\ge1$ because $1\in S$.


```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[>=latex,scale=1.2]
  \draw[->] (-2.8,0) -- (2.9,0) node[right] {$R$};
  \foreach \x in {-2,-1,0,1,2} {\draw (\x,0.07) -- (\x,-0.07) node[below] {$\x$};}
  \draw[very thick,blue] (0,0) -- (1,0);
  \fill[blue] (0,0) circle (1.8pt); \fill[blue] (1,0) circle (1.8pt);
  \node[blue,above] at (0.5,0.1) {$S$};
\end{tikzpicture}
\end{document}
```
*$S=[0,1]$.*

2. $S=(0,1)=\{x\in\mathbb R:0<x<1\}$ is non-empty and bounded above. $\sup S=1$ because:
   - $1$ is an upper bound;
   - no upper bound $c$ satisfies $c<1$. Indeed $c>0$ (in fact $c\ge\frac12$ since $\frac12\in S$), so if $c<1$ then $0<c<1$, and so $\frac{c+1}2\in S$ with $\frac{c+1}2>c$, a contradiction.


```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[>=latex]
  \draw[->] (-0.3,0) -- (4.6,0);
  \draw (0,0.07) -- (0,-0.07) node[below] {$0$};
  \draw (4,0.07) -- (4,-0.07) node[below] {$1$};
  \draw (2.2,0.07) -- (2.2,-0.07) node[below] {$c$};
  \draw[red,->] (3.1,0.6) node[above] {$\frac{c+1}2$} -- (3.1,0.1);
  \draw[very thick,blue] (0,0) -- (4,0);
  \draw[blue,fill=white] (0,0) circle (1.8pt); \draw[blue,fill=white] (4,0) circle (1.8pt);
\end{tikzpicture}
\end{document}
```
*$S=(0,1)$: for $c<1$ the midpoint $\frac{c+1}2$ of $c$ and $1$ lies in $S$ and exceeds $c$.*

## 2.3 Consequences of the least upper bound axiom

**Recap.** $x\in\mathbb R$ is the least upper bound of $S$ if $x$ is an upper bound for $S$ and every other upper bound $y$ satisfies $y\ge x$. If $S$ has a greatest element, then $\sup S=\max S\in S$. But $\sup S$ can exist when $\max S$ doesn't, in which case $\sup S\notin S$.

**Example 3.** Let
$$S=\left\{0,\tfrac12,\tfrac23,\tfrac34,\dots\right\}=\left\{1-\tfrac1n:n\in\mathbb N\right\}.$$
Clearly $1$ is an upper bound. Is there an upper bound $<1$? (Answered after Corollary 3.)

### Proposition 2 — Axiom of Archimedes

$\mathbb N$ is not bounded above in $\mathbb R$.

**Proof.** Suppose on the contrary that $\mathbb N$ is bounded above, and let $c=\sup\mathbb N$. By definition $c-1$ is not an upper bound for $\mathbb N$, so there is $n\in\mathbb N$ with $n>c-1$. But then $n+1\in\mathbb N$ with $n+1>c$, contradicting the fact that $c$ is an upper bound for $\mathbb N$. $\square$

### Corollary 3 — Arbitrarily small 1 over n

For any real $t>0$ there is $n\in\mathbb N$ with $\frac1n<t$.

**Proof.** Given $t>0$, by Proposition 2 there is $n\in\mathbb N$ with $n>\frac1t$. Hence $\frac1n<t$. $\square$

### Definition — Lower bound and greatest lower bound

A set $S$ is **bounded below** if there is $x$ with $x\le y$ for all $y\in S$; such an $x$ is a **lower bound** for $S$.

If $S$ is non-empty and bounded below, then $-S=\{-y:y\in S\}$ is non-empty and bounded above, so it has a least upper bound, $c$ say. Hence $-c$ is the **greatest lower bound** for $S$, written $\operatorname{GLB}(S)$, "infimum$(S)$" or $\inf(S)$.

- Corollary 3 immediately gives $\inf\left\{\frac1n:n\in\mathbb N\right\}=0$.
- Proposition 2 and Corollary 3 show that there are no "infinitely large" or "infinitely small" numbers in $\mathbb R$.

**Back to Example 3.** $\sup S=1$. Suppose $c<1$ is an upper bound for $S$. Then $1-\frac1n\le c$ for all $n\in\mathbb N$, so
$$0<1-c\le\frac1n\qquad\text{for all }n\in\mathbb N,$$
contradicting Corollary 3 (take $t=1-c$). Note $\sup S=1\notin S$: $S$ has no greatest element.

### Theorem 4 — Existence of square root of 2

There exists $x\in\mathbb R$ with $x^2=2$.

**Proof.** Let $S=\{x\in\mathbb R:x^2<2\}$. $S$ is non-empty, since e.g. $1\in S$, and bounded above, e.g. by $2$. Hence $S$ has a supremum, $c$ say. Observe that $1<c<2$. We claim $c^2=2$.

*Suppose $c^2<2$.* For $0<t<1$,
$$\begin{aligned}
(c+t)^2&=c^2+2ct+t^2\\
&<c^2+4t+t &&(c<2,\ t^2<t)\\
&=c^2+5t\\
&<2 &&\text{for sufficiently small }t\text{, e.g. }t<\tfrac{2-c^2}5.
\end{aligned}$$
So $c+t\in S$ with $c+t>c$, contradicting that $c$ is an upper bound for $S$.

*Suppose $c^2>2$.* For $0<t<1$,
$$\begin{aligned}
(c-t)^2&=c^2-2ct+t^2\\
&>c^2-4t+0 &&(c<2)\\
&>2 &&\text{for sufficiently small }t\text{, e.g. }t<\tfrac{c^2-2}4.
\end{aligned}$$
Then $c-t$ is an upper bound for $S$ with $c-t<c$, contradicting that $c$ is the *least* upper bound.

Hence $c^2=2$. $\square$

> [!note] Explanation
> Why is $c-t$ an upper bound in the second case? Take $t$ also below $1$, so $c-t>0$. If some $x\in S$ had $x>c-t>0$, then $x^2>(c-t)^2>2$, contradicting $x^2<2$. So every $x\in S$ satisfies $x\le c-t$.

**Remark.** The same proof shows that $\sqrt[n]x$ exists for all $n\in\mathbb N$ and all $x\in\mathbb R$ with $x>0$, i.e. for all such $n,x$ there is $y\in\mathbb R$ with $y^n=x$.

### Definition — Irrational numbers

A real that is not rational is called **irrational**. E.g. $\sqrt2,\sqrt3,\sqrt5,\dots$ are irrational.

**Example.** $2+3\sqrt5$ is irrational. Indeed, if $2+3\sqrt5=\frac ab$ with $a,b\in\mathbb N$, then
$$\sqrt5=\frac{a-2b}{3b}\in\mathbb Q,$$
a contradiction.

### Density of the rationals

The rationals are **dense** in $\mathbb R$: for all $a<b$ in $\mathbb R$ there is $c\in\mathbb Q$ with $a<c<b$.

```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[>=latex,scale=1.2]
  \draw[->] (-0.6,0) -- (5.2,0) node[right] {$R$};
  \draw (0,0.08) -- (0,-0.08) node[below] {$0$};
  \draw (1.2,0.08) -- (1.2,-0.08) node[below] {$a$};
  \draw (3.8,0.08) -- (3.8,-0.08) node[below] {$b$};
  \draw[red] (2.6,0.08) -- (2.6,-0.08) node[below] {$c$};
  \draw[red,<->] (2.6,0.35) -- (3.15,0.35) node[midway,above] {$\frac1n$};
\end{tikzpicture}
\end{document}
```
*$0\le a<b$; the rational $c=\frac{m-1}n$ is the last multiple of $\frac1n$ below $b$, and steps of length $\frac1n<b-a$ cannot jump over $(a,b)$.*

**Proof.** We may assume $a\ge0$. By Corollary 3 there is $n\in\mathbb N$ with $\frac1n<b-a$. Let
$$T=\left\{k\in\mathbb N:\tfrac kn\ge b\right\}.$$
By the Axiom of Archimedes there is $N\in\mathbb N$ with $N>b$; hence $Nn\in T$, so $T\ne\varnothing$. By the well-ordering principle $T$ has a least element $m$. Set $c=\frac{m-1}n$. Since $m-1\notin T$, $c<b$. If $c\le a$, then
$$\frac mn=c+\frac1n<a+(b-a)=b,$$
contradicting $m\in T$. So $a<c<b$. $\square$

### Density of the irrationals

The irrationals are also dense in $\mathbb R$: for all $a<b$ in $\mathbb R$ there is $c\in\mathbb R\setminus\mathbb Q$ with $a<c<b$.

**Proof.** Take a rational $c$ with $a\sqrt2<c<b\sqrt2$. Then
$$a<\frac c{\sqrt2}<b,$$
and $\frac c{\sqrt2}$ is irrational (choosing $c\ne0$, e.g. by applying density of $\mathbb Q$ to a subinterval avoiding $0$). $\square$

## 2.4 Sequences

### Definition — Sequence

A **sequence** is an enumerated collection of objects in which repetition is allowed and order matters. Write
$$a_1,a_2,a_3,\dots\qquad\text{or}\qquad(a_n)_{n=1}^\infty.$$

What does it mean for a sequence $a_1,a_2,a_3,\dots$ to tend to a limit $\ell$?
- It is **not** enough that the terms get closer to $\ell$: e.g. we would not want $0,\frac12,\frac23,\frac34,\dots$ to tend to $35$.
- And it is not enough that the terms get "arbitrarily close" to $\ell$, in the sense that for all $\varepsilon>0$ there is $n\in\mathbb N$ with $\ell-\varepsilon<a_n<\ell+\varepsilon$: e.g. we would not want $0,10,\frac12,10,\frac23,10,\dots$ to tend to $1$.

We want the sequence to **get and stay** within $\varepsilon$ of $\ell$.

### Definition — Limit of a sequence

The sequence $a_1,a_2,a_3,\dots$ **tends to the limit** $\ell\in\mathbb R$ as $n$ tends to infinity if
$$\forall\varepsilon>0,\ \exists N\in\mathbb N\ \text{s.t.}\ \forall n\ge N,\quad\ell-\varepsilon<a_n<\ell+\varepsilon,$$
i.e.
$$\forall\varepsilon>0,\ \exists N\in\mathbb N\ \text{s.t.}\ \forall n\ge N,\quad|a_n-\ell|<\varepsilon.$$

### Definition — Absolute value

The **absolute value** $|x|$ of $x\in\mathbb R$ is
$$|x|=\begin{cases}x&\text{if }x\ge0,\\-x&\text{if }x<0.\end{cases}$$
We think of $|a-b|$ as the "distance between $a$ and $b$ on our number line". It is easy to check that the **triangle inequality** holds: for all $a,b,c$,
$$|a-c|\le|a-b|+|b-c|.$$

### Definition — Convergence and divergence

When $(a_n)_{n=1}^\infty$ tends to $\ell$ as $n$ tends to infinity, we write "$a_n\to\ell$ as $n\to\infty$", or "$\lim_{n\to\infty}a_n=\ell$", or "$(a_n)_{n=1}^\infty$ **converges** to $\ell$". If there is a limit $\ell$ but it is not specified, we simply say "$(a_n)_{n=1}^\infty$ converges". If $(a_n)_{n=1}^\infty$ does not converge, we say it **diverges**.

If $a_n$ does not tend to $\ell$, we write $a_n\not\to\ell$. This means
$$\exists\varepsilon>0\ \ \forall N\in\mathbb N\ \ \exists n\ge N\ \text{s.t.}\ |a_n-\ell|\ge\varepsilon.$$

### Examples of limits

**(1)** $0,\frac12,\frac23,\frac34,\dots$ The $n$th term is $a_n=1-\frac1n$.

```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[>=latex]
  % number line
  \draw[->] (-0.3,3.6) -- (5.4,3.6) node[right] {$R$};
  \foreach \x/\l in {0/0,2.6/1-\varepsilon,3.6/1,4.6/1+\varepsilon} {\draw (\x,3.68) -- (\x,3.52) node[below] {$\l$};}
  % graph of a_n
  \draw[->] (0,0) -- (5.6,0) node[right] {$n$};
  \draw[->] (0,0) -- (0,2.9);
  \draw (0,2.0) -- (5.4,2.0); \node[left] at (0,2.0) {$1$};
  \draw (0,2.5) -- (5.4,2.5); \node[left] at (0,2.5) {$1+\varepsilon$};
  \draw[red] (0,1.5) -- (5.4,1.5); \node[left,red] at (0,1.5) {$1-\varepsilon$};
  \foreach \n in {1,...,14} {\fill[blue] (0.36*\n,{2*(1-1/\n)}) circle (1.2pt); \draw (0.36*\n,0.06) -- (0.36*\n,-0.06);}
\end{tikzpicture}
\end{document}
```
*Top: the band $(1-\varepsilon,1+\varepsilon)$. Bottom: $a_n=1-\frac1n$; from some $N$ on, every term stays inside the band.*

Given $\varepsilon>0$, choose $N>\frac1\varepsilon$ (by the Axiom of Archimedes). If $n\ge N$, then
$$|a_n-1|=\left|1-\frac1n-1\right|=\frac1n\le\frac1N<\varepsilon.$$
Hence $a_n\to1$ as $n\to\infty$.

**(2)** $0,\frac12,0,\frac14,0,\frac16,\dots$, i.e.
$$a_n=\begin{cases}\frac1n,&n\text{ even},\\0,&n\text{ odd}.\end{cases}$$

```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[>=latex]
  \draw[->] (0,0) -- (5.2,0) node[right] {$n$};
  \draw[->] (0,-0.3) -- (0,2.2) node[above] {$a_n$};
  \foreach \n in {1,...,12} {
    \pgfmathsetmacro{\y}{mod(\n,2)==0 ? 3/\n : 0}
    \fill[red] (0.4*\n,\y) circle (1.3pt);
  }
\end{tikzpicture}
\end{document}
```
*$a_n$ is $0$ for odd $n$ and $\frac1n$ for even $n$ (vertical scale enlarged).*

Given $\varepsilon>0$, pick $N>\frac1\varepsilon$. If $n\ge N$, then $|a_n-0|\le\frac1n\le\frac1N<\varepsilon$. Hence $a_n\to0$ as $n\to\infty$.

**(3)** $\frac12,\ \frac12+\frac14,\ \frac12+\frac14+\frac18,\dots$, i.e. $a_n=1-\frac1{2^n}$. Given $\varepsilon>0$, choose $N>\frac1\varepsilon$. If $n\ge N$, then
$$|a_n-1|=\frac1{2^n}<\frac1n\le\frac1N<\varepsilon.$$
Hence $a_n\to1$ as $n\to\infty$.

**(4)** $-1,1,-1,1,\dots$, i.e. $a_n=(-1)^n$.

```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[>=latex]
  \draw[->] (0,0) -- (5.2,0) node[right] {$n$};
  \draw[->] (0,-1.3) -- (0,1.4) node[above] {$a_n$};
  \node[left] at (0,1) {$1$}; \node[left] at (0,-1) {$-1$};
  \foreach \n in {1,...,12} {\fill[red] (0.4*\n,{(-1)^\n}) circle (1.3pt);}
\end{tikzpicture}
\end{document}
```
*$a_n=(-1)^n$ jumps between $-1$ and $1$.*

Let us show that $a_n\not\to0$. Let $\varepsilon=1$, and observe $|a_N-0|=1$ for all $N\in\mathbb N$.

In fact, $a_n$ does not converge to any limit $\ell\in\mathbb R$. For suppose $a_n\to\ell$ as $n\to\infty$, for some $\ell\in\mathbb R$. Let $\varepsilon=1$; so there is $N\in\mathbb N$ such that $|a_n-\ell|<1$ for all $n\ge N$. In particular (taking one even and one odd $n\ge N$) $|1-\ell|<1$ and $|-1-\ell|<1$. But then
$$\begin{aligned}
2=|1-(-1)|&\le|1-\ell|+|\ell-(-1)| &&(\text{triangle inequality})\\
&<1+1=2,
\end{aligned}$$
a contradiction. Hence $(a_n)_{n=1}^\infty$ is divergent (note that it does not "go off to infinity").

### Proposition — Uniqueness of limits

If a limit exists, then it is unique.

**Proof.** We implicitly assumed this above. Suppose $a_n\to\ell$ and $a_n\to k$ as $n\to\infty$, with $k\ne\ell$. Choose $\varepsilon=\frac12|\ell-k|>0$. Then there is $N\in\mathbb N$ with $|a_n-\ell|<\varepsilon$ for all $n\ge N$, and there is $M\in\mathbb N$ with $|a_n-k|<\varepsilon$ for all $n\ge M$. But then for every $n\ge\max(N,M)$,
$$\begin{aligned}
2\varepsilon=|\ell-k|&\le|\ell-a_n|+|a_n-k| &&(\text{triangle inequality})\\
&<\varepsilon+\varepsilon=2\varepsilon,
\end{aligned}$$
a contradiction. $\square$

### Definition — Bounded sequence

A sequence $(a_n)_{n=1}^\infty$ is **bounded** if there exists a real number $B$ such that $|a_n|\le B$ for all $n\in\mathbb N$.

Note that a convergent sequence is bounded: if $a_n\to\ell$ as $n\to\infty$, then there is $N\in\mathbb N$ such that $|a_n-\ell|<1$ for all $n\ge N$. Hence
$$|a_n|\le\max\{|a_1|,\dots,|a_{N-1}|,\ |\ell|+1\}\qquad\text{for all }n\in\mathbb N.$$

### Definition — Monotonic sequence

A sequence $(a_n)_{n=1}^\infty$ is **monotonic** if it is either increasing or decreasing. It is **increasing** if $a_{n+1}\ge a_n$ for all $n\in\mathbb N$, and **decreasing** if $a_{n+1}\le a_n$ for all $n\in\mathbb N$.

### Theorem 5 — Monotone convergence theorem

Every bounded monotonic sequence converges.

**Proof.** Suppose $(a_n)$ is increasing. The set $\{a_n:n\ge1\}$ is non-empty, and bounded above because $(a_n)$ is bounded. So it has a supremum, $\ell$ say. Given $\varepsilon>0$, $\ell-\varepsilon$ is **not** an upper bound for $\{a_n:n\ge1\}$, so there is $N\in\mathbb N$ with $a_N>\ell-\varepsilon$. Since $(a_n)$ is increasing and $\ell$ is an upper bound,
$$\ell-\varepsilon<a_N\le a_n\le\ell\qquad\text{for all }n\ge N.$$
Hence $|a_n-\ell|<\varepsilon$ for all $n\ge N$, so $a_n\to\ell$. The decreasing case is similar. $\square$

**Remarks.**
1. For an increasing sequence to converge, we only need to know that it is bounded above.
2. The sequence $(a_n)_{n=1}^\infty$ with $a_n=n$ is increasing but not bounded (and in fact it diverges).
3. Theorem 5 is in fact equivalent to the least upper bound axiom.
4. One can show that every sequence has a monotonic subsequence.

### Proposition 6 — Limits preserve weak inequalities

If $a_n\le d$ for all $n$ and $a_n\to c$ as $n\to\infty$, then $c\le d$.

**Proof.** Suppose $c>d$. Let $\varepsilon=|c-d|=c-d>0$. Then there is $N\in\mathbb N$ such that $|a_n-c|<\varepsilon$ for all $n\ge N$. But
$$|a_n-c|<\varepsilon\ \Rightarrow\ a_n>c-\varepsilon=d,$$
a contradiction. $\square$

**Warning.** If $a_n<d$ for all $n$ and $a_n\to c$ as $n\to\infty$, we need **not** have $c<d$. E.g. $\frac12,\ \frac12+\frac14,\ \frac12+\frac14+\frac18,\dots$: each term is $<1$, but $\lim_{n\to\infty}a_n=1$.

### Proposition 7 — Limit of a sum

If $a_n\to c$ and $b_n\to d$ as $n\to\infty$, then $a_n+b_n\to c+d$ as $n\to\infty$.

**Proof.** Given $\varepsilon>0$, there is $N\in\mathbb N$ with $|a_n-c|<\varepsilon$ for all $n\ge N$, and there is $M\in\mathbb N$ with $|b_n-d|<\varepsilon$ for all $n\ge M$. Choose $N^*=\max\{N,M\}$. Then for all $n\ge N^*$,
$$\begin{aligned}
|a_n+b_n-(c+d)|&\le|a_n-c|+|b_n-d| &&(\text{triangle inequality})\\
&<\varepsilon+\varepsilon=2\varepsilon.
\end{aligned}$$
$\square$

> [!note] Explanation
> Ending with $2\varepsilon$ instead of $\varepsilon$ is fine: $\varepsilon>0$ was arbitrary, so $2\varepsilon$ is also an arbitrary positive number. (Equivalently, run the argument with $\frac\varepsilon2$ in place of $\varepsilon$ to finish with exactly $\varepsilon$.)

## 2.5 Series

In the reals, the sum of two numbers is defined, so by induction finite sums are defined. But infinite sums are not! Nevertheless, e.g.
$$1-\frac12+\frac13-\frac14+\frac15-\dots=\log2.$$

### Definition — Partial sums and series

Let $(a_n)$ be a sequence. Then
$$S_k=\sum_{n=1}^ka_n$$
is the **$k$-th partial sum** of the series whose $n$th term is $a_n$. We write
$$\sum_{n=1}^\infty a_n=\lim_{k\to\infty}S_k\qquad\text{if the limit exists.}$$

### Examples of series

**1) Geometric series.** The series whose $n$th term is $a_n=r^n$ for some $|r|<1$ is the **geometric series**:
$$\begin{aligned}
S_k&=r+r^2+\dots+r^k\\
&=r\cdot\frac{1-r^k}{1-r}\\
&\to r\cdot\frac1{1-r}\qquad\text{as }k\to\infty,\ \text{since }r^k\to0.
\end{aligned}$$
Hence
$$\sum_{n=1}^\infty r^n=\frac r{1-r}.$$

**2) Harmonic series.** The series whose $n$th term is $a_n=\frac1n$ is the **harmonic series**. Group the terms in blocks ending at powers of $2$:
$$\begin{aligned}
S_{2^k}&=1+\frac12+\underbrace{\frac13+\frac14}_{\text{each}\ \ge\frac14}+\underbrace{\frac15+\frac16+\frac17+\frac18}_{\text{each}\ \ge\frac18}+\frac19+\dots+\frac1{2^k}\\
&\ge1+\frac12+2\cdot\frac14+4\cdot\frac18+\dots+\frac1{2^k}\cdot2^{k-1}.
\end{aligned}$$
In general,
$$\frac1{2^m+1}+\frac1{2^m+2}+\dots+\frac1{2^{m+1}}\ \ge\ \frac{2^m}{2^{m+1}}=\frac12.$$
Hence $S_{2^k}\ge1+\frac k2$. So the partial sums are increasing and unbounded, and $\sum_{n=1}^\infty\frac1n$ diverges.
**3)** $a_n=\frac1{n^2}$. Group the terms in blocks starting at powers of $2$:
$$S_{2^k-1}=1+\underbrace{\frac1{2^2}+\frac1{3^2}}_{\le2\cdot\frac1{2^2}}+\underbrace{\frac1{4^2}+\frac1{5^2}+\frac1{6^2}+\frac1{7^2}}_{\le4\cdot\frac1{4^2}}+\dots+\frac1{(2^k-1)^2}.$$
In general,
$$\frac1{(2^m)^2}+\frac1{(2^m+1)^2}+\dots+\frac1{(2^{m+1}-1)^2}\ \le\ \frac{2^m}{(2^m)^2}=\frac1{2^m}.$$
So
$$S_{2^k-1}\le1+\frac12+\frac14+\dots+\frac1{2^{k-1}}<2.$$
By [[#Theorem 5 — Monotone convergence theorem|Theorem 5]], $\sum_{n=1}^\infty\frac1{n^2}$ converges, as its partial sums are increasing and bounded above. (In fact, $\sum_{n=1}^\infty\frac1{n^2}=\frac{\pi^2}6$.)

## 2.6 Decimal expansions

### Definition — Decimal expansion

Let $(d_n)$ be a sequence with $d_n\in\{0,1,\dots,9\}$. Then $\sum_{n=1}^\infty\frac{d_n}{10^n}$ converges to some limit $x$, where $0\le x\le1$, because the partial sums $S_m=\sum_{n=1}^m\frac{d_n}{10^n}$ are increasing and bounded by
$$\sum_{n=1}^\infty\frac9{10^n}=\frac9{10}\cdot\frac1{1-\frac1{10}}=1.$$
We say that $0.d_1d_2d_3\ldots$ is the **decimal expansion** of $x$.

### Existence of decimal expansions

Does every $x$ with $0\le x<1$ have a decimal expansion?

Pick $d_1\in\mathbb Z$ maximal such that $\frac{d_1}{10}\le x<1$. Then $0\le d_1\le9$ because $0\le x<1$, and $0\le x-\frac{d_1}{10}<\frac1{10}$ because $d_1$ is maximal.

Pick $d_2\in\mathbb Z$ maximal such that $\frac{d_2}{100}\le x-\frac{d_1}{10}$. Then $0\le d_2\le9$ because $0\le x-\frac{d_1}{10}<\frac1{10}$, and $0\le x-\frac{d_1}{10}-\frac{d_2}{100}<\frac1{100}$ because $d_2$ is maximal.

Inductively, pick $d_n\in\mathbb Z$ maximal such that
$$\frac{d_n}{10^n}\le x-\sum_{j=1}^{n-1}\frac{d_j}{10^j},\qquad\text{so}\qquad0\le x-\sum_{j=1}^n\frac{d_j}{10^j}<\frac1{10^n}.$$
Since $\frac1{10^n}\to0$ as $n\to\infty$, $x-\sum_{j=1}^n\frac{d_j}{10^j}\to0$, i.e.
$$x=\sum_{j=1}^\infty\frac{d_j}{10^j}=0.d_1d_2d_3\ldots$$

### Non-uniqueness of decimal expansions

Decimal expansions need not be unique, e.g. $0.47999\ldots=0.48000\ldots$

Suppose $0.a_1a_2\ldots=0.b_1b_2\ldots$ are different. We may suppose $a_j=b_j$ for $j<k$, for some $k$, and $a_k<b_k$. Then
$$\sum_{j=k+1}^\infty\frac{a_j}{10^j}\le\sum_{j=k+1}^\infty\frac9{10^j}=\frac9{10^{k+1}}\cdot\frac1{1-\frac1{10}}=\frac1{10^k}.$$
We must have $b_k=a_k+1$: for if $b_k>a_k+1$, then $b-a\ge\frac2{10^k}-\frac1{10^k}>0$. Also, for all $j>k$, $a_j=9$ and $b_j=0$.

> [!note] Explanation
> Writing $a=0.a_1a_2\ldots$ and $b=0.b_1b_2\ldots$: after the first $k-1$ digits agree, $b$ is ahead by $\frac{b_k-a_k}{10^k}$ at digit $k$, and the tail of $a$ can make up at most $\frac1{10^k}$ (all $9$s), while the tail of $b$ only adds. Equality therefore forces the gap to be exactly one unit ($b_k=a_k+1$), the tail of $a$ to be all $9$s, and the tail of $b$ to be all $0$s.

### Definition — Periodic decimal

A decimal expansion is **periodic** if, after a finite number of terms, it repeats in blocks, of length $k$ say, i.e.
$$\exists\,\ell,k\ \text{ such that }\ d_{n+k}=d_n\ \text{ for all }n>\ell.$$

### Periodic decimals are exactly the rationals

*A periodic decimal is rational.* E.g. $x=0.7832147147147\ldots$:
$$\begin{aligned}
10^4x-7832&=0.147147147\ldots\\
&=147\sum_{j=1}^\infty\frac1{10^{3j}}\\
&=147\cdot\frac1{10^3}\cdot\frac1{1-\frac1{10^3}},
\end{aligned}$$
so $x\in\mathbb Q$.

*Conversely, if $x\in\mathbb Q$, then it has a periodic decimal expansion.* To see this, write
$$x=\frac p{2^a5^bq},\qquad a,b,p,q\in\mathbb Z,\quad a,b,q\ge0,\quad\gcd(q,10)=1.$$
Then
$$10^{\max\{a,b\}}x=\frac tq=n+\frac cq,\qquad n,c\in\mathbb Z,\quad0\le c<q.$$
By the [[Numbers and Sets - Chapter 1 Elementary Number Theory#Theorem 13' — Fermat–Euler theorem|Fermat–Euler theorem]], since $\gcd(q,10)=1$,
$$10^{\varphi(q)}-1=kq\qquad\text{for some }k\in\mathbb N.$$
Hence
$$\frac cq=\frac{kc}{kq}=\frac{kc}{10^{\varphi(q)}-1}=kc\sum_{j=1}^\infty\frac1{(10^{\varphi(q)})^j}.$$
Since $0\le kc<kq$, we can write $kc$ as a $\varphi(q)$-digit number $d_1d_2\ldots d_{\varphi(q)}$ ($kq=10^{\varphi(q)}-1$ has $\varphi(q)$ digits), and so $x$ is periodic.

> [!note] Explanation
> $\frac{kc}{10^N-1}$ with $N=\varphi(q)$ is the repeating decimal $0.\overline{d_1\ldots d_N}$: dividing by $10^N-1$ means "repeat this $N$-digit block forever", exactly as $\frac{147}{999}=0.147147\ldots$ The factor $10^{\max\{a,b\}}$ clears the $2$s and $5$s in the denominator, which only shift the decimal point and produce the finite non-repeating start.

## 2.7 Euler's number e

### Definition — Euler's number e

Define
$$e=1+\frac1{1!}+\underbrace{\frac1{2!}}_{=\frac12}+\underbrace{\frac1{3!}}_{\le\frac14}+\underbrace{\frac1{4!}}_{\le\frac18}+\cdots$$
By [[#Theorem 5 — Monotone convergence theorem|Theorem 5]] this series converges, because the partial sums are increasing and bounded above by
$$1+1+\frac12+\frac14+\frac18+\cdots=3.$$
If we define $0!=1$, then $e=\sum_{j=0}^\infty\frac1{j!}$.

### Proposition 8 — e is irrational

$e$ is irrational.

**Proof.** Suppose $e$ were rational, i.e. $e=\frac pq$ where $p,q\in\mathbb N$ and $q>1$ (since $2<e<3$). Then $q!\,e\in\mathbb N$. But
$$q!\,e=q!+\frac{q!}{1!}+\frac{q!}{2!}+\dots+\frac{q!}{q!}+\frac{q!}{(q+1)!}+\cdots=N+x\qquad\text{for some }N\in\mathbb N,$$
where
$$\begin{aligned}
x=\sum_{j=q+1}^\infty\frac{q!}{j!}=\sum_{j=1}^\infty\frac{q!}{(q+j)!}&=\frac1{q+1}+\underbrace{\frac1{(q+1)(q+2)}}_{\le\frac1{(q+1)^2}}+\underbrace{\frac1{(q+1)(q+2)(q+3)}}_{\le\frac1{(q+1)^3}}+\cdots
\end{aligned}$$
In general $\frac{q!}{(q+j)!}\le\frac1{(q+1)^j}$, so
$$x\le\frac1{q+1}+\frac1{(q+1)^2}+\dots=\frac1q<1\qquad(\text{as }q\ge2).$$
Hence $0<x<1$, contradicting the fact that $q!\,e\in\mathbb N$ (since $N\in\mathbb N$ and $q!\,e=N+x$). So $e$ is irrational. $\square$

> [!note] Explanation
> Multiplying by $q!$ makes the first $q+1$ terms of the series integers, so if $e$ were $\frac pq$ the leftover tail $x$ would have to be an integer too. But the tail is squeezed strictly between $0$ and $1$ by comparing it with a geometric series, which is impossible.

## 2.8 Algebraic and transcendental numbers

### Definition — Algebraic and transcendental numbers

A real number is **algebraic** if it is a root of a (non-zero) polynomial with integer coefficients (or rational coefficients — same thing!). A real number is **transcendental** if it is not algebraic.

**Examples.**
1. Every rational number is algebraic: $x=\frac pq\Rightarrow qx-p=0$.
2. $\sqrt2$ is algebraic: it satisfies $x^2-2=0$.

### Theorem 9 — Liouville's theorem

(Liouville, 1851.) The number
$$L=\sum_{n=1}^\infty\frac1{10^{n!}}$$
is transcendental.

We will need two facts about polynomials.

**Fact A.** For any polynomial $p$ there is a constant $K$ such that $|p(x)-p(y)|\le K|x-y|$ for all $0\le x,y\le1$.

Indeed, suppose $p(x)=a_\alpha x^\alpha+a_{\alpha-1}x^{\alpha-1}+\dots+a_1x+a_0$. Then
$$\begin{aligned}
p(x)-p(y)&=a_\alpha(x^\alpha-y^\alpha)+a_{\alpha-1}(x^{\alpha-1}-y^{\alpha-1})+\dots+a_1(x-y)\\
&=(x-y)\big[a_\alpha(x^{\alpha-1}+x^{\alpha-2}y+\dots+y^{\alpha-1})+\dots+a_1\big],
\end{aligned}$$
so
$$|p(x)-p(y)|\le|x-y|\,\underbrace{\big(|a_\alpha|+|a_{\alpha-1}|+\dots+|a_1|\big)\cdot\alpha}_{K}.$$

**Fact B.** A non-zero polynomial of degree $d$ has at most $d$ roots.

Indeed, given a polynomial $p$ of degree $d$, we may assume by induction that the fact holds for all polynomials of degree $<d$, and that $p$ has a root, $r$ say (otherwise we are done). By long division we may write $p(x)=(x-r)q(x)$ for some polynomial $q$ of degree $d-1$. So each root of $p$ is either $r$ or a root of $q$. But by the induction hypothesis, $q$ has at most $d-1$ roots.

**Proof of Theorem 9.** Write $L_n=\sum_{k=1}^n\frac1{10^{k!}}$, so $L_n\to L$ as $n\to\infty$. Suppose there is a polynomial $p$ of which $L$ is a root. By Fact A there is $K$ with $|p(x)-p(y)|\le K|x-y|$ for all $0\le x,y\le1$. Note
$$|L-L_n|=\sum_{k=n+1}^\infty\frac1{10^{k!}}\le2\cdot\frac1{10^{(n+1)!}}.$$
Suppose $p$ has degree $d$, i.e. $p(x)=a_dx^d+\dots+a_1x+a_0$ with $a_i\in\mathbb Z$, $a_d\ne0$. Notice that $L_n=\frac s{10^{n!}}$ for some $s\in\mathbb N$, so
$$p(L_n)=\frac t{10^{dn!}}\qquad\text{for some }t\in\mathbb Z.$$
By Fact B, for sufficiently large $n$, $L_n$ is not a root of $p$. Hence
$$|p(L_n)-p(L)|=|p(L_n)|\ge\frac1{10^{dn!}}.$$
Therefore
$$\begin{aligned}
\frac1{10^{dn!}}&\le|p(L_n)-p(L)|\\
&\le K|L_n-L| &&(\text{Fact A})\\
&\le K\frac2{10^{(n+1)!}}.
\end{aligned}$$
This is a contradiction for sufficiently large $n$. $\square$

> [!note] Explanation
> The inequality says $10^{(n+1)!-dn!}\le2K$. But $(n+1)!-dn!=n!\,(n+1-d)\to\infty$, so the left side eventually exceeds the fixed number $2K$. Fact B is used because the $L_n$ are all different (strictly increasing), so at most $d$ of them can be roots of $p$; for every other $n$, $p(L_n)$ is a non-zero integer divided by $10^{dn!}$, hence at least $\frac1{10^{dn!}}$ in size. In short: $L$ is approximated by rationals far too well for a polynomial with integer coefficients to vanish at it.

**Remarks.**
1. The same proof shows that any real number $x$ such that for every $n\in\mathbb N$ there is a rational $\frac pq$ ($p,q\in\mathbb Z$, $q\ge2$) with $0<|x-\frac pq|<\frac1{q^n}$ is transcendental: "$x$ has a very good rational approximation $\Rightarrow$ $x$ is transcendental." (The condition $q\ge2$ matters: with $q=1$ allowed, $x=\frac12$ would qualify via $\frac pq=\frac01$, since $0<\frac12<1$.)
2. Such $x$ are known as **Liouville numbers**.
3. This proof does **not** show that $e$ is transcendental, but it is in fact.
4. We will give another proof of the existence of transcendental numbers in Chapter 4.
