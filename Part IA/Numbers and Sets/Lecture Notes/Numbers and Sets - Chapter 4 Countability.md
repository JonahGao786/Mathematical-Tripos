---
title: Numbers and Sets - Chapter 4 Countability
course: Part IA Numbers and Sets
material_type: lecture notes
chapter: 4
source_file: Ch4. Countability.pdf
drive_file_id: 1BP8s-umleZR5F0W7zdTZInHoTPxS-Vfh
source_url: https://drive.google.com/file/d/1BP8s-umleZR5F0W7zdTZInHoTPxS-Vfh/view
source_pages: 4
tags: [lecture, numbers-and-sets]
---

# Numbers and Sets — Chapter 4: Countability

> [!abstract] Overview
> Comparing the sizes of infinite sets. A set is countable if it is finite or in bijection with $\mathbb N$, i.e. if its elements can be listed $x_1,x_2,\dots$. Finite sets, $\mathbb N$ and $\mathbb Z$ are countable, and so is every subset of $\mathbb N$. Equivalently, $X$ is countable if it injects into $\mathbb N$, or if it is empty or $\mathbb N$ maps onto it. Subsets of countable sets, $\mathbb N\times\mathbb N$, $\mathbb Z^k$, countable unions of countable sets, $\mathbb Q$ and the algebraic numbers are all countable.
> Prerequisite: [[Numbers and Sets - Chapter 3 Sets, Functions and Relations]] (bijections, finite sets).

## Results index

