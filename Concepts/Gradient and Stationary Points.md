---
title: Gradient and Stationary Points
course: Part IA Differential Equations
material_type: concept note
tags: [concept, differential-equations]
---

# Gradient and Stationary Points

> [!abstract] In one paragraph
> The gradient $\nabla f=(f_x,f_y)$ packages the partial derivatives: the change of $f$ along $d\mathbf s$ is $df=d\mathbf s\cdot\nabla f$, and the rate of change in a unit direction $\hat{\mathbf s}$ is $\hat{\mathbf s}\cdot\nabla f=|\nabla f|\cos\theta$. So $\nabla f$ points uphill fastest and is perpendicular to the contours. Stationary points are where $\nabla f=\mathbf 0$. Near one, the Taylor expansion is $f(\mathbf x_0)+\frac12\delta\mathbf x^{\mathsf T}H\delta\mathbf x+\cdots$, with $H$ the Hessian. When $H$ is non-singular, this quadratic term decides between maximum, minimum and saddle. When $H$ is singular, the second-order test is inconclusive: $x^4+y^4$ (minimum) and $x^4-y^4$ (saddle) both have $H=0$ at the origin.

## Definitions

- **Gradient** $\nabla f$, with $df=d\mathbf s\cdot\nabla f$. → [[Differential Equations - Chapter 6 Multivariate Functions Applications#Gradient|lecture]]
- **Directional derivative** $\frac{df}{ds}=\hat{\mathbf s}\cdot\nabla f$. → [[Differential Equations - Chapter 6 Multivariate Functions Applications#Definition — Directional derivative|lecture]]
- **Stationary point:** $\nabla f=\mathbf 0$. → [[Differential Equations - Chapter 6 Multivariate Functions Applications#Definition — Stationary point|lecture]]
- **Hessian** $H=\begin{pmatrix}f_{xx}&f_{xy}\\f_{yx}&f_{yy}\end{pmatrix}$, symmetric. → [[Differential Equations - Chapter 6 Multivariate Functions Applications#Definition — Hessian matrix|lecture]]

## Key results

- $\nabla f$ points in the direction of fastest increase, $|\nabla f|$ is that rate, and $\nabla f\perp$ contours. *Idea:* $\frac{df}{ds}=|\nabla f|\cos\theta$. → [[Differential Equations - Chapter 6 Multivariate Functions Applications#Properties of the gradient|lecture]]
- Maxima and minima have locally elliptical contours; at a saddle they are hyperbolic, and contours cross only at saddles. → [[Differential Equations - Chapter 6 Multivariate Functions Applications#Types of stationary points|lecture]]
- **Taylor expansion:** $f(\mathbf x_0+\delta\mathbf x)=f(\mathbf x_0)+\delta\mathbf x\cdot\nabla f+\frac12\delta\mathbf x^{\mathsf T}H\delta\mathbf x+\cdots$, from the one-variable series along $\mathbf x_0+s\hat{\mathbf s}$. → [[Differential Equations - Chapter 6 Multivariate Functions Applications#Taylor series for multivariate functions|derivation]]

## Related

[[Partial Derivatives and the Multivariate Chain Rule]] · [[Taylor Series and Taylor's Theorem]] · [[Fixed Points and Stability]]
