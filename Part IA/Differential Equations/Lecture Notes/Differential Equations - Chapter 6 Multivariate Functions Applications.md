---
title: Differential Equations - Chapter 6 Multivariate Functions Applications
course: Part IA Differential Equations
material_type: lecture notes
chapter: 6
source_file: Ch.6 Multivariate Functions Application.pdf
drive_file_id: 19RlohvUsewtUnZL3-iyPLwzOtwX2UmAi
source_url: https://drive.google.com/file/d/19RlohvUsewtUnZL3-iyPLwzOtwX2UmAi/view
source_pages: 5
tags: [lecture, differential-equations]
---

# Differential Equations — Chapter 6: Multivariate Functions — Applications

> [!abstract] Overview
> For $f(x,y)$, the gradient $\nabla f=(f_x,f_y)$ gives the change of $f$ along any displacement, $df=d\mathbf s\cdot\nabla f$. The directional derivative is $\hat{\mathbf s}\cdot\nabla f$. $\nabla f$ points the way $f$ increases fastest, its length is that fastest rate, and it is perpendicular to the contours. Stationary points are where $\nabla f=\mathbf 0$: local maxima, local minima and saddle points, told apart by their contours. To classify them, expand $f$ along a line by Taylor's theorem; the second-order term is a quadratic form in the Hessian matrix.
> Prerequisite: [[Differential Equations - Chapter 3 Partial Differentiation]] (partial derivatives, chain rule).

## Results index

