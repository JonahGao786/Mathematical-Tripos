---
title: Groups - Chapter 9 Platonic Solids
course: Part IA Groups
material_type: lecture notes
chapter: 9
source_file: Ch.9 Platonic Solids.pdf
drive_file_id: 1DI95lqKNiVZed3VucgyRB_uS7KzO0ANX
source_url: https://drive.google.com/file/d/1DI95lqKNiVZed3VucgyRB_uS7KzO0ANX/view
source_pages: 1
tags: [lecture, groups]
---

# Groups — Chapter 9: Platonic Solids

> [!abstract] Overview
> In 2D there are infinitely many regular polygons. In 3D, a convex polyhedron is a Platonic solid when it is regular: its isometry group can move any face–edge–vertex flag to any other.
> Prerequisites: [[Groups - Chapter 8 Matrices]] (orthogonal groups, isometries); [[Groups - Chapter 1 Examples and Definitions]] (symmetry groups).

## Results index

| Result | Statement in brief | Page |
| --- | --- | --- |
| [[#Definition — Isometry group]] | $\operatorname{Isom}(X)$: bijections of $X$ preserving distances | 1 |
| [[#Definition — Platonic solid]] | convex polyhedron in which any flag $V\in E\subseteq F$ can be moved to any other | 1 |

## 9.1 Regular polyhedra

- **2D:** there are infinitely many regular polygons.
- **3D:** suppose $X\subseteq\mathbb R^3$.

### Definition — Isometry group

$$\operatorname{Isom}(X)=\{f\in\operatorname{Sym}(X):\|f(\mathbf x)-f(\mathbf y)\|=\|\mathbf x-\mathbf y\|\ \text{for all }\mathbf x,\mathbf y\in X\}$$
is called the **isometry group** of $X$.

### Definition — Platonic solid

A **convex polyhedron** is made of flat polygonal faces, with edges glued to edges and vertices to vertices. A convex polyhedron $X\subseteq\mathbb R^3$ is a **Platonic solid** if it is regular, i.e. any triple (face $F$, edge $E$, vertex $V$) with $V\in E\subseteq F$ can be sent to any other by an isometry.

**Example.** A box that is not a cube is not regular.

```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[scale=0.8]
  \foreach \s/\lab in {0/1,6/2} {
  \begin{scope}[xshift=\s cm]
    \fill[red!12] (0,0) rectangle (3.4,1);
    \draw (0,0) rectangle (3.4,1);
    \draw (0,1) -- (0.8,1.6) -- (4.2,1.6) -- (3.4,1);
    \draw (3.4,0) -- (4.2,0.6) -- (4.2,1.6);
    \draw[dashed,gray] (0,0) -- (0.8,0.6) -- (4.2,0.6); \draw[dashed,gray] (0.8,0.6) -- (0.8,1.6);
    \fill[red] (0,1) circle (2pt);
  \end{scope}}
  \draw[red,very thick] (0,0) -- (0,1);
  \draw[red,very thick] (6,1) -- (9.4,1);
\end{tikzpicture}
\end{document}
```
*Two flags on the same box: the same shaded face and the same vertex (dot), but a short edge on the left and a long edge on the right. No isometry can send one flag to the other.*

> [!note] Explanation
> An isometry preserves lengths, so it cannot send a short edge to a long one. So the flags of this box cannot all be moved to each other, and the box is not regular.
