---
title: Dirac Delta Function
course: Part IA Differential Equations
material_type: concept note
tags: [concept, differential-equations]
---

# Dirac Delta Function

> [!abstract] In one paragraph
> A sudden blow delivers an impulse $I=\int F\,dt$ in an instant: the velocity jumps by $I/m$ while the position stays continuous. The delta function $\delta(t)$ is the limit of unit-area spikes $D(t;\varepsilon)$; it is zero away from $0$, has integral $1$, and picks out values: $\int g(t)\delta(t-t_0)\,dt=g(t_0)$. Forcing an ODE with $\delta$ puts the $\delta$ in the highest derivative, so the derivative one order below jumps (for a second-order equation, $y'$ jumps and $y$ is continuous).

## Definitions

- **Impulse** $I=\int_{T-\varepsilon}^{T+\varepsilon}F(t;\varepsilon)\,dt$; as $\varepsilon\to0$, $m[\dot y]=I$. → [[Differential Equations - Chapter 5 Higher Order Linear ODEs#Impulses and point forces|lecture]]
- **Delta function** $\delta(t)=\lim_{\varepsilon\to0}D(t;\varepsilon)$ for unit-area spikes concentrating at $0$, e.g. $D=\frac{e^{-t^2/\varepsilon^2}}{\varepsilon\sqrt\pi}$; a distribution, meaningful only inside integrals. → [[Differential Equations - Chapter 5 Higher Order Linear ODEs#Definition — Dirac delta function|lecture]]

## Key results

- **Sifting property** $\int_a^bg(t)\delta(t-t_0)\,dt=g(t_0)$ for $a<t_0<b$ ($g$ continuous at $t_0$), and $0$ if $t_0\notin[a,b]$. → [[Differential Equations - Chapter 5 Higher Order Linear ODEs#Definition — Dirac delta function|lecture]]
- **Jump condition.** For $y''+py'+qy=\delta(x)$: $y$ is continuous and $[y']_{0^-}^{0^+}=1$; solve the homogeneous equation on each side and join. → [[Differential Equations - Chapter 5 Higher Order Linear ODEs#Delta-function forcing and the jump condition|lecture]]

## Examples

- $y''-y=3\delta(x-\frac\pi2)$, $y(0)=y(\pi)=0$: $y=A\sinh x$ then $A\sinh(\pi-x)$, with $A=-\frac3{2\cosh(\pi/2)}$.

## Related

[[Second-Order Linear ODEs with Constant Coefficients]] · [[Riemann Integration and the Fundamental Theorem of Calculus]]
