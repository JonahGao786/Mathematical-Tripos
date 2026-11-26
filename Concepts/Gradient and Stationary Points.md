---
title: Gradient and Stationary Points
course: Part IA Differential Equations
material_type: concept note
tags: [concept, differential-equations]
---

# Gradient and Stationary Points

> [!abstract] In one paragraph
> The gradient $\nabla f=(f_x,f_y)$ packages the partial derivatives: the change of $f$ along $d\mathbf s$ is $df=d\mathbf s\cdot\nabla f$, and the rate of change in a unit direction $\hat{\mathbf s}$ is $\hat{\mathbf s}\cdot\nabla f=|\nabla f|\cos\theta$. So $\nabla f$ points uphill fastest and is perpendicular to the contours. Stationary points are where $\nabla f=\mathbf 0$. Near one, the Taylor expansion is $f(\mathbf x_0)+\frac12\delta\mathbf x^{\mathsf T}H\delta\mathbf x+\cdots$, with $H$ the Hessian. When $H$ is non-singular, this quadratic term decides between maximum, minimum and saddle. When $H$ is singular and its non-zero eigenvalues all have one sign, the second-order test is inconclusive: $x^4+y^4$ (minimum) and $x^4-y^4$ (saddle) both have $H=0$ at the origin.

## Definitions

- **Gradient** $\nabla f$, with $df=d\mathbf s\cdot\nabla f$. → [[Differential Equations - Chapter 6 Multivariate Functions Applications#Gradient|lecture]]
- **Directional derivative** $\frac{df}{ds}=\hat{\mathbf s}\cdot\nabla f$. → [[Differential Equations - Chapter 6 Multivariate Functions Applications#Definition — Directional derivative|lecture]]
- **Stationary point:** $\nabla f=\mathbf 0$. → [[Differential Equations - Chapter 6 Multivariate Functions Applications#Definition — Stationary point|lecture]]
- **Positive / negative definite:** $\mathbf x^{\mathsf T}H\mathbf x>0$ / $<0$ for all $\mathbf x\ne\mathbf 0$; otherwise indefinite. **Signature:** signs of the leading principal minors. → [[Differential Equations - Chapter 6 Multivariate Functions Applications#Definition — Positive and negative definite|lecture]] · [[Differential Equations - Chapter 6 Multivariate Functions Applications#Definition — Signature of H|lecture]]
- **Hessian** $H=\begin{pmatrix}f_{xx}&f_{xy}\\f_{yx}&f_{yy}\end{pmatrix}$, symmetric. → [[Differential Equations - Chapter 6 Multivariate Functions Applications#Definition — Hessian matrix|lecture]]

## Key results

- $\nabla f$ points in the direction of fastest increase, $|\nabla f|$ is that rate, and $\nabla f\perp$ contours. *Idea:* $\frac{df}{ds}=|\nabla f|\cos\theta$. → [[Differential Equations - Chapter 6 Multivariate Functions Applications#Properties of the gradient|lecture]]
- Maxima and minima have locally elliptical contours; at a saddle they are hyperbolic, and contours cross only at saddles. → [[Differential Equations - Chapter 6 Multivariate Functions Applications#Types of stationary points|lecture]]
- **Taylor expansion:** $f(\mathbf x_0+\delta\mathbf x)=f(\mathbf x_0)+\delta\mathbf x\cdot\nabla f+\frac12\delta\mathbf x^{\mathsf T}H\delta\mathbf x+\cdots$, from the one-variable series along $\mathbf x_0+s\hat{\mathbf s}$. → [[Differential Equations - Chapter 6 Multivariate Functions Applications#Taylor series for multivariate functions|derivation]]
- **Classification.** At a stationary point, $H$ positive definite (all $\lambda_i>0$) $\Rightarrow$ local minimum; negative definite (all $\lambda_i<0$) $\Rightarrow$ local maximum; eigenvalues of both signs $\Rightarrow$ saddle; some zero eigenvalues with the rest of one sign $\Rightarrow$ look at higher-order terms (e.g. $x^2+y^4$). → [[Differential Equations - Chapter 6 Multivariate Functions Applications#Definiteness and eigenvalues|lecture]]
- **Sylvester's criterion.** Leading principal minors $+,+,\dots,+$ $\iff$ positive definite; $-,+,-,\dots$ $\iff$ negative definite. → [[Differential Equations - Chapter 6 Multivariate Functions Applications#Sylvester's criterion|lecture]]
- **Contours** near a non-degenerate stationary point are $\lambda_1\xi^2+\lambda_2\eta^2=$ const in principal axes: ellipses at extrema, hyperbolas at saddles. Worked example: $4x^3-12xy+y^2+10y+6$ has a saddle at $(1,1)$ and a minimum at $(5,25)$. → [[Differential Equations - Chapter 6 Multivariate Functions Applications#Contours near a stationary point|lecture]]

## Related

[[Partial Derivatives and the Multivariate Chain Rule]] · [[Taylor Series and Taylor's Theorem]] · [[Fixed Points and Stability]]