| Result | Statement in brief | Page |
| --- | --- | --- |
| [[#Gradient]] | $df=d\mathbf s\cdot\nabla f$, $\nabla f=(f_x,f_y)$ | 1 |
| [[#Definition — Directional derivative]] | $\frac{df}{ds}=\hat{\mathbf s}\cdot\nabla f=\cos\theta\,\lvert\nabla f\rvert$ | 2 |
| [[#Properties of the gradient]] | steepest ascent; $\lvert\nabla f\rvert=\max\frac{df}{ds}$; $\nabla f\perp$ contours | 2 |
| [[#Definition — Stationary point]] | $\nabla f=\mathbf 0$ | 2 |
| [[#Types of stationary points]] | maximum, minimum (elliptical contours), saddle (hyperbolic) | 3–4 |
| [[#Taylor series for multivariate functions]] | $f(\mathbf x_0+\delta\mathbf x)\approx f(\mathbf x_0)+\delta\mathbf x\cdot\nabla f+\frac12\delta\mathbf x^{\mathsf T}H\delta\mathbf x$ | 4–5 |
| [[#Definition — Hessian matrix]] | $H=\nabla\nabla f=\begin{pmatrix}f_{xx}&f_{xy}\\f_{yx}&f_{yy}\end{pmatrix}$, symmetric | 5 |

**Outline of the chapter:** directional derivatives; stationary points; coupled systems of first-order ODEs; partial differential equations.

## 1. Directional derivative

### Gradient

Consider $f(x,y)$ and a vector displacement $d\mathbf s=(dx,dy)$.

```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[>=latex]
  \draw[->] (-0.2,0) -- (4.6,0) node[right] {$x$};
  \draw[->] (0,-0.2) -- (0,2.8) node[above] {$y$};
  \draw[rotate around={-15:(2.3,1.4)}] (2.3,1.4) ellipse (1.8 and 1.0);
  \draw[rotate around={-15:(2.3,1.4)}] (2.3,1.4) ellipse (1.1 and 0.6);
  \draw[rotate around={-15:(2.3,1.4)}] (2.3,1.4) ellipse (0.4 and 0.25);
  \draw[blue,<-] (3.7,2.05) -- (4.2,2.5) node[above right] {\small$f$ const.};
  \draw[red,->,thick] (1.9,0.95) -- (2.15,1.25) node[left=1pt,pos=0.4] {\small$d\mathbf{s}$};
\end{tikzpicture}
\end{document}
```
*Contours of $f$ (curves on which $f$ is constant) and a small displacement $d\mathbf s$.*

The infinitesimal change in $f$ along $d\mathbf s$ is, by the [[Differential Equations - Chapter 3 Partial Differentiation#Theorem — Chain rule for partial derivatives|multivariate chain rule]],
$$df=\frac{\partial f}{\partial x}dx+\frac{\partial f}{\partial y}dy=(dx,dy)\cdot\Big(\frac{\partial f}{\partial x},\frac{\partial f}{\partial y}\Big)=d\mathbf s\cdot\nabla f,$$
where
$$\nabla f=\Big(\frac{\partial f}{\partial x},\frac{\partial f}{\partial y}\Big)\qquad(\text{in Cartesian coordinates})$$
is the **gradient** of $f$, sometimes written $\operatorname{grad}(f)$. If we write $d\mathbf s=ds\,\hat{\mathbf s}$ with $\hat{\mathbf s}$ a unit vector, then
$$df=ds\,(\hat{\mathbf s}\cdot\nabla f).$$

### Definition — Directional derivative

The **directional derivative** of $f$ in the direction of $\hat{\mathbf s}$ is
$$\frac{df}{ds}=\hat{\mathbf s}\cdot\nabla f=\cos\theta\,|\nabla f|,$$
the rate of change of $f$ in the direction $\hat{\mathbf s}$; here $\theta$ is the angle between $\hat{\mathbf s}$ and $\nabla f$. (One can define the gradient vector $\nabla f$ geometrically as the vector such that $\frac{df}{ds}=\hat{\mathbf s}\cdot\nabla f$ for all $\hat{\mathbf s}$.)

### Properties of the gradient

1. The **direction** of $\nabla f$ is that in which $f$ **increases** most rapidly.
2. The **magnitude** of $\nabla f$ is the maximum rate of change of $f$: $|\nabla f|=\max_{\theta}\Big(\dfrac{df}{ds}\Big)$.
3. If $\hat{\mathbf s}$ is parallel to the **contours of $f$** (curves of constant $f$), then
$$0=\frac{df}{ds}=\hat{\mathbf s}\cdot\nabla f.$$
Therefore $\nabla f$ is perpendicular to the contours of $f$.

> [!note] Explanation
> Properties 1 and 2 come from $\frac{df}{ds}=\cos\theta\,|\nabla f|$: as the direction $\hat{\mathbf s}$ varies, this is largest when $\cos\theta=1$, i.e. when $\hat{\mathbf s}$ points along $\nabla f$, and then it equals $|\nabla f|$.

## 2. Stationary points

There is always at least one direction in which $\frac{df}{ds}=0$, namely parallel to the contours of $f$.

### Definition — Stationary point

A **stationary point** is a point where $\frac{df}{ds}=0$ for all $\hat{\mathbf s}$. Since $\frac{df}{ds}=\hat{\mathbf s}\cdot\nabla f$, this means
$$\nabla f=\mathbf 0\qquad\text{at stationary points.}$$

### Types of stationary points

- **Local maximum:** contours are usually locally elliptical around the maximum.
- **Local minimum:** again, contours are usually elliptical around a minimum.
- **Saddle point** (not a local extremum): contours are usually locally hyperbolic. Contours cross at (and only at) saddle points.

```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[>=latex]
  % maximum
  \foreach \r in {0.3,0.6,0.9} {\draw[blue] (0,0) circle (\r);}
  \fill[red] (0,0) circle (1.2pt);
  \foreach \a in {45,135,225,315} {\draw[red,->] (\a:0.95) -- (\a:0.65);}
  \node at (0,-1.3) {\small local maximum};
  % minimum
  \begin{scope}[xshift=3cm]
  \foreach \r in {0.3,0.6,0.9} {\draw[blue] (0,0) circle (\r);}
  \fill[red] (0,0) circle (1.2pt);
  \foreach \a in {45,135,225,315} {\draw[red,->] (\a:0.6) -- (\a:0.9);}
  \node at (0,-1.3) {\small local minimum};
  \end{scope}
  % saddle
  \begin{scope}[xshift=6cm]
  \draw[blue] (-0.9,-0.9) -- (0.9,0.9); \draw[blue] (-0.9,0.9) -- (0.9,-0.9);
  \foreach \c in {0.35,0.6} {
    \draw[blue,domain=-1.1:1.1,samples=40] plot ({\c*sinh(\x)},{\c*cosh(\x)});
    \draw[blue,domain=-1.1:1.1,samples=40] plot ({\c*sinh(\x)},{-\c*cosh(\x)});
    \draw[blue,domain=-1.1:1.1,samples=40] plot ({\c*cosh(\x)},{\c*sinh(\x)});
    \draw[blue,domain=-1.1:1.1,samples=40] plot ({-\c*cosh(\x)},{\c*sinh(\x)});
  }
  \fill[red] (0,0) circle (1.2pt);
  \draw[red,->] (0,0.12) -- (0,0.3); \draw[red,->] (0,-0.12) -- (0,-0.3);
  \draw[red,->] (-0.32,0) -- (-0.14,0); \draw[red,->] (0.32,0) -- (0.14,0);
  \node at (0,-1.3) {\small saddle point};
  \end{scope}
\end{tikzpicture}
\end{document}
```
*Contours (blue) and $\nabla f$ (red) near each type of stationary point. At a maximum $\nabla f$ points inwards, at a minimum outwards; at a saddle $f$ increases away from the point in one pair of directions and decreases in the other, and two contours cross there.*

## 3. Classification of stationary points

How does $f$ change in the vicinity of a stationary point?

### Taylor series for multivariate functions

Consider how $f(x,y)$ varies along the line $\mathbf x(s)=\mathbf x_0+s\hat{\mathbf s}$ (we will think of $s$ as small).

```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[>=latex]
  \draw[->] (-0.2,0) -- (4.6,0); \draw[->] (0,-0.2) -- (0,2.8);
  \draw (2.3,1.3) ellipse (1.9 and 1.1); \draw (2.3,1.3) ellipse (1.1 and 0.65); \draw (2.3,1.3) ellipse (0.45 and 0.3);
  \fill[blue] (2.6,0.2) circle (1.3pt) node[below right] {\small$\mathbf{x}_0$};
  \draw[blue,->] (2.6,0.2) -- (3.8,2.7) node[right] {\small$s\hat{\mathbf{s}}$};
\end{tikzpicture}
\end{document}
```
*The line through $\mathbf x_0$ in direction $\hat{\mathbf s}$; along it, $f$ is a function of the single variable $s$.*

Along the line, $f(x(s),y(s))$ is a function of $s$, so use the usual [[Taylor Series and Taylor's Theorem|Taylor series]]:
$$\begin{aligned}
f(\mathbf x_0+s\hat{\mathbf s})&=f(\mathbf x_0)+s\frac{df}{ds}\Big|_{\mathbf x_0}+\frac12s^2\frac{d^2f}{ds^2}\Big|_{\mathbf x_0}+\cdots\\
&=f(\mathbf x_0)+\underbrace{s\,\hat{\mathbf s}\cdot\nabla f\big|_{\mathbf x_0}}_{①}+\underbrace{\tfrac12s^2(\hat{\mathbf s}\cdot\nabla)(\hat{\mathbf s}\cdot\nabla f)\big|_{\mathbf x_0}}_{②}+\cdots
\end{aligned}$$

① With $\delta\mathbf x=(\delta x,\delta y)=s\hat{\mathbf s}$, i.e. $\delta x=x(s)-x_0$, $\delta y=y(s)-y_0$:
$$s\,\hat{\mathbf s}\cdot\nabla f=\delta x\frac{\partial f}{\partial x}+\delta y\frac{\partial f}{\partial y}.$$

② Writing $\hat{\mathbf s}=(\hat s_x,\hat s_y)$,
$$\begin{aligned}
s^2(\hat{\mathbf s}\cdot\nabla)(\hat{\mathbf s}\cdot\nabla f)&=s^2\Big(\hat s_x\frac{\partial}{\partial x}+\hat s_y\frac{\partial}{\partial y}\Big)\Big(\hat s_x\frac{\partial f}{\partial x}+\hat s_y\frac{\partial f}{\partial y}\Big)\\
&=(\delta x)^2\frac{\partial^2f}{\partial x^2}+(\delta y)^2\frac{\partial^2f}{\partial y^2}+\underbrace{(\delta x)(\delta y)\frac{\partial^2f}{\partial x\partial y}+(\delta y)(\delta x)\frac{\partial^2f}{\partial y\partial x}}_{\text{equal}}\\
&=(\delta x,\delta y)\begin{pmatrix}f_{xx}&f_{xy}\\f_{yx}&f_{yy}\end{pmatrix}\begin{pmatrix}\delta x\\\delta y\end{pmatrix}.
\end{aligned}$$

> [!note] Explanation
> Together,
> $$f(\mathbf x_0+\delta\mathbf x)=f(\mathbf x_0)+\delta\mathbf x\cdot\nabla f\big|_{\mathbf x_0}+\tfrac12\,\delta\mathbf x^{\mathsf T}H\,\delta\mathbf x+\cdots,$$
> with $H$ the Hessian below, evaluated at $\mathbf x_0$. At a stationary point the first-order term vanishes ($\nabla f=\mathbf 0$), so near it the behaviour of $f$ is governed by the quadratic term. This is what will classify the stationary point. The two mixed terms are equal by [[Differential Equations - Chapter 3 Partial Differentiation#Theorem — Schwarz's theorem|Schwarz's theorem]].

### Definition — Hessian matrix

The **Hessian matrix** of $f$ is
$$H=\nabla\nabla f=\begin{pmatrix}f_{xx}&f_{xy}\\f_{yx}&f_{yy}\end{pmatrix},$$
which is symmetric since $f_{xy}=f_{yx}$.