| Result | Statement in brief | Page |
| --- | --- | --- |
| [[#Definition — Countable and countably infinite]] | finite, or a bijection $X\to\mathbb N$ | 1 |
| [[#Examples — countable sets]] | finite sets, $\mathbb N$, $\mathbb Z$ | 1 |
| [[#Lemma 1 — Subsets of N are countable]] | any $A\subseteq\mathbb N$ is countable | 1–2 |
| [[#Theorem 2 — Characterisations of countability]] | countable $\iff$ injection $X\to\mathbb N$ $\iff$ $X=\varnothing$ or surjection $\mathbb N\to X$ | 2 |
| [[#Corollary 3 — Subsets of countable sets]] | subsets of countable sets are countable | 3 |
| [[#Theorem 4 — N × N is countable]] | diagonal listing; or $(x,y)\mapsto2^x3^y$ | 3 |
| [[#Corollary 5 — Z × Z is countable]] | and $\mathbb Z^k$ by induction | 3 |
| [[#Theorem 6 — Countable unions of countable sets]] | $x=a_j^{(i)}\mapsto2^i3^j$; $\mathbb Q$ countable | 4 |
| [[#Theorem 7 — Algebraic numbers are countable]] | integer polynomials of degree $d$ inject into $\mathbb Z^{d+1}$ | 4 |

## 4.1 Countable sets

We would like to talk about sizes of infinite sets. E.g. $\mathbb N$ "looks smaller than" $\mathbb Z$, and "a lot smaller than" $\mathbb Q$, which in turn looks "much smaller than" $\mathbb R$.

### Definition — Countable and countably infinite

A set $X$ is **countable** if $X$ is finite or there is a bijection $X\to\mathbb N$. That is, $X$ is countable if and only if we can list the elements of $X$ as $x_1,x_2,\dots$ (the list might terminate).

If $X$ is countable but not finite, it is said to be **countably infinite**.

### Examples — countable sets

1. Any finite set is countable.
2. $\mathbb N$ is countable.
3. $\mathbb Z$ is countable, as we may list the elements of $\mathbb Z$ as $0,1,-1,2,-2,\dots$, i.e.
$$x_n=\begin{cases}\dfrac n2&\text{if }n\text{ is even},\\[2mm]-\dfrac{n-1}2&\text{if }n\text{ is odd}.\end{cases}$$

```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[>=latex]
  \draw[->] (-3,0) -- (3,0) node[right] {$Z$};
  \foreach \x in {-2,-1,0,1,2} {\draw (\x,0.08) -- (\x,-0.08) node[below] {\small$\x$};}
  \draw[red,->] (0,0) to[bend left=70] (1,0);
  \draw[red,->] (1,0) to[bend right=70] (-1,0);
  \draw[red,->] (-1,0) to[bend left=70] (2,0);
  \draw[red,->] (2,0) to[bend right=70] (-2,0);
\end{tikzpicture}
\end{document}
```
*Listing $\mathbb Z$ by zig-zagging out from $0$: $x_1=0$, $x_2=1$, $x_3=-1$, $x_4=2$, $x_5=-2,\dots$; every integer appears exactly once.*

### Lemma 1 — Subsets of N are countable

Any subset of $\mathbb N$ is countable.

**Proof.** If $S\subseteq\mathbb N$ is non-empty, by the well-ordering principle there is a least element $s_1\in S$. If $S\setminus\{s_1\}\ne\varnothing$, by WOP there is a least element $s_2\in S\setminus\{s_1\}$. If $S\setminus\{s_1,s_2\}\ne\varnothing$, and so on.

If at some point this process ends, then $S=\{s_1,s_2,\dots,s_m\}$ is finite. If it goes on forever, then the map
$$g:\mathbb N\to S,\qquad n\mapsto s_n$$
is well defined (for every $n$ there is a unique $s_n$) and is injective. It is also surjective: if $k\in S$, then $k\in\mathbb N$, and there are fewer than $k$ elements of $S$ less than $k$, so $k=s_n$ for some $n\le k$.

> [!note] Explanation
> The listing is increasing, $s_1<s_2<\cdots$, so if $k$ has exactly $r$ elements of $S$ below it (with $r<k$, since they all lie in $\{1,\dots,k-1\}$), then $k$ is chosen at step $r+1$: $k=s_{r+1}$. (If $S=\varnothing$, it is finite.)

**Warning.** In $\mathbb R$, let $S=\{\frac12,\frac23,\frac34,\dots\}\cup\{1\}$. Then $S$ is countable, as we can list it as $1,\frac12,\frac23,\dots$. But if we had tried to list the elements in increasing order (as in the proof of Lemma 1), then $1$ would not be in the list.

### Theorem 2 — Characterisations of countability

The following statements are equivalent:
1. $X$ is countable;
2. there is an injection $X\to\mathbb N$;
3. $X=\varnothing$ or there is a surjection $\mathbb N\to X$.

**Proof.** (1) $\Rightarrow$ (2): if $X$ is finite, it obviously injects into $\mathbb N$, and if $X$ bijects with $\mathbb N$, then it certainly injects into $\mathbb N$.

(2) $\Rightarrow$ (1): if there is an injection $f:X\to\mathbb N$, then $f$ is a bijection between $X$ and $S=f(X)$. If $S$ is finite, then so is $X$. If $S$ is infinite, then by Lemma 1 there is a bijection $g:S\to\mathbb N$, and thus
$$X\xrightarrow{\ f\ }S\xrightarrow{\ g\ }\mathbb N$$
is a bijection.

Plainly (1) $\Rightarrow$ (3). Finally, (3) $\Rightarrow$ (2): suppose $X\ne\varnothing$ and there is a surjection $f:\mathbb N\to X$. Define $g:X\to\mathbb N$ by
$$g(a)=\min f^{-1}(\{a\}),$$
which exists by WOP. By construction $g$ is injective.

> [!note] Explanation
> "Plainly (1) $\Rightarrow$ (3)": a bijection $X\to\mathbb N$ has an inverse $\mathbb N\to X$, which is a surjection. If $X=\{x_1,\dots,x_m\}$ is finite and non-empty, $n\mapsto x_{\min(n,m)}$ is a surjection. In (3) $\Rightarrow$ (2), $f^{-1}(\{a\})$ is non-empty because $f$ is surjective; $g$ is injective because $f(g(a))=a$, so $g(a)=g(b)$ forces $a=b$.

### Corollary 3 — Subsets of countable sets

Any subset of a countable set is countable.

**Proof.** If $Y\subseteq X$ and $X$ is countable, take the injection $X\to\mathbb N$ (Theorem 2) restricted to $Y$.

We may thus view "countable" as saying that a set is "at most as big as $\mathbb N$".

### Theorem 4 — N × N is countable

$\mathbb N\times\mathbb N$ is countable.

**Proof 1.** Define $a_1=(1,1)$ and, inductively, given $a_{n-1}=(p,q)$,
$$a_n=\begin{cases}(p-1,\,q+1)&\text{if }p\ne1,\\(p+q,\,1)&\text{otherwise.}\end{cases}$$
This list includes every point $(x,y)\in\mathbb N\times\mathbb N$.

```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[>=latex,scale=0.8]
  \draw[->] (0.3,0.3) -- (5,0.3) node[right] {$p$};
  \draw[->] (0.3,0.3) -- (0.3,5) node[above] {$q$};
  \foreach \p in {1,...,4} {\foreach \q in {1,...,4} {\fill[blue] (\p,\q) circle (1.6pt);}}
  \draw[red,->,shorten <=2pt,shorten >=2pt] (1,1) -- (2,1);
  \draw[red,->,shorten <=2pt,shorten >=2pt] (2,1) -- (1,2);
  \draw[red,->,shorten <=2pt,shorten >=2pt] (1,2) -- (3,1);
  \draw[red,->,shorten <=2pt,shorten >=2pt] (3,1) -- (2,2);
  \draw[red,->,shorten <=2pt,shorten >=2pt] (2,2) -- (1,3);
  \draw[red,->,shorten <=2pt,shorten >=2pt] (1,3) -- (4,1);
  \draw[red,->,shorten <=2pt,shorten >=2pt] (4,1) -- (3,2);
  \draw[red,->,shorten <=2pt,shorten >=2pt] (3,2) -- (2,3);
  \draw[red,->,shorten <=2pt,shorten >=2pt] (2,3) -- (1,4);
  \node[below] at (1,0.3) {\small$1$}; \node[left] at (0.3,1) {\small$1$};
\end{tikzpicture}
\end{document}
```
*The list $a_1,a_2,\dots$ runs up each diagonal $p+q=\text{const}$ from bottom right to top left, then jumps to the start of the next diagonal.*

**Proof 2.** Define
$$f:\mathbb N\times\mathbb N\to\mathbb N,\qquad(x,y)\mapsto2^x3^y.$$
Then $f$ is injective by the [[Numbers and Sets - Chapter 1 Elementary Number Theory|Fundamental Theorem of Arithmetic]], so $\mathbb N\times\mathbb N$ is countable by Theorem 2.

> [!note] Explanation
> In Proof 1, the diagonal $p+q=k$ holds $k-1$ points, and the list visits them in turn: $(k-1,1),(k-2,2),\dots,(1,k-1)$. Then it moves to $(k,1)$, the first point of the next diagonal. So every $(x,y)$ appears, on diagonal $x+y$.

### Corollary 5 — Z × Z is countable

$\mathbb Z\times\mathbb Z$ is countable.

**Proof.** Since $\mathbb Z$ is countable, there is an injection $f:\mathbb Z\to\mathbb N$; since $\mathbb N\times\mathbb N$ is countable, there is an injection $g:\mathbb N\times\mathbb N\to\mathbb N$. Hence we have an injection
$$\mathbb Z\times\mathbb Z\xrightarrow{\ (f,f)\ }\mathbb N\times\mathbb N\xrightarrow{\ g\ }\mathbb N.$$

By induction, $\mathbb Z^k$ is countable for any $k\in\mathbb N$.

### Theorem 6 — Countable unions of countable sets

A countable union of countable sets is countable.

**Proof.** We may assume that our countable sets are indexed by $\mathbb N$, so given countable sets $A_1,A_2,\dots$, we wish to show $\bigcup_{n\in\mathbb N}A_n$ is countable. For each $i\in\mathbb N$, since $A_i$ is countable, we may list its elements as $a_1^{(i)},a_2^{(i)},\dots$ (the list might terminate). Define
$$f:\bigcup_{n\in\mathbb N}A_n\to\mathbb N,\qquad x\mapsto2^i3^j,$$
where $x=a_j^{(i)}$ for the least $i$ such that $x\in A_i$ (as $x$ could be in more than one of the $A_i$). This is an injection.

> [!note] Explanation
> A finite union is covered too, by taking the remaining $A_i$ to be empty. $f$ is injective because $2^i3^j$ determines $i$ and $j$ (Fundamental Theorem of Arithmetic), and $(i,j)$ determines $x=a_j^{(i)}$.

**Example.**
$$\mathbb Q=\bigcup_{n\in\mathbb N}\tfrac1n\mathbb Z=\bigcup_{n\in\mathbb N}\Big\{\frac mn:m\in\mathbb Z\Big\},$$
so $\mathbb Q$ is a countable union of countable sets, hence countable.

### Theorem 7 — Algebraic numbers are countable

The set $\mathbb A$ of [[Numbers and Sets - Chapter 2 The Reals|algebraic numbers]] is countable.

**Proof.** It suffices to show that the set of all (non-zero) polynomials with integer coefficients is countable: then $\mathbb A$ is a countable union of finite sets (the root sets of these polynomials), so by Theorem 6 it is countable.

In fact, it suffices to show that for each $d\in\mathbb N$ the set $P_d$ of all integer polynomials of degree $d$ is countable, again by Theorem 6. But the map $P_d\to\mathbb Z^{d+1}$,
$$p(x)=a_dx^d+a_{d-1}x^{d-1}+\dots+a_1x+a_0\ \longmapsto\ (a_d,\dots,a_0),$$
is an injection, so since $\mathbb Z^{d+1}$ is countable (Corollary 5), $P_d$ is also countable.
