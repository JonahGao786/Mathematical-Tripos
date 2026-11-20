---
title: Series Solutions of ODEs
course: Part IA Differential Equations
material_type: concept note
tags: [concept, differential-equations]
---

# Series Solutions of ODEs

> [!abstract] In one paragraph
> For $p(x)y''+q(x)y'+r(x)y=0$, look at $\frac qp$ and $\frac rp$ near $x_0$. If both are analytic, $x_0$ is an ordinary point and there are two independent power-series solutions. If they blow up but $(x-x_0)\frac qp$ and $(x-x_0)^2\frac rp$ are analytic, $x_0$ is a regular singular point and there is at least one Frobenius series $(x-x_0)^\sigma\sum a_n(x-x_0)^n$. Substituting a series and equating coefficients gives a recurrence for the $a_n$.

## Definitions

- **Ordinary / regular singular / irregular singular point.** → [[Differential Equations - Chapter 5 Higher Order Linear ODEs#Definition — Ordinary, regular singular and irregular singular points|lecture]]

## Key results

- **Fuchs' theorem.** Ordinary point: two Taylor-series solutions; regular singular point: at least one Frobenius series ($a_0\ne0$); irregular: the method may fail. → [[Differential Equations - Chapter 5 Higher Order Linear ODEs#Fuchs' theorem|lecture]]
- **Indicial equation** (lowest power of $x$ in the Frobenius substitution) gives $\sigma_1,\sigma_2$. $\sigma_2-\sigma_1\notin\mathbb Z$: two Frobenius series. Non-zero integer: one series from the larger root; the second is $(x-x_0)^{\sigma_1}\sum b_n(x-x_0)^n+c\,y_1\ln(x-x_0)$, $c$ possibly $0$. Repeated root: the $\ln$ term is always needed. → [[Differential Equations - Chapter 5 Higher Order Linear ODEs#Second solutions about a regular singular point|lecture]]

## Examples

- $(1-x^2)y''-2xy'+2y=0$ about $0$: $a_n=\frac{n-3}{n-1}a_{n-2}$, giving $y=a_1x+a_0\big(1-\frac12x\ln\frac{1+x}{1-x}\big)$; $x=\pm1$ are regular singular points. → [[Differential Equations - Chapter 5 Higher Order Linear ODEs#Example — series solution about an ordinary point|lecture]]
- $(1+\sqrt x)y''-2xy'+2y=0$: $x=0$ is irregular singular.
- $4xy''+2(1-x^2)y'-xy=0$: indicial $2\sigma(2\sigma-1)=0$, two independent series (Taylor for $\sigma=0$, Frobenius for $\sigma=\frac12$). → [[Differential Equations - Chapter 5 Higher Order Linear ODEs#Example — Frobenius series about a regular singular point|lecture]]
- $x^2y''-xy=0$: $\sigma=0,1$; $y_1=a_0\sum\frac{x^{n+1}}{n!(n+1)!}$, $\sigma=0$ fails, so $y_2$ needs $c\,y_1\ln x$. Around $x=-1$, $(1-x^2)y''-2xy'+2y=0$ has a repeated indicial root $0$. → [[Differential Equations - Chapter 5 Higher Order Linear ODEs#Second solutions about a regular singular point|lecture]]

## Related

[[Second-Order Linear ODEs with Constant Coefficients]] · [[Taylor Series and Taylor's Theorem]]
