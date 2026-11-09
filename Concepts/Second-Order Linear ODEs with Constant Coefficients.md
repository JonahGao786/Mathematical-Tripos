---
title: Second-Order Linear ODEs with Constant Coefficients
course: Part IA Differential Equations
material_type: concept note
tags: [concept, differential-equations]
---

# Second-Order Linear ODEs with Constant Coefficients

> [!abstract] In one paragraph
> For $ay''+by'+cy=f(x)$ the operator is linear, so the general solution is two independent complementary functions plus one particular integral. Trying $e^{\lambda x}$ gives the characteristic equation $a\lambda^2+b\lambda+c=0$. Distinct roots give $e^{\lambda_1x},e^{\lambda_2x}$ (complex roots give oscillations); a repeated root $\lambda$ gives $e^{\lambda x}$ and $xe^{\lambda x}$.

## Definitions

- **Linear operator:** $D(\alpha y_1+\beta y_2)=\alpha Dy_1+\beta Dy_2$ (superposition). → [[Differential Equations - Chapter 5 Higher Order Linear ODEs#Definition — Linear differential operator|lecture]]
- **Complementary function** solves $Dy_c=0$; **particular integral** solves $Dy_p=f$. → [[Differential Equations - Chapter 5 Higher Order Linear ODEs#General solution — complementary function plus particular integral|lecture]]

## Key results

- **General solution** $y=C_1y_{c_1}+C_2y_{c_2}+y_p$. → [[Differential Equations - Chapter 5 Higher Order Linear ODEs#General solution — complementary function plus particular integral|lecture]]
- **Characteristic equation.** $De^{\lambda x}=(a\lambda^2+b\lambda+c)e^{\lambda x}$, so $e^{\lambda x}$ is a C.F. exactly when $a\lambda^2+b\lambda+c=0$. → [[Differential Equations - Chapter 5 Higher Order Linear ODEs#Characteristic equation|lecture]]
- **Repeated roots by detuning.** Shift the equation so the roots are $\lambda\pm\varepsilon$, fix initial conditions, let $\varepsilon\to0$: the C.F. becomes $\alpha e^{\lambda x}+\beta xe^{\lambda x}$. → [[Differential Equations - Chapter 5 Higher Order Linear ODEs#Detuning — repeated roots|derivation]]
- **General rule.** A degenerate C.F. $y_{c_1}$ gives a second one $xy_{c_1}$ (factorise $(\frac d{dx}-\lambda)^2$). → [[Differential Equations - Chapter 5 Higher Order Linear ODEs#General rule — degenerate complementary functions|lecture]]

## Non-constant coefficients

- **Reduction of order.** Given $y_1$ for $y''+py'+qy=0$, put $y_2=vy_1$; then $u=v'$ solves a separable equation, $u=\frac A{y_1^2}e^{-\int^xp}$. → [[Differential Equations - Chapter 5 Higher Order Linear ODEs#Reduction of order|derivation]]
- **Phase space.** The state is the solution vector $\mathbf Y=(y,y',\dots,y^{(n-1)})^{\mathsf T}$; as $x$ varies it traces a trajectory. → [[Differential Equations - Chapter 5 Higher Order Linear ODEs#Definition — Solution vector and phase space|lecture]]
- **Wronskian** $W=\det(\mathbf Y_1\cdots\mathbf Y_n)$: dependent $\Rightarrow W\equiv0$, so $W(x)\ne0$ somewhere $\Rightarrow$ independent (the converse fails). → [[Differential Equations - Chapter 5 Higher Order Linear ODEs#Wronskian test for linear independence|lecture]]
- **Abel's theorem.** $W'=-pW$, so $W(x)=W(x_0)e^{-\int_{x_0}^xp}$ (Abel's identity): $W$ is identically $0$ or never $0$; also gives a second solution via $\frac d{dx}(y_2/y_1)=W/y_1^2$. → [[Differential Equations - Chapter 5 Higher Order Linear ODEs#Abel's theorem|proof]]
- **Equidimensional** $ax^2y''+bxy'+cy=f$: try $x^k$ with $ak^2+(b-a)k+c=0$, or substitute $z=\ln x$ to get constant coefficients; a repeated root gives $x^k$ and $x^k\ln x$. → [[Differential Equations - Chapter 5 Higher Order Linear ODEs#Solving equidimensional ODEs|lecture]]

## Forced equations

- **Trial P.I.s:** $e^{mx}\to Ae^{mx}$, $\sin kx,\cos kx\to A\sin kx+B\cos kx$, polynomial $\to$ polynomial of the same degree; superpose. → [[Differential Equations - Chapter 5 Higher Order Linear ODEs#Trial particular integrals|lecture]]
- **Resonance.** If the forcing is a C.F., detune, add a C.F. to regularise, and take the limit: P.I. $=t\times$(non-resonant P.I.), e.g. $y''+\omega_0^2y=\sin\omega_0t$ gives $-\frac t{2\omega_0}\cos\omega_0t$; equidimensional analogue $(\ln x)x^{k}$. → [[Differential Equations - Chapter 5 Higher Order Linear ODEs#Resonance|derivation]]
- **Variation of parameters.** $y_p=uy_1+vy_2$ with $u'y_1+v'y_2=0$ gives $u'=-\frac{y_2f}W$, $v'=\frac{y_1f}W$. → [[Differential Equations - Chapter 5 Higher Order Linear ODEs#Variation of parameters|derivation]]

## Examples

- $y''-5y'+6y=0$: $\lambda=2,3$, $y=Ae^{3x}+Be^{2x}$.
- $y''+4y=0$: $\lambda=\pm2i$, $y=\alpha\cos2x+\beta\,i\sin2x$.
- $y''-4y'+4y=0$: $\lambda=2$ (repeated), $y=\alpha e^{2x}+\beta xe^{2x}$ (also by reduction of order).
- $\cos2x,\sin2x$ have Wronskian $2$, so they are independent.

## Related

[[First-Order Linear Differential Equations]] · [[Complex Exponential and Trigonometric Functions]] · [[Taylor Series and Taylor's Theorem]]
