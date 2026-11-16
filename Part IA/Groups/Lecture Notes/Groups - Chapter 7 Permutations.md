---
title: Groups - Chapter 7 Permutations
course: Part IA Groups
material_type: lecture notes
chapter: 7
source_file: Ch.7 Permutation.pdf
drive_file_id: 1HbJG7sgn41dEBzVvy_WrH_2_0PF8Gjf0
source_url: https://drive.google.com/file/d/1HbJG7sgn41dEBzVvy_WrH_2_0PF8Gjf0/view
source_pages: 4
tags: [lecture, groups]
---

# Groups — Chapter 7: Permutations

> [!abstract] Overview
> Permutations of $\{1,\dots,n\}$ written as cycles. Every permutation is a product of disjoint cycles, essentially uniquely, which gives its cycle type and its order. Transpositions generate $S_n$, and even adjacent transpositions $(i\ i{+}1)$ suffice.
> Prerequisites: [[Groups - Chapter 1 Examples and Definitions]] ($\operatorname{Sym}(X)$, $S_n$); [[Groups - Chapter 3 Group Actions]] (orbits; conjugation).

## Results index

| Result | Statement in brief | Page |
| --- | --- | --- |
| [[#Recall — Permutations and Sym(X)]] | a permutation is a bijection $X\to X$; composition | 1 |
| [[#Definition 7.1 — k-cycle]] | $(a_1\,a_2\,\cdots\,a_k)$; cyclic symmetry | 1 |
| [[#Definition 7.2 — Disjoint cycles]] | no common entries; disjoint cycles commute | 2 |
| [[#Theorem 7.3 — Disjoint cycle decomposition]] | every $\sigma\in S_n$ is a product of disjoint cycles, essentially uniquely | 2–3 |
| [[#Definition 7.4 — Cycle type]] | $(k_1,\dots,k_\ell)$-cycle; $\operatorname{ord}\sigma=\operatorname{lcm}(k_1,\dots,k_\ell)$ | 3 |
| [[#Definition 7.5 — Transposition]] | a $2$-cycle | 3 |
| [[#Theorem 7.6 — Transpositions generate S_n]] | every $\sigma\in S_n$ is a product of transpositions | 4 |
| [[#Definition 7.7 — Adjacent transposition]] | $(i\ i{+}1)$, $1\le i\le n-1$ | 4 |
| [[#Lemma 7.8 — Adjacent transpositions suffice]] | $(i\,j)=(j{-}1\ j)(i\ j{-}1)(j{-}1\ j)$ | 4 |

## 7.1 Permutations and cycles

### Recall — Permutations and Sym(X)

- A **permutation** of a set $X$ is a bijection $X\to X$.
- $\operatorname{Sym}(X)$ is the group of all such permutations ([[Groups - Chapter 1 Examples and Definitions#Definition 1.14 — The groups $S_n$|Definition 1.14]]); e.g. for $X=\{1,2,3\}$, $\operatorname{Sym}(X)=S_3$.

```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[>=latex,y=0.6cm]
  \foreach \dx/\name/\maps in {0/\sigma/{1/3,2/1,3/2},3.2/\tau/{1/2,2/1,3/3},6.4/f/{1/1,2/2,3/2}} {
    \begin{scope}[xshift=\dx cm]
      \node at (-0.7,-2) {$\name$:};
      \foreach \i in {1,2,3} {\node (l\i) at (0,-\i) {\small$\i$}; \node (r\i) at (1.4,-\i) {\small$\i$};}
      \foreach \a/\b in \maps {\draw[->] (l\a) -- (r\b);}
    \end{scope}
  }
  \node[green!50!black] at (0.7,-3.8) {\small permutation};
  \node[green!50!black] at (3.9,-3.8) {\small permutation};
  \node[red] at (7.1,-3.8) {\small not a bijection};
\end{tikzpicture}
\end{document}
```
*Two permutations of $\{1,2,3\}$, $\sigma$ ($1\mapsto3$, $2\mapsto1$, $3\mapsto2$) and $\tau$ ($1\leftrightarrow2$); the third map sends both $2$ and $3$ to $2$, so it is not a permutation.*

The group operation is composition of functions. For $\tau\circ\sigma$ (first $\sigma$, then $\tau$):
$$1\overset\sigma\longmapsto3\overset\tau\longmapsto3,\qquad2\overset\sigma\longmapsto1\overset\tau\longmapsto2,\qquad3\overset\sigma\longmapsto2\overset\tau\longmapsto1.$$

### Definition 7.1 — k-cycle

Any list of $k$ distinct elements $a_1,\dots,a_k\in\{1,\dots,n\}$ defines a **$k$-cycle** $\sigma=(a_1\,a_2\,\cdots\,a_k)\in S_n$ as follows:
$$\sigma(b)=\begin{cases}a_{i+1}&\text{if }b=a_i\ (i<k),\\a_1&\text{if }b=a_k,\\b&\text{otherwise.}\end{cases}$$
E.g. above, $\sigma=(1\,3\,2)=(3\,2\,1)=(2\,1\,3)$ (cyclic symmetry).

**Remark.** $(a_1\,a_2\,\cdots\,a_k)=(a_2\,\cdots\,a_k\,a_1)$.

**Remember:** when multiplying cycles, keep track of members "from the right". E.g. from above, $(1\,2)(1\,3\,2)$ sends $1\mapsto3$, $2\mapsto2$, $3\mapsto1$, so
$$(1\,2)(1\,3\,2)=(1\,3).$$
**Exercise:** check that $(1\,4\,3\,2)(2\,4\,3)=(1\,4\,2\,3)$.

> [!note] Explanation
> "From the right" means: to find where $b$ goes, apply the right-hand cycle first, then the left-hand one. For the exercise, $1$ is fixed by $(2\,4\,3)$ and then goes to $4$; $4\to3\to2$; $2\to4\to3$; $3\to2\to1$. So $1\mapsto4\mapsto2\mapsto3\mapsto1$, which is $(1\,4\,2\,3)$.

### Definition 7.2 — Disjoint cycles

Cycles $(a_1\,\cdots\,a_k)$ and $(b_1\,\cdots\,b_\ell)$ are **disjoint** if $a_i\ne b_j$ for all $i,j$.

**Note.**
- Disjoint cycles commute: $(a_1\,\cdots\,a_k)(b_1\,\cdots\,b_\ell)=(b_1\,\cdots\,b_\ell)(a_1\,\cdots\,a_k)$.
- Singletons act as the identity: $(a)=\operatorname{id}_X$ for any $a\in\{1,\dots,n\}$.

### Theorem 7.3 — Disjoint cycle decomposition

Every element $\sigma\in S_n$ can be written as a product of disjoint cycles. This expression is unique up to
1. shifting the elements in a cycle,
2. reordering the cycles,
3. suppressing singleton cycles.

E.g. $(1\,2)(1\,3\,2)=(1\,3)=(3\,1)=(3\,1)(2)$.

**Proof.** The action of $\langle\sigma\rangle$ on $X=\{1,\dots,n\}$ partitions $X$ into orbits,
$$X=\langle\sigma\rangle i_1\sqcup\langle\sigma\rangle i_2\sqcup\cdots\sqcup\langle\sigma\rangle i_\ell.$$
Set $k_j=|\langle\sigma\rangle i_j|$. Then
$$\sigma=\big(i_1\ \sigma(i_1)\ \cdots\ \sigma^{k_1-1}(i_1)\big)\cdots\big(i_\ell\ \sigma(i_\ell)\ \cdots\ \sigma^{k_\ell-1}(i_\ell)\big).$$
This proves existence. *Uniqueness?* The only choices were (i) the orbit representatives $i_j$, and (ii) the indexing of the orbits ($j\mapsto i_j$). Changing (i) shifts the elements of a cycle; changing (ii) permutes the cycles. Finally, we're free to omit singleton cycles, as they act as $\operatorname{id}_X$.

> [!note] Explanation
> Starting from $i_1$ and applying $\sigma$ repeatedly gives $i_1,\sigma(i_1),\sigma^2(i_1),\dots$; this runs through the orbit of $i_1$ and returns to $i_1$ after exactly $k_1$ steps (orbit–stabiliser for the cyclic group $\langle\sigma\rangle$). So on that orbit $\sigma$ acts as the cycle $(i_1\ \sigma(i_1)\ \cdots\ \sigma^{k_1-1}(i_1))$. Different orbits are disjoint, so the cycles are disjoint.

### Definition 7.4 — Cycle type

If $\sigma=(a_1^1\,a_2^1\,\cdots\,a_{k_1}^1)\cdots(a_1^\ell\,a_2^\ell\,\cdots\,a_{k_\ell}^\ell)$ is a product of disjoint cycles, then $\sigma$ is called a **$(k_1,\dots,k_\ell)$-cycle**. The multiset $\{k_1,k_2,\dots,k_\ell\}$ (repeats allowed) is called the **cycle type** of $\sigma$.

**Remark.**
- For a $k$-cycle $\sigma=(a_1\,\cdots\,a_k)$, $\operatorname{ord}(\sigma)=k$.
- If $\sigma$ is a $(k_1,\dots,k_\ell)$-cycle, $\operatorname{ord}(\sigma)=\operatorname{lcm}(k_1,\dots,k_\ell)$.

> [!note] Explanation
> The disjoint cycles commute, so $\sigma^m$ is the product of the $m$th powers of the cycles, and it is the identity exactly when each $k_j$-cycle's power is, i.e. when every $k_j$ divides $m$. The least such $m$ is $\operatorname{lcm}(k_1,\dots,k_\ell)$.

## 7.2 Transpositions

### Definition 7.5 — Transposition

A $2$-cycle is also called a **transposition**.

### Theorem 7.6 — Transpositions generate S_n

The set of transpositions generates $S_n$.

**Proof.** By induction on $n$.
- *Base case:* $n=2$, $S_2=\{e,(1\,2)\}$. ✓
- *Induction step:* suppose $S_{n-1}$ is generated by transpositions, and let $\sigma\in S_n$.
  - (a) If $\sigma(n)=n$, then $\sigma\in S_{n-1}\le S_n$, and $\sigma=\tau_1\cdots\tau_k$ for some $k$, with the $\tau_i$ transpositions.
  - (b) If $\sigma(n)\ne n$, let $\tau=(n\ \sigma(n))$. Now $(\tau\sigma)(n)=\tau(\sigma(n))=n$, so $\tau\sigma\in S_{n-1}\le S_n$. Hence $\tau\sigma=\tau_1\cdots\tau_k$ ($\tau_i$ transpositions), and so $\sigma=\tau\tau_1\cdots\tau_k$, as required.

> [!note] Explanation
> In (b), $\tau^{-1}=\tau$ (a transposition is its own inverse), so multiplying $\tau\sigma=\tau_1\cdots\tau_k$ on the left by $\tau$ gives $\sigma$. "$\sigma\in S_{n-1}$" means $\sigma$ fixes $n$ and so is a permutation of $\{1,\dots,n-1\}$.

### Definition 7.7 — Adjacent transposition

A transposition of the form $(i\ i{+}1)$ with $1\le i\le n-1$ is called **adjacent**.

### Lemma 7.8 — Adjacent transpositions suffice

Any transposition can be written as a product of adjacent transpositions.

**Proof.** Consider $(i\,j)$ and assume $j>i$; we argue by induction on $j-i$.
- *Base:* $j=i+1$, so $(i\,j)=(i\ i{+}1)$ is adjacent.
- *Inductive step:* assume $(i\ j{-}1)$ is a product of adjacent transpositions. Observe that
$$(i\,j)=(j{-}1\ j)(i\ j{-}1)(j{-}1\ j)$$
(by the conjugation formula, or just check by hand), and the result follows.

> [!note] Explanation
> By [[Groups - Chapter 3 Group Actions#Definition 3.10 — Conjugacy classes|Slogan #2]], $g(i\ j{-}1)g^{-1}$ with $g=(j{-}1\ j)=g^{-1}$ is the transposition $(g(i)\ g(j{-}1))=(i\,j)$. The right-hand side is a product of two adjacent transpositions and (by induction) a product of adjacent ones, so $(i\,j)$ is too. With Theorem 7.6, the adjacent transpositions generate $S_n$.
