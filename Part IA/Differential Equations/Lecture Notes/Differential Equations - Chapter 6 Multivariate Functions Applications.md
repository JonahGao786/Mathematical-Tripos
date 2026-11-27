---
title: Differential Equations - Chapter 6 Multivariate Functions Applications
course: Part IA Differential Equations
material_type: lecture notes
chapter: 6
source_file: Ch.6 Multivariate Functions Application.pdf
drive_file_id: 19RlohvUsewtUnZL3-iyPLwzOtwX2UmAi
source_url: https://drive.google.com/file/d/19RlohvUsewtUnZL3-iyPLwzOtwX2UmAi/view
source_pages: 14
tags: [lecture, differential-equations]
---

# Differential Equations — Chapter 6: Multivariate Functions — Applications

> [!abstract] Overview
> For $f(x,y)$, the gradient $\nabla f=(f_x,f_y)$ gives the change of $f$ along any displacement, $df=d\mathbf s\cdot\nabla f$. The directional derivative is $\hat{\mathbf s}\cdot\nabla f$. $\nabla f$ points the way $f$ increases fastest, its length is that fastest rate, and it is perpendicular to the contours. Stationary points are where $\nabla f=\mathbf 0$: local maxima, local minima and saddle points, told apart by their contours. To classify them, expand $f$ by Taylor's theorem; the second-order term is a quadratic form in the Hessian matrix $H$. Positive definite $H$ (all eigenvalues positive, or all leading minors positive by Sylvester's criterion) gives a minimum, negative definite a maximum, mixed signs a saddle, and zero eigenvalues need higher-order terms. Finally, systems of linear ODEs $\dot{\mathbf Y}=M\mathbf Y+\mathbf F$ are solved with the eigenvectors of $M$, and the eigenvalues determine the phase portrait near the fixed point.
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
| [[#Definition — Positive and negative definite]] | $\mathbf x^{\mathsf T}H\mathbf x>0$ (min) / $<0$ (max) for $\mathbf x\ne\mathbf 0$ | 5–6 |
| [[#Definiteness and eigenvalues]] | all $\lambda_i>0$ min, all $<0$ max, mixed saddle, a zero needs higher terms | 6–7 |
| [[#Definition — Signature of H]] | signs of the leading principal minors $\lvert H_1\rvert,\dots,\lvert H_N\rvert$ | 7 |
| [[#Sylvester's criterion]] | $+,+,\dots$ positive definite; $-,+,-,\dots$ negative definite | 7 |
| [[#Contours near a stationary point]] | $\lambda_1\xi^2+\lambda_2\eta^2=$ const: elliptical or hyperbolic; worked example | 8–9 |
| [[#4. Systems of linear ODEs]] | $\dot{\mathbf Y}=M\mathbf Y+\mathbf F$; reduce to one 2nd-order ODE, or the reverse | 10–11 |
| [[#4.1 Matrix methods]] | $\mathbf Y_c=\mathbf ve^{\lambda t}$ with $M\mathbf v=\lambda\mathbf v$; worked example | 11–13 |
| [[#Definition — Phase space and phase portrait]] | trajectories of $\dot{\mathbf Y}=M\mathbf Y$ | 13 |
| [[#Classification of the fixed point]] | saddle, unstable/stable node, complex pair | 13–14 |

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
> The two mixed terms are equal by [[Differential Equations - Chapter 3 Partial Differentiation#Theorem — Schwarz's theorem|Schwarz's theorem]], which is why they combine into $2\,\delta x\,\delta y\,f_{xy}$ below.

### Definition — Hessian matrix

The **Hessian matrix** of $f$ is
$$H=\nabla\nabla f=\begin{pmatrix}f_{xx}&f_{xy}\\f_{yx}&f_{yy}\end{pmatrix},$$
which is symmetric since $f_{xy}=f_{yx}$.

**Multivariate Taylor series.**
$$\begin{aligned}
f(x_0+\delta x,\,y_0+\delta y)={}&f(x_0,y_0)+\Big(\delta x\frac{\partial f}{\partial x}+\delta y\frac{\partial f}{\partial y}\Big)\Big|_{(x_0,y_0)}\\
&+\frac12\Big[(\delta x)^2\frac{\partial^2f}{\partial x^2}+2\,\delta x\,\delta y\frac{\partial^2f}{\partial x\partial y}+(\delta y)^2\frac{\partial^2f}{\partial y^2}\Big]\Big|_{(x_0,y_0)}+\cdots
\end{aligned}$$
In coordinate-independent form,
$$f(\mathbf x_0+\delta\mathbf x)=f(\mathbf x_0)+\delta\mathbf x\cdot(\nabla f)\big|_{\mathbf x_0}+\tfrac12\,\delta\mathbf x^{\mathsf T}H\big|_{\mathbf x_0}\delta\mathbf x+\cdots$$

## 3.2 Classification of stationary points

Suppose $\mathbf x_0$ is a stationary point ($\nabla f|_{\mathbf x_0}=\mathbf 0$). Around $\mathbf x_0$,
$$f(\mathbf x)\approx f(\mathbf x_0)+\tfrac12\,\delta\mathbf x^{\mathsf T}H\,\delta\mathbf x,\qquad\delta\mathbf x=\mathbf x-\mathbf x_0.$$

### Definition — Positive and negative definite

A (real) symmetric matrix $H$ is **positive definite** if
$$\mathbf x^{\mathsf T}H\mathbf x>0\quad\text{for all real }\mathbf x\ne\mathbf 0.$$
It is **negative definite** if $\mathbf x^{\mathsf T}H\mathbf x<0$ for all real $\mathbf x\ne\mathbf 0$. Otherwise it is **indefinite**.

- $H$ positive definite at $\mathbf x_0$ $\Rightarrow$ local minimum ($f(\mathbf x)>f(\mathbf x_0)$ close to $\mathbf x_0$).
- $H$ negative definite at $\mathbf x_0$ $\Rightarrow$ local maximum.
- $H$ indefinite $\Rightarrow$ may be a maximum, a minimum or a saddle.

> [!note] Explanation
> "Indefinite" here means everything else, including the cases where some $\mathbf x\ne\mathbf 0$ has $\mathbf x^{\mathsf T}H\mathbf x=0$. If $H$ takes both signs, the point is a saddle. Only when $H$ is singular can it still be a maximum or a minimum; the eigenvalue test below makes this precise.

### Definiteness and eigenvalues

$H$ is a real symmetric matrix, so it can be diagonalised by an orthogonal transformation. This corresponds to using coordinates along the principal axes (the eigenvectors). In $N$ dimensions, with real eigenvalues $\lambda_1,\dots,\lambda_N$,
$$\delta\mathbf x^{\mathsf T}H\,\delta\mathbf x=(\delta x_1,\delta x_2,\dots,\delta x_N)\begin{pmatrix}\lambda_1&&&0\\&\lambda_2&&\\&&\ddots&\\0&&&\lambda_N\end{pmatrix}\begin{pmatrix}\delta x_1\\\delta x_2\\\vdots\\\delta x_N\end{pmatrix}=\lambda_1(\delta x_1)^2+\lambda_2(\delta x_2)^2+\dots+\lambda_N(\delta x_N)^2.$$
- $H$ positive definite $\iff$ all $\lambda_i>0$ (minimum).
- $H$ negative definite $\iff$ all $\lambda_i<0$ (maximum).
- If there are eigenvalues of both signs $\Rightarrow$ saddle point (in particular, all eigenvalues non-zero but of mixed signs).
- If some eigenvalues are zero and all the others have the same sign, we need higher terms in the Taylor series to classify the stationary point.

> [!note] Explanation
> In these coordinates $\delta x_i$ means the component along the $i$th eigenvector. One positive and one negative eigenvalue already give a direction in which $f$ rises and one in which it falls, so a zero eigenvalue elsewhere does not matter: e.g. $x^2-y^2+z^4$ has $H=\operatorname{diag}(2,-2,0)$ at the origin and is a saddle there. The real eigenvalues and the orthogonal diagonalisation come from the [[Vectors and Matrices - Chapter 4 Eigenvalues and Eigenvectors#Theorem — Eigenvalues of Hermitian matrices|theorem on Hermitian and symmetric matrices]].

**Example.** $f(x,y)=x^2+y^4$ has a (global) minimum at $(x,y)=(0,0)$. Here $\nabla f=(2x,4y^3)$ and
$$H=\begin{pmatrix}2&0\\0&12y^2\end{pmatrix}=\begin{pmatrix}2&0\\0&0\end{pmatrix}\ \text{at }(0,0)\ \Rightarrow\ \lambda_1=2,\ \lambda_2=0.$$
So the Hessian alone cannot classify this minimum.

### Definition — Signature of H

The signature gives an alternative method, without having to find the eigenvalues. The **signature** of $H$ is the pattern of signs of the ordered determinants of the leading principal minors of $H$. E.g. for $f(x_1,x_2,\dots,x_N)$:
$$\underbrace{\big|f_{x_1x_1}\big|}_{|H_1|},\qquad\underbrace{\begin{vmatrix}f_{x_1x_1}&f_{x_1x_2}\\f_{x_2x_1}&f_{x_2x_2}\end{vmatrix}}_{|H_2|},\qquad\dots,\qquad\underbrace{\begin{vmatrix}f_{x_1x_1}&\cdots&f_{x_1x_N}\\\vdots&&\vdots\\f_{x_Nx_1}&\cdots&f_{x_Nx_N}\end{vmatrix}}_{|H_N|=|H|}.$$

### Sylvester's criterion

- $H$ is positive definite $\iff$ the signature is $+,+,+,\dots,+$.
- $H$ is negative definite $\iff$ the signature is $-,+,-,+,\dots$ (N.B. the order).

> [!note] Explanation
> For negative definite $H$, a leading minor with an odd number of rows has negative determinant: it is itself negative definite, so its eigenvalues are all negative, and an odd number of negative factors gives a negative product. With an even number of rows the determinant is positive.

## 3.3 Contours near stationary points

### Contours near a stationary point

Suppose $f(x,y)$ has a stationary point at $\mathbf x_0=(x_0,y_0)$. Use coordinates aligned with the principal axes of $H(\mathbf x_0)$:
$$H(\mathbf x_0)=\begin{pmatrix}\lambda_1&0\\0&\lambda_2\end{pmatrix}\qquad(\text{assume the eigenvalues are non-zero}),$$
and write $\mathbf x=\mathbf x_0+(\xi,\eta)$ around $\mathbf x_0$. Then
$$f(\mathbf x)\approx f(\mathbf x_0)+\tfrac12(\lambda_1\xi^2+\lambda_2\eta^2),$$
so the contours close to $\mathbf x_0$ are $\lambda_1\xi^2+\lambda_2\eta^2=\text{const}$.
- Maximum or minimum: $\lambda_1,\lambda_2$ of the same sign $\Rightarrow$ elliptical contours.
- Saddle: $\lambda_1,\lambda_2$ of opposite sign $\Rightarrow$ hyperbolic contours.

**Example.** Find and classify the stationary points of
$$f(x,y)=4x^3-12xy+y^2+10y+6.$$
We have $f_x=12x^2-12y$ and $f_y=-12x+2y+10$. Stationary points: $f_x=0$ gives $y=x^2$, and then $f_y=0$ gives
$$-12x+2x^2+10=0\iff x=1\text{ or }5.$$
So the stationary points are $(1,1)$ and $(5,25)$. Also $f_{xx}=24x$, $f_{xy}=-12$, $f_{yy}=2$.
- At $(1,1)$: $H=\begin{pmatrix}24&-12\\-12&2\end{pmatrix}$, $|H_1|=24$, $|H_2|=|H|=2\times24-12^2=-96$. The signature is $+,-$, so $H$ is indefinite. Note $|H|\ne0$, so all eigenvalues are non-zero $\Rightarrow$ **saddle point**.
- At $(5,25)$: $H=\begin{pmatrix}120&-12\\-12&2\end{pmatrix}$, $|H_1|=120$, $|H_2|=|H|=96$. The signature is $+,+$ $\Rightarrow$ positive definite $\Rightarrow$ **local minimum**.

Near the saddle point the contours are
$$24(\delta x)^2-24(\delta x)(\delta y)+2(\delta y)^2=\text{const}.$$

> [!note] Explanation
> For a $2\times2$ Hessian, $|H|=\lambda_1\lambda_2$. At $(1,1)$, $|H|<0$, so the eigenvalues have opposite signs: a saddle with hyperbolic contours. At $(5,25)$, $|H|>0$ and $|H_1|>0$, so both eigenvalues are positive.

## 4. Systems of linear ODEs

Consider $y_1(t)$ and $y_2(t)$ with
$$\dot y_1=ay_1+by_2+f_1(t),\qquad\dot y_2=cy_1+dy_2+f_2(t)\qquad(a,b,c,d\text{ constants}).$$
In vector form,
$$\dot{\mathbf Y}=M\mathbf Y+\mathbf F,\qquad M=\begin{pmatrix}a&b\\c&d\end{pmatrix},\quad\mathbf Y=\begin{pmatrix}y_1\\y_2\end{pmatrix},\quad\mathbf F=\begin{pmatrix}f_1(t)\\f_2(t)\end{pmatrix}.$$

There are two ways to solve it.

1. **Convert to a higher-order ODE for one variable:**
$$\begin{aligned}
\ddot y_1&=a\dot y_1+b\dot y_2+\dot f_1\\
&=a\dot y_1+b(cy_1+dy_2+f_2)+\dot f_1\\
&=a\dot y_1+bcy_1+d(\dot y_1-ay_1-f_1)+bf_2+\dot f_1,
\end{aligned}$$
so
$$\ddot y_1-(a+d)\dot y_1+(ad-bc)y_1=bf_2-df_1+\dot f_1,$$
a linear second-order ODE with constant coefficients (see [[Differential Equations - Chapter 5 Higher Order Linear ODEs|Chapter 5]]).
2. **Solve directly with matrix methods**, which may be more convenient.

> [!note] Explanation
> In the last step of 1, $by_2$ was replaced using the first equation: $by_2=\dot y_1-ay_1-f_1$. The coefficients $a+d=\operatorname{tr}M$ and $ad-bc=\det M$ appear, so the characteristic equation is $\lambda^2-(\operatorname{tr}M)\lambda+\det M=0$, the same as that of $M$.

Conversely, we sometimes write a higher-order ODE as a set of first-order ODEs. E.g. for $\ddot y+a\dot y+by=f$, let $y_1=y$, $y_2=\dot y$, $\mathbf Y=\begin{pmatrix}y_1\\y_2\end{pmatrix}$. Then $\dot y_1=y_2$ and $\dot y_2=\ddot y=-ay_2-by_1+f$, i.e.
$$\dot{\mathbf Y}=\begin{pmatrix}0&1\\-b&-a\end{pmatrix}\mathbf Y+\begin{pmatrix}0\\f\end{pmatrix}.$$

### 4.1 Matrix methods

For
$$\dot{\mathbf Y}=M\mathbf Y+\mathbf F(t),\tag{$*$}$$
1. write $\mathbf Y=\mathbf Y_c+\mathbf Y_p$ (complementary function plus particular integral), where $\dot{\mathbf Y}_c=M\mathbf Y_c$;
2. look for $\mathbf Y_c$ of the form $\mathbf Y_c=\mathbf v e^{\lambda t}$ with $\mathbf v$ a constant vector. Then
$$M\mathbf Y_c=\dot{\mathbf Y}_c=\lambda\mathbf ve^{\lambda t}=\lambda\mathbf Y_c\ \Rightarrow\ M\mathbf v=\lambda\mathbf v,$$
so $\mathbf v$ is an [[Eigenvalues and Eigenvectors|eigenvector]] of $M$ with corresponding eigenvalue $\lambda$. For a system of $n$ equations there are $n$ such $\mathbf Y_c$ if the eigenvalues are distinct;
3. find a $\mathbf Y_p$ that satisfies $(*)$.

**Example.**
$$\dot{\mathbf Y}=\underbrace{\begin{pmatrix}-4&24\\1&-2\end{pmatrix}}_{M}\mathbf Y+\underbrace{\begin{pmatrix}4\\1\end{pmatrix}e^t}_{\mathbf F}.$$
For $\mathbf Y_c=\mathbf ve^{\lambda t}$: $M\mathbf v=\lambda\mathbf v\Rightarrow\det(M-\lambda I)=0$:
$$(-4-\lambda)(-2-\lambda)-24=0\iff\lambda^2+6\lambda-16=0\iff\lambda_1=2\ \text{or}\ \lambda_2=-8,$$
with
$$\mathbf v_1=\begin{pmatrix}4\\1\end{pmatrix},\qquad\mathbf v_2=\begin{pmatrix}-6\\1\end{pmatrix},\qquad\mathbf Y_c=A\begin{pmatrix}4\\1\end{pmatrix}e^{2t}+B\begin{pmatrix}-6\\1\end{pmatrix}e^{-8t}\quad(A,B\text{ constants}).$$
Try $\mathbf Y_p=\mathbf ue^t$ with $\mathbf u$ a constant vector:
$$\mathbf u=M\mathbf u+\begin{pmatrix}4\\1\end{pmatrix}\iff(I-M)\mathbf u=\begin{pmatrix}4\\1\end{pmatrix}\iff\mathbf u=(I-M)^{-1}\begin{pmatrix}4\\1\end{pmatrix}=\begin{pmatrix}-4\\-1\end{pmatrix}$$
(the inverse exists because $1$ is not an eigenvalue of $M$). General solution:
$$\mathbf Y(t)=A\begin{pmatrix}4\\1\end{pmatrix}e^{2t}+B\begin{pmatrix}-6\\1\end{pmatrix}e^{-8t}-\begin{pmatrix}4\\1\end{pmatrix}e^t.$$

**Note.** If $\mathbf F\propto e^{\lambda t}$ with $\lambda$ an eigenvalue of $M$, try $\mathbf Y_p=(\mathbf a+\mathbf bt)e^{\lambda t}$.

> [!note] Explanation
> Check: $M\begin{pmatrix}4\\1\end{pmatrix}=\begin{pmatrix}8\\2\end{pmatrix}=2\begin{pmatrix}4\\1\end{pmatrix}$ and $M\begin{pmatrix}-6\\1\end{pmatrix}=\begin{pmatrix}48\\-8\end{pmatrix}=-8\begin{pmatrix}-6\\1\end{pmatrix}$. The Note is the matrix version of [[Differential Equations - Chapter 5 Higher Order Linear ODEs|resonance]]. For $\mathbf F=\mathbf fe^{\lambda t}$, the trial $\mathbf ue^{\lambda t}$ needs $(\lambda I-M)\mathbf u=\mathbf f$. When $\lambda$ is an eigenvalue, $\lambda I-M$ is not invertible, so this has a solution only if $\mathbf f$ lies in the image of $\lambda I-M$. If it does not, the $t$ factor is needed. E.g. $M=\operatorname{diag}(1,2)$ with $\mathbf F=(0,1)^{\mathsf T}e^t$ still has $\mathbf Y_p=(0,-1)^{\mathsf T}e^t$, but $\mathbf F=(1,0)^{\mathsf T}e^t$ needs $\mathbf Y_p=(t,0)^{\mathsf T}e^t$.

### 4.2 Non-degenerate phase portraits

### Definition — Phase space and phase portrait

The **phase space** of $n$ first-order ODEs has points $\mathbf Y=(y_1,y_2,\dots,y_n)^{\mathsf T}$. A **phase portrait** shows solution trajectories in phase space. For autonomous systems there is one trajectory through each point of phase space, except at fixed points.

Consider the homogeneous system $\dot{\mathbf Y}=M\mathbf Y$, with a fixed point at $\mathbf Y=\mathbf 0$. For $n=2$ and $\lambda_1\ne\lambda_2$ (non-degenerate), the general solution is
$$\mathbf Y(t)=A\mathbf v_1e^{\lambda_1t}+B\mathbf v_2e^{\lambda_2t},$$
with eigenvalues $\lambda_1,\lambda_2$ and eigenvectors $\mathbf v_1,\mathbf v_2$. Take $\lambda_1\ne0$, $\lambda_2\ne0$, $\lambda_1\ne\lambda_2$.

### Classification of the fixed point

1. **$\lambda_1,\lambda_2$ real, opposite signs** — without loss of generality $\lambda_1>0$, $\lambda_2<0$ ($\mathbf v_1,\mathbf v_2$ can be chosen real): a **saddle**.
2. **$\lambda_1,\lambda_2$ real, same sign** — without loss of generality $|\lambda_1|>|\lambda_2|$ (choose $\mathbf v_1,\mathbf v_2$ real).
   - (a) $\lambda_1,\lambda_2>0$: **unstable node**.
   - (b) $\lambda_1,\lambda_2<0$: **stable node** (reverse the directions of the arrows).
3. **$\lambda_1,\lambda_2$ a complex conjugate pair**: $\lambda_2=\bar\lambda_1$, $\mathbf v_2=\bar{\mathbf v}_1$, and the real solutions are
$$\mathbf Y(t)=C\mathbf v_1e^{\operatorname{Re}(\lambda_1)t}e^{i\operatorname{Im}(\lambda_1)t}+\text{c.c.},$$
where $C$ is a complex constant and c.c. denotes the complex conjugate of the first term.

```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[>=latex,scale=0.9]
  % saddle
  \draw[->] (-2,0) -- (2.1,0) node[right] {$y_1$}; \draw[->] (0,-1.8) -- (0,1.9) node[above] {$y_2$};
  \draw[blue] (-1.7,-1.3) -- (1.7,1.3) node[above right] {$v_1$};
  \draw[blue] (-1.7,1.3) -- (1.7,-1.3) node[below right] {$v_2$};
  \draw[blue,->] (0,0) -- (1.2,0.92); \draw[blue,->] (0,0) -- (-1.2,-0.92);
  \draw[blue,->] (-1.5,1.15) -- (-0.7,0.54); \draw[blue,->] (1.5,-1.15) -- (0.7,-0.54);
  \foreach \s in {1,-1} {
    \draw[red,->] plot[smooth] coordinates {(-1.3*\s,1.25*\s) (-0.35*\s,0.55*\s) (0.6*\s,0.75*\s) (1.5*\s,1.45*\s)};
    \draw[red,->] plot[smooth] coordinates {(1.3*\s,-0.95*\s) (0.45*\s,-0.15*\s) (0.85*\s,0.4*\s) (1.75*\s,1.15*\s)};
  }
  \node at (0,-2.3) {\small saddle};
  % unstable node
  \begin{scope}[xshift=5.5cm]
  \draw[->] (-2,0) -- (2.1,0) node[right] {$y_1$}; \draw[->] (0,-1.8) -- (0,1.9) node[above] {$y_2$};
  \draw[blue] (-1.7,-1.3) -- (1.7,1.3) node[above right] {$v_1$};
  \draw[blue] (-1.7,1.3) -- (1.7,-1.3) node[below right] {$v_2$};
  \foreach \a/\b in {1/1,1/-1,-1/1,-1/-1,0.4/1,0.4/-1,-0.4/1,-0.4/-1} {
    \draw[red,->,domain=0:1,samples=20] plot ({0.77*\a*1.6*\x*\x*1.6 - 0.77*\b*1.6*\x},{0.59*\a*1.6*\x*\x*1.6 + 0.59*\b*1.6*\x});
  }
  \node at (0,-2.3) {\small unstable node};
  \end{scope}
\end{tikzpicture}
\end{document}
```
*Left: saddle. Trajectories come in along $\mathbf v_2$ ($\lambda_2<0$) and leave along $\mathbf v_1$ ($\lambda_1>0$). Right: unstable node with $\lambda_1>\lambda_2>0$. Trajectories leave the origin tangent to $\mathbf v_2$ (the slower direction) and turn parallel to $\mathbf v_1$ far away. For a stable node, reverse the arrows.*

> [!note] Explanation
> In the saddle, $A\mathbf v_1e^{\lambda_1t}$ grows and $B\mathbf v_2e^{\lambda_2t}$ decays, so trajectories bend away from $\mathbf v_2$ towards $\mathbf v_1$: hyperbola-like curves. In an unstable node both terms grow. Near $\mathbf 0$ (as $t\to-\infty$) the slower term $e^{\lambda_2t}$ dominates, and far away (as $t\to+\infty$) the faster one $e^{\lambda_1t}$ does. In a stable node both terms decay, and the times are reversed. Trajectories approach $\mathbf 0$ as $t\to+\infty$, where the slower-decaying $e^{\lambda_2t}$ dominates, so they still come in tangent to $\mathbf v_2$. Far away, as $t\to-\infty$, $e^{\lambda_1t}$ dominates.
