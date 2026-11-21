---
title: Numbers and Sets - Chapter 4 Countability
course: Part IA Numbers and Sets
material_type: lecture notes
chapter: 4
source_file: Ch4. Countability.pdf
drive_file_id: 1BP8s-umleZR5F0W7zdTZInHoTPxS-Vfh
source_url: https://drive.google.com/file/d/1BP8s-umleZR5F0W7zdTZInHoTPxS-Vfh/view
source_pages: 1
tags: [lecture, numbers-and-sets]
---

# Numbers and Sets — Chapter 4: Countability

> [!abstract] Overview
> Comparing the sizes of infinite sets. A set is countable if it is finite or in bijection with $\mathbb N$, i.e. if its elements can be listed $x_1,x_2,\dots$. Finite sets, $\mathbb N$ and $\mathbb Z$ are countable, and so is every subset of $\mathbb N$.
> Prerequisite: [[Numbers and Sets - Chapter 3 Sets, Functions and Relations]] (bijections, finite sets).

## Results index

| Result | Statement in brief | Page |
| --- | --- | --- |
| [[#Definition — Countable and countably infinite]] | finite, or a bijection $X\to\mathbb N$ | 1 |
| [[#Examples — countable sets]] | finite sets, $\mathbb N$, $\mathbb Z$ | 1 |
| [[#Lemma 1 — Subsets of N are countable]] | any $A\subseteq\mathbb N$ is countable | 1 |

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
