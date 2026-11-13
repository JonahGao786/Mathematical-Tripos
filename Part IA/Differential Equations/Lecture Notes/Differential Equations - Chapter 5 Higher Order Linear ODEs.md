---
title: Differential Equations - Chapter 5 Higher Order Linear ODEs
course: Part IA Differential Equations
material_type: lecture notes
chapter: 5
source_file: Ch.5 Higher Order Linear ODEs.pdf
drive_file_id: 1zZMeu0U4PjDGE0fJuLsDnVFj5p1KfLcB
source_url: https://drive.google.com/file/d/1zZMeu0U4PjDGE0fJuLsDnVFj5p1KfLcB/view
source_pages: 28
tags: [lecture, differential-equations]
---

# Differential Equations — Chapter 5: Higher Order Linear ODEs

> [!abstract] Overview
> Second-order linear ODEs with constant coefficients. Linearity of the differential operator gives the general solution as complementary function plus particular integral. Complementary functions come from $e^{\lambda x}$ and the characteristic equation; complex roots give oscillations, and repeated roots are handled by detuning, which produces $xe^{\lambda x}$. For non-constant coefficients: reduction of order finds a second solution from a first; phase space and solution vectors; the Wronskian tests linear independence, and Abel's identity gives it without solving the ODE. Equidimensional equations reduce to constant coefficients. For forced equations: trial particular integrals, resonance (handled by detuning, giving a factor $t$, or $\ln x$ for equidimensional equations), and variation of parameters. Finally the damped, forced mass–spring system: light, critical and heavy damping, and the transient and steady-state forced response; impulses, the Dirac delta function, and delta-function forcing with its jump condition.
> Prerequisite: [[Differential Equations - Chapter 4 First-Order Linear Differential Equations]] ($e^{\lambda x}$ as eigenfunction, CF + PI).

## Results index

| Result | Statement in brief | Page |
| --- | --- | --- |
| [[#Definition — Linear differential operator]] | $D(\alpha y_1+\beta y_2)=\alpha Dy_1+\beta Dy_2$ (superposition) | 1 |
| [[#General solution — complementary function plus particular integral]] | $y=C_1y_{c_1}+C_2y_{c_2}+y_p$ | 1–2 |
| [[#Characteristic equation]] | $y_c=Ae^{\lambda x}$ with $a\lambda^2+b\lambda+c=0$; distinct vs repeated roots | 2–3 |
| [[#Detuning — repeated roots]] | repeated root $\lambda$: $y_c=\alpha e^{\lambda x}+\beta xe^{\lambda x}$ | 4–5 |
| [[#General rule — degenerate complementary functions]] | $y_{c_2}=xy_{c_1}$ | 5 |
| [[#Reduction of order]] | $y_2=vy_1$, $v'=\frac A{y_1^2}\exp\left(-\int^xp\right)$ | 6–7 |
| [[#Definition — Solution vector and phase space]] | $\mathbf Y=(y,y',\dots,y^{(n-1)})^{\mathsf T}$; trajectories | 7–8 |
| [[#Definition — Fundamental matrix and Wronskian]] | $W=\det(\mathbf Y_1\cdots\mathbf Y_n)$ | 9 |
| [[#Wronskian test for linear independence]] | dependent $\Rightarrow W\equiv0$; $W(x)\ne0$ somewhere $\Rightarrow$ independent | 9–10 |
| [[#Abel's theorem]] | $W\equiv0$ on $I$ or $W$ never $0$ on $I$; $W(x)=W(x_0)e^{-\int_{x_0}^xp}$ | 10–12 |
| [[#Definition — Equidimensional ODE]] | $ax^2y''+bxy'+cy=f(x)$; scaling property | 12–13 |
| [[#Solving equidimensional ODEs]] | $y_c=x^k$, $ak^2+(b-a)k+c=0$; $z=\ln x$; repeated root gives $x^k\ln x$ | 13–14 |
| [[#Trial particular integrals]] | $e^{mx}\to Ae^{mx}$; $\sin kx,\cos kx\to A\sin kx+B\cos kx$; $P_n\to Q_n$ | 15–16 |
| [[#Resonance]] | forcing in the C.F.: P.I. $=t\times$(non-resonant P.I.), e.g. $-\frac t{2\omega_0}\cos\omega_0t$ | 16–17 |
| [[#Resonance in equidimensional equations]] | forcing $x^{k_1}$: P.I. $\propto(\ln x)x^{k_1}$ | 17–18 |
| [[#Variation of parameters]] | $y_p=-y_1\int^x\frac{y_2f}W+y_2\int^x\frac{y_1f}W$; example $y''+4y=\sin2x$ | 18–20 |
| [[#Damped mass–spring system]] | $m\ddot y+b\dot y+ky=F(t)$; $y''+2\kappa y'+y=f(\tau)$ with $\tau=\omega_0t$ | 20–21 |
| [[#Free response — light, critical and heavy damping]] | $\kappa<1$ oscillates and decays; $\kappa=1$: $e^{-\tau}(A+B\tau)$; $\kappa>1$: two decaying exponentials | 21–23 |
| [[#Forced response — transient and steady state]] | C.F. decays, leaving the steady state $y_p=\frac{F_0/m}{(\omega_0^2-\omega^2)^2+\mu^2\omega^2}\big((\omega_0^2-\omega^2)\sin\omega t-\mu\omega\cos\omega t\big)$ | 23 |
| [[#Impulses and point forces]] | impulse $I=\int F\,dt$; $\lim m[\dot y]=I$: velocity jumps | 24–25 |
| [[#Definition — Dirac delta function]] | $\delta(t)=\lim_{\varepsilon\to0}D(t;\varepsilon)$; $\int g(t)\delta(t-t_0)\,dt=g(t_0)$ | 25–26 |
| [[#Delta-function forcing and the jump condition]] | $y''+py'+qy=\delta(x)$: $y$ continuous, $[y']=1$ | 27–28 |

Notes on scope:
- We focus on second order, but many methods apply to higher order.
- Closed-form solutions to second-order linear ODEs don't always exist (unlike first order).

## 1. Second-order ODEs with constant coefficients

The general form is
$$a\frac{d^2y}{dx^2}+b\frac{dy}{dx}+cy=f(x),\tag{$*$}$$
where $a,b,c$ are constants. This is $Dy=f$, where the differential operator
$$D\equiv a\frac{d^2}{dx^2}+b\frac d{dx}+c$$
is linear.

### Definition — Linear differential operator

A differential operator $D$ is **linear** if for any $y_1(x)$ and $y_2(x)$, and constants $\alpha$ and $\beta$,
$$D(\alpha y_1+\beta y_2)=\alpha Dy_1+\beta Dy_2$$
(the **principle of superposition**).

### General solution — complementary function plus particular integral

Exploit linearity to solve $(*)$:
1. Find **complementary functions** (C.F.s) $y_c$ that satisfy the homogeneous equation
$$a\frac{d^2y_c}{dx^2}+b\frac{dy_c}{dx}+cy_c=0.$$
2. Find a **particular integral** (P.I.) $y_p(x)$ that satisfies the full equation $(*)$.

Then a solution of the full equation is $y_c+y_p$:
$$D(y_c+y_p)=Dy_c+Dy_p=0+f(x).$$
A second-order ODE has two linearly independent C.F.s, so the general solution to the full equation is
$$y(x)=C_1y_{c_1}(x)+C_2y_{c_2}(x)+y_p(x),\qquad C_1,C_2\text{ constants}.$$

## 1.1 Complementary functions

### Characteristic equation

Recall $\frac d{dx}e^{\lambda x}=\lambda e^{\lambda x}$ ($e^{\lambda x}$ is an eigenfunction of $\frac d{dx}$). It is also an eigenfunction of $D$:
$$\begin{aligned}
De^{\lambda x}&=a\frac{d^2}{dx^2}e^{\lambda x}+b\frac d{dx}e^{\lambda x}+ce^{\lambda x}\\
&=\underbrace{(a\lambda^2+b\lambda+c)}_{\text{eigenvalue}}e^{\lambda x}.
\end{aligned}$$
The C.F.s of $(*)$ satisfy $Dy_c=0$, i.e. they are eigenfunctions with eigenvalue $0$. Therefore
$$y_c=Ae^{\lambda x}\qquad\text{with}\qquad a\lambda^2+b\lambda+c=0,$$
the **characteristic** (or **auxiliary**) **equation** of $D$, with roots $\lambda_1$ and $\lambda_2$.

**Case 1: $\lambda_1\ne\lambda_2$.** There are two linearly independent C.F.s,
$$y_{c_1}\propto e^{\lambda_1x},\qquad y_{c_2}\propto e^{\lambda_2x}.$$
The most general C.F. is
$$y_c(x)=C_1y_{c_1}(x)+C_2y_{c_2}(x);$$
$y_{c_1},y_{c_2}$ form a **basis** for the space of solutions of the homogeneous equation.

Note: the roots may be complex, which gives oscillations.

**Case 2: $\lambda_1=\lambda_2$.** There is only one linearly independent C.F. of the form $e^{\lambda_1x}$; see [[#Detuning — repeated roots]] for how to deal with this.

**Example (real, non-degenerate roots).**
$$\frac{d^2y}{dx^2}-5\frac{dy}{dx}+6y=0.$$
Characteristic equation: $\lambda^2-5\lambda+6=0$, so $\lambda=3$, $\lambda=2$. C.F.:
$$y_c(x)=Ae^{3x}+Be^{2x}.$$

**Example (complex roots).**
$$\frac{d^2y}{dx^2}+4y=0.$$
Characteristic equation: $\lambda^2=-4$, so $\lambda=\pm2i$. C.F.:
$$\begin{aligned}
y_c(x)&=Ae^{2ix}+Be^{-2ix} &&(e^{\pm2ix}=\cos2x\pm i\sin2x)\\
&=(A+B)\cos2x+(A-B)\,i\sin2x\\
&=\alpha\cos2x+\beta\,i\sin2x,
\end{aligned}$$
with $\alpha=A+B$, $\beta=A-B$ arbitrary constants.

### Detuning — repeated roots

**Example (degenerate roots).**
$$\frac{d^2y}{dx^2}-4\frac{dy}{dx}+4y=0.$$
Characteristic equation: $\lambda^2-4\lambda+4=0$, so $\lambda=2$, a degenerate (repeated) root. There is only one C.F. of the form $e^{2x}$.

**Detuning.** Remove the degeneracy by considering a slightly modified (**detuned**) equation:
$$\frac{d^2y}{dx^2}-4\frac{dy}{dx}+(4-\varepsilon^2)y=0\qquad(\varepsilon\ll1).$$
Then $\lambda^2-4\lambda+4-\varepsilon^2=0$, so $\lambda=2\pm\varepsilon$. The general C.F. is
$$\begin{aligned}
y_c&=Ae^{(2+\varepsilon)x}+Be^{(2-\varepsilon)x}\\
&=e^{2x}\left(Ae^{\varepsilon x}+Be^{-\varepsilon x}\right)\\
&=e^{2x}\left[(A+B)+\varepsilon(A-B)x+O(A\varepsilon^2x^2)+O(B\varepsilon^2x^2)\right]\qquad\text{as }\varepsilon\to0.
\end{aligned}$$
Consider initial conditions (for the original and the detuned equation)
$$y(0)=C,\qquad y'(0)=D.$$
Then
$$\begin{aligned}
A+B&=C,\\
2(A+B)+\varepsilon(A-B)&=D,\quad\text{so}\quad\varepsilon(A-B)=D-2C,
\end{aligned}$$
giving
$$A=\frac12\left(C+\frac{D-2C}\varepsilon\right),\qquad B=\frac12\left(C-\frac{D-2C}\varepsilon\right).$$
Therefore $O(A\varepsilon^2x^2)=O(\varepsilon x^2)\to0$ as $\varepsilon\to0$, and similarly for $B$, while
$$\alpha=A+B=O(1),\qquad\beta=\varepsilon(A-B)=O(1).$$
So the general C.F. of the original degenerate equation is
$$y=\alpha e^{2x}+\beta xe^{2x}.$$

> [!note] Explanation
> $A$ and $B$ each blow up like $\frac1\varepsilon$ as $\varepsilon\to0$, but in opposite directions, so their sum $A+B=C$ and the combination $\varepsilon(A-B)=D-2C$ stay fixed by the initial conditions. Those two finite numbers are the coefficients of $e^{2x}$ and $xe^{2x}$; every remaining term carries at least one extra factor of $\varepsilon$ and vanishes in the limit. The second, "missing" solution of the degenerate equation is therefore $xe^{2x}$.

### General rule — degenerate complementary functions

If $y_{c_1}(x)$ is a degenerate C.F. of a linear ODE with constant coefficients, then
$$y_{c_2}(x)=xy_{c_1}(x)$$
is a second linearly independent C.F. For the example above, the equation factorises as
$$\Big(\frac d{dx}-2\Big)\Big(\frac d{dx}-2\Big)y=0,\qquad\text{i.e.}\qquad\Big(\frac d{dx}-2\Big)u=0\quad\text{with}\quad u=\Big(\frac d{dx}-2\Big)y.$$

> [!note] Explanation
> The factorised form gives the general rule directly. First $u'-2u=0$ gives $u=Ce^{2x}$. Then $y'-2y=Ce^{2x}$; with the integrating factor $e^{-2x}$, $(e^{-2x}y)'=C$, so $y=(Cx+D)e^{2x}$. The repeated factor is what produces the extra $x$.

## 2. Homogeneous second-order ODEs with non-constant coefficients

The general form is
$$y''+p(x)y'+q(x)y=0.\tag{$*$}$$

## 2.1 Second C.F. — reduction of order

### Reduction of order

Find a second solution $y_2(x)$ given one solution $y_1(x)$. Try the form
$$y_2(x)=v(x)y_1(x),$$
with $v$ to be determined. Then
$$y_2'=v'y_1+vy_1',\qquad y_2''=v''y_1+2v'y_1'+vy_1''.$$
If $y_2$ satisfies $(*)$,
$$v''y_1+v'(2y_1'+py_1)+v\underbrace{(y_1''+py_1'+qy_1)}_{=0\text{ since }y_1\text{ solves }(*)}=0,$$
so
$$v''y_1+v'(2y_1'+py_1)=0,\qquad\text{i.e.}\qquad u'y_1+u(2y_1'+py_1)=0\quad\text{where }u=v',$$
a separable first-order ODE for $u$. Hence (assuming the right-hand side is non-zero)
$$\begin{aligned}
\frac{u'}u&=-\frac{2y_1'}{y_1}-p\\
\Rightarrow\quad\ln u&=-2\ln y_1-\int_0^xp(t)\,dt+\ln A\\
\Rightarrow\quad u(x)&=\frac A{y_1^2}\exp\Big(-\int_0^xp(t)\,dt\Big).
\end{aligned}$$
Integrate to get $v(x)$.

**Example.** $y''-4y'+4y=0$, so $p(x)=-4$, $q(x)=4$. One solution is $y_1=e^{2x}$. Then
$$\frac{u'}u=-\frac{2\cdot2e^{2x}}{e^{2x}}+4=0,$$
so $v'=u$ is constant, and $v(x)=Ax+B$. Thus
$$y_2(x)=(Ax+B)e^{2x},$$
where the $Be^{2x}$ part reproduces $y_1$. Therefore $xe^{2x}$ is a second linearly independent solution.

## 2.2 Phase space

### Definition — Solution vector and phase space

For an $n$th-order linear ODE
$$y^{(n)}+p(x)y^{(n-1)}+\dots+q(x)y=f(x),$$
$y^{(n)}(x)$ is determined by $y(x),y'(x),\dots,y^{(n-1)}(x)$, and higher derivatives of $y$ can be determined by differentiating the ODE. So we can construct the Taylor series about $x_0$ if $y(x_0),y'(x_0),\dots,y^{(n-1)}(x_0)$ are specified.

The **state of the system** is fully specified at any $x$ by the $n$-dimensional **solution vector**
$$\mathbf Y(x)=\begin{pmatrix}y(x)\\y'(x)\\\vdots\\y^{(n-1)}(x)\end{pmatrix}$$
(i.e. knowing this at one $x$ gives the solution at any $x$).
- At any $x$, $\mathbf Y(x)$ defines a point in $n$-dimensional **phase space**.
- As $x$ varies, $\mathbf Y(x)$ traces out a **trajectory** in phase space.

**Example.** $y''+4y=0$ with $y_1(x)=\cos2x$, $y_2(x)=\sin2x$:
$$\mathbf Y_1(x)=\begin{pmatrix}y_1\\y_1'\end{pmatrix}=\begin{pmatrix}\cos2x\\-2\sin2x\end{pmatrix},\qquad\mathbf Y_2(x)=\begin{pmatrix}y_2\\y_2'\end{pmatrix}=\begin{pmatrix}\sin2x\\2\cos2x\end{pmatrix}.$$

```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[>=latex,scale=1.1]
  \draw[->] (-2.2,0) -- (2.4,0) node[right] {$y$};
  \draw[->] (0,-2.5) -- (0,2.6) node[above] {$y'$};
  \draw[red,thick] (0,0) ellipse (1 and 2);
  \draw[blue,thick,->] (0,0) -- (0.878,-0.959) node[right] {$\mathbf Y_1(x)$};
  \draw[blue,thick,->] (0,0) -- (0.479,1.755) node[right] {$\mathbf Y_2(x)$};
\end{tikzpicture}
\end{document}
```
*2D phase space for $y''+4y=0$: both trajectories run round the ellipse $y^2+\frac{y'^2}4=1$; shown at the same $x$ (here $2x=0.5$).*

$\mathbf Y_1$ and $\mathbf Y_2$ are linearly independent vectors (in the linear-algebra sense), so we can use them as basis vectors for the 2D phase space.

## 2.3 Wronskian and linear dependence

**Recall.** $\{y_i(x)\}$ is linearly dependent if
$$\sum_{i=1}^nc_iy_i(x)=0\quad\text{for all }x,\qquad c_i\text{ not all zero}.$$
This must hold for all $x$, so we can differentiate $1,2,\dots,n-1$ times:
$$\sum_{i=1}^nc_i\mathbf Y_i(x)=\mathbf 0\quad\text{for all }x.$$

### Definition — Fundamental matrix and Wronskian

The **fundamental matrix** of solution vectors is $\mathsf M=\big(\mathbf Y_1\ \cdots\ \mathbf Y_n\big)$, with the $\mathbf Y_i$ as columns. The **Wronskian** $W(x)$ of $n$ functions $y_i(x)$ ($i=1,\dots,n$) is
$$W(x)=\det\big(\mathbf Y_1\ \cdots\ \mathbf Y_n\big)=\begin{vmatrix}y_1&\cdots&y_n\\y_1'&\cdots&y_n'\\\vdots&&\vdots\\y_1^{(n-1)}&\cdots&y_n^{(n-1)}\end{vmatrix}.$$

### Wronskian test for linear independence

The equation above for linear dependence reads $\mathsf M\mathbf c=\mathbf 0$. It has non-trivial solutions only if $\mathsf M$ is not invertible, i.e. $W=0$. Therefore
$$\{y_i(x)\}\text{ linearly dependent}\ \Rightarrow\ W(x)=0\ \text{ for all }x.$$
It follows that if **$W(x)\ne0$ for some $x$, then $\{y_i(x)\}$ is linearly independent.**

**N.B.** $W(x)=0$ for all $x$ does **not** necessarily imply that $\{y_i(x)\}$ are linearly dependent.

**Example.** $y''+4y=0$ gives $y_1=\cos2x$, $y_2=\sin2x$, and
$$\begin{aligned}
W(x)=\begin{vmatrix}y_1&y_2\\y_1'&y_2'\end{vmatrix}&=\begin{vmatrix}\cos2x&\sin2x\\-2\sin2x&2\cos2x\end{vmatrix}\\
&=2\cos^22x+2\sin^22x\\
&=2.
\end{aligned}$$
$W\ne0$, so $y_1,y_2$ are linearly independent.

## 2.4 Abel's theorem

### Abel's theorem

Given any two solutions of
$$y''+p(x)y'+q(x)y=0,$$
if $p(x)$ and $q(x)$ are continuous on an interval $I$, then either $W(x)=0$ for all $x\in I$, or $W(x)\ne0$ for all $x\in I$.

**Proof.** $W=y_1y_2'-y_2y_1'$, so
$$\begin{aligned}
W'&=y_1y_2''+y_1'y_2'-y_2'y_1'-y_2y_1''\\
&=-y_1(py_2'+qy_2)+y_2(py_1'+qy_1) &&(y_1,y_2\text{ solve the ODE})\\
&=-p(x)W(x).
\end{aligned}$$
This is a separable ODE for $W(x)$:
$$W(x)=W(x_0)\underbrace{\exp\Big(-\int_{x_0}^xp(u)\,du\Big)}_{\text{never zero}},$$
**Abel's identity**. Therefore $W(x_0)=0\Rightarrow W(x)=0$ for all $x$, and $W(x_0)\ne0\Rightarrow W(x)\ne0$ for all $x$.

**Geometric interpretation.** The solution vectors are always collinear or never collinear as $x$ varies.

**Corollary.** If $p(x)=0$, then $W(x)$ is constant.

So we can find $W(x)$ without knowing the solutions of the ODE.

**Example (Bessel's equation).**
$$x^2y''+xy'+(x^2-n^2)y=0,\qquad\text{i.e.}\qquad y''+\underbrace{\frac1x}_{p(x)}y'+\Big(1-\frac{n^2}{x^2}\Big)y=0.$$
Abel's identity gives
$$\begin{aligned}
W(x)&=W(x_0)\exp\Big(-\int_{x_0}^x\frac{du}u\Big)\\
&=W(x_0)\exp\Big(-\ln\frac x{x_0}\Big)\\
&=W(x_0)\frac{x_0}x.
\end{aligned}$$

**Application.** Abel's identity can be used to find a second solution $y_2$ given a known solution $y_1$:
$$y_1y_2'-y_2y_1'=W(x_0)\exp\Big(-\int_{x_0}^xp(u)\,du\Big).$$
Dividing by $y_1^2$,
$$\frac{y_2'}{y_1}-\frac{y_2y_1'}{y_1^2}=\frac d{dx}\Big(\frac{y_2}{y_1}\Big)=\frac{W(x_0)}{y_1^2}\exp\Big(-\int_{x_0}^xp(u)\,du\Big),$$
the same as we had using the [[#Reduction of order|reduction of order]] method.

**Generalisation.** Abel's theorem holds for solutions of $n$th-order linear homogeneous ODEs, with a generalisation of Abel's identity (see Example Sheet 3, Q7).

## 2.5 Linear equidimensional ODEs

These are related to ODEs with constant coefficients.

### Definition — Equidimensional ODE

A linear second-order ODE is **equidimensional** if it has the form
$$ax^2y''+bxy'+cy=f(x).\tag{$*$}$$

**Scaling property** of solutions of the homogeneous equation: if $g(x)$ is a solution of $(*)$ with $f(x)=0$, then so is $y=g(\alpha x)$. Indeed,
$$\frac{dy}{dx}=\frac{dg(\alpha x)}{dx}=\frac{dg(\alpha x)}{d(\alpha x)}\cdot\frac{d(\alpha x)}{dx}=\alpha g'(\alpha x),$$
so $x\frac{dy}{dx}=(\alpha x)g'(\alpha x)$ and $x^2\frac{d^2y}{dx^2}=(\alpha x)^2g''(\alpha x)$. Therefore, with $u=\alpha x$,
$$\begin{aligned}
ax^2\frac{d^2y}{dx^2}+bx\frac{dy}{dx}+cy&=a(\alpha x)^2g''(\alpha x)+b(\alpha x)g'(\alpha x)+cg(\alpha x)\\
&=au^2g''(u)+bug'(u)+cg(u)=0 &&(g\text{ satisfies }(*)).
\end{aligned}$$

### Solving equidimensional ODEs

**By eigenfunctions.** $x\frac d{dx}x^k=kx^k$, so $x^k$ is an eigenfunction of $x\frac d{dx}$ with eigenvalue $k$. Look for a C.F. of $(*)$ of the form $y_c=x^k$:
$$x^k\big[ak(k-1)+bk+c\big]=0\iff ak^2+k(b-a)+c=0,$$
with roots $k_1,k_2$. If $k_1\ne k_2$, the general C.F. is
$$y_c=Ax^{k_1}+Bx^{k_2}.$$
What if $k_1=k_2$?

**By substitution.** Substitute $z=\ln x$ ($x=e^z$). Then
$$\frac{dy}{dz}=\frac{dy}{dx}\cdot\underbrace{\frac{dx}{dz}}_{e^z=x}=x\frac{dy}{dx},\qquad\frac{d^2y}{dz^2}=\underbrace{e^z\frac{dy}{dx}}_{x\frac{dy}{dx}}+\underbrace{e^{2z}\frac{d^2y}{dx^2}}_{x^2\frac{d^2y}{dx^2}}.$$
So $(*)$ becomes
$$\begin{aligned}
a\Big(\frac{d^2y}{dz^2}-\frac{dy}{dz}\Big)+b\frac{dy}{dz}+cy&=f(e^z)\\
\iff\quad a\frac{d^2y}{dz^2}+(b-a)\frac{dy}{dz}+cy&=f(e^z),
\end{aligned}$$
which has constant coefficients. Then $y_c\propto e^{\lambda z}$ with
$$a\lambda^2+(b-a)\lambda+c=0$$
(the same equation as for $k_1,k_2$), so
$$y_c=Ae^{k_1z}+Be^{k_2z}=Ax^{k_1}+Bx^{k_2},\qquad A,B\text{ constants}.$$
**Degenerate case** ($k_1=k_2=k$):
$$y_c=Ae^{kz}+Bze^{kz}=Ax^k+B(\ln x)x^k,$$
so $(\ln x)x^k$ is the other C.F.

## 3. Inhomogeneous (forced) second-order ODEs

Methods to find a P.I.

## 3.1 Constant coefficients

### Trial particular integrals

For
$$a\frac{d^2y}{dx^2}+b\frac{dy}{dx}+cy=f(x),$$
with $f(x)$ the **forcing function**:

| $f(x)$ | try $y_p$ of the form |
| --- | --- |
| $e^{mx}$ | $Ae^{mx}$ |
| $\sin kx$ or $\cos kx$ | $A\sin kx+B\cos kx$ |
| polynomial $P_n(x)$ | polynomial $Q_n(x)$ |

Since the equation is linear, we can superpose terms.

**Example.** $y''-5y'+6y=2x+e^{4x}$. Try
$$y_p=\underbrace{Ax+B}_{\text{for }2x}+\underbrace{Ce^{4x}}_{\text{for }e^{4x}},\qquad y_p'=A+4Ce^{4x},\qquad y_p''=16Ce^{4x}.$$
Substituting,
$$\underbrace{(16C-20C+6C)}_{=1}e^{4x}+\underbrace{6A}_{=2}x+\underbrace{(-5A+6B)}_{=0}=2x+e^{4x},$$
so $C=\frac12$, $A=\frac13$, $B=\frac5{18}$. The C.F. is $y_c=\alpha e^{2x}+\beta e^{3x}$ ($\alpha,\beta$ constants), so the general solution is
$$y=\alpha e^{2x}+\beta e^{3x}+\frac12e^{4x}+\frac13x+\frac5{18}.$$

### Resonance

What if the forcing term $f(x)$ involves a term that is in a C.F.? Use detuning.

**Example.**
$$y''+\omega_0^2y=\sin\omega_0t.\tag{$*$}$$
The left side is SHM at angular frequency $\omega_0$, and the forcing term is at the "natural frequency" $\omega_0$: the oscillator is driven **resonantly**. Here $y_c(t)=A\sin\omega_0t+B\cos\omega_0t$.

"Detuned" equation, with $\omega\ne\omega_0$:
$$y''+\omega_0^2y=\sin\omega t.\tag{$\dagger$}$$
Try $y_p(t)=C\sin\omega t+D\cos\omega t$; then $D=0$ and
$$(-\omega^2+\omega_0^2)C=1\ \Rightarrow\ C=\frac1{\omega_0^2-\omega^2}.$$
The limit $\omega\to\omega_0$ doesn't exist. Add in a C.F. to regularise the limit:
$$y_p(t)=\frac1{\omega_0^2-\omega^2}\big(\sin\omega t-\underbrace{\sin\omega_0t}_{\text{a C.F.}}\big)$$
still satisfies $(\dagger)$. Evaluate the indeterminate limit using [[L'Hôpital's Rule|L'Hôpital's rule]] (differentiating top and bottom with respect to $\omega$):
$$\lim_{\omega\to\omega_0}y_p(t)=\lim_{\omega\to\omega_0}\frac{t\cos\omega t}{-2\omega}=-\frac t{2\omega_0}\cos\omega_0t.$$
Therefore the P.I. of the original equation $(*)$ is
$$y_p(t)=-\frac t{2\omega_0}\cos\omega_0t,$$
with **linear growth in amplitude**.

```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[>=latex,xscale=0.5,yscale=0.32]
  \draw[->] (0,0) -- (21,0) node[right] {$t$};
  \draw[->] (0,-6.5) -- (0,6.8) node[above] {$y_p$};
  \draw[gray,dashed,domain=0:20] plot (\x,{0.3*\x}) node[right] {\small$\frac t{2\omega_0}$};
  \draw[gray,dashed,domain=0:20] plot (\x,{-0.3*\x});
  \draw[blue,thick,domain=0:20,samples=300] plot (\x,{-0.3*\x*cos(\x*90)});
\end{tikzpicture}
\end{document}
```
*Resonant response $y_p=-\frac t{2\omega_0}\cos\omega_0t$ (schematic): the oscillation stays at frequency $\omega_0$ while its amplitude grows linearly between the dashed lines $\pm\frac t{2\omega_0}$.*

**General rule.** If the forcing term is a linear combination of C.F.s, the P.I. is
$$y_p(t)=t\times(\text{non-resonant P.I.}),$$
with the non-resonant P.I. from the [[#Trial particular integrals|table above]].

**Note.** If the homogeneous equation is degenerate, we may need $t^2\times(\text{non-resonant P.I.})$.

### Resonance in equidimensional equations

Consider $ax^2y''+bxy'+cy=f(x)$ with $y_c=Ax^{k_1}+Bx^{k_2}$ (assume non-degenerate, $k_1\ne k_2$).
- If $f(x)\propto x^m$, the P.I. is $Cx^m$ for $m\ne k_1,k_2$.
- If $f(x)\propto x^{k_1}$ (or $x^{k_2}$), the P.I. is $y_p\propto(\ln x)x^{k_1}$. (This follows from transforming with $z=\ln x$: $ze^{k_1z}\propto(\ln x)x^{k_1}$.)

**Note.** If degenerate ($k_1=k_2$), we need $(\ln x)^2x^{k_1}$.

## 3.2 Variation of parameters

### Variation of parameters

A systematic method to find a P.I. given two linearly independent C.F.s. Consider
$$y''+p(x)y'+q(x)y=f(x)\tag{$*$}$$
with linearly independent C.F.s $y_1$ and $y_2$. Use the solution vectors $\mathbf Y_1(x)$ and $\mathbf Y_2(x)$ as a basis in phase space at any $x$ to write the solution vector for the P.I. as
$$\mathbf Y_p(x)=u(x)\mathbf Y_1(x)+v(x)\mathbf Y_2(x).$$
In components:
$$\begin{aligned}
y_p(x)&=u(x)y_1(x)+v(x)y_2(x),\\
y_p'(x)&=u(x)y_1'(x)+v(x)y_2'(x).
\end{aligned}\qquad\begin{aligned}&(\dagger)\\&(\dagger\dagger)\end{aligned}$$
Differentiating $(\dagger\dagger)$: $y_p''=uy_1''+u'y_1'+vy_2''+v'y_2'$. So, from $(*)$,
$$\begin{aligned}
f(x)&=y_p''+py_p'+qy_p\\
&=uy_1''+u'y_1'+v'y_2'+vy_2''+p(x)\big[uy_1'+vy_2'\big]+q(x)\big[uy_1+vy_2\big]\\
&=u'y_1'+v'y_2' &&(y_1,y_2\text{ are C.F.s}).
\end{aligned}$$
But $(\dagger\dagger)$ must be consistent with $\frac d{dx}(\dagger)$:
$$\frac d{dx}y_p=uy_1'+u'y_1+vy_2'+v'y_2=y_p'=uy_1'+vy_2'\quad(\dagger\dagger)\ \Rightarrow\ u'y_1+v'y_2=0.$$
Combining, with the fundamental matrix:
$$\begin{pmatrix}y_1&y_2\\y_1'&y_2'\end{pmatrix}\begin{pmatrix}u'\\v'\end{pmatrix}=\begin{pmatrix}0\\f\end{pmatrix}\ \Rightarrow\ \begin{pmatrix}u'\\v'\end{pmatrix}=\frac1W\begin{pmatrix}y_2'&-y_2\\-y_1'&y_1\end{pmatrix}\begin{pmatrix}0\\f\end{pmatrix},$$
with $W=y_1y_2'-y_2y_1'$. So
$$u'=-\frac{y_2}Wf,\qquad v'=\frac{y_1}Wf.$$
Integrating,
$$y_p(x)=-y_1(x)\int^x\frac{y_2(u)f(u)}{W(u)}\,du+y_2(x)\int^x\frac{y_1(u)f(u)}{W(u)}\,du.$$
Changing the lower limit just adds multiples of the C.F.

> [!note] Explanation
> There are two unknown functions $u,v$ but only one equation $(*)$, so we are free to impose one extra condition; choosing $(\dagger\dagger)$ (equivalently $u'y_1+v'y_2=0$) keeps $y_p'$ free of $u'$ and $v'$, so $y_p''$ contains only first derivatives of $u,v$. The matrix is invertible because $W\ne0$ for linearly independent solutions ([[#Abel's theorem]]).

**Example.** $y''+4y=\sin2x$, so $f(x)=\sin2x$. The C.F.s are $y_1=\sin2x$, $y_2=\cos2x$, giving $W(x)=y_1y_2'-y_2y_1'=-2$. The forcing is resonant. Then
$$\begin{aligned}
y_p(x)&=\frac{\sin2x}2\int^x\underbrace{\cos2u\sin2u}_{\frac12\sin4u}\,du-\frac{\cos2x}2\int^x\underbrace{\sin2u\sin2u}_{\frac12(1-\cos4u)}\,du\\
&=\frac14\sin2x\Big(-\frac14\underbrace{\cos4x}_{2\cos^22x-1}\Big)-\frac14\cos2x\Big(x-\frac14\underbrace{\sin4x}_{2\sin2x\cos2x}\Big)\\
&=-\frac14x\cos2x+\frac1{16}\sin2x.
\end{aligned}$$
The term $-\frac14x\cos2x$ is $x\times$(C.F.), as expected for resonance; $\frac1{16}\sin2x$ is a C.F., so it can be removed.

## 4. Forced ODEs — transient and damping

### Damped mass–spring system

```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[>=latex]
  % ground
  \draw[thick] (-1.5,0) -- (3.5,0);
  \foreach \x in {-1.4,-1.1,...,3.4} {\draw (\x,0) -- (\x-0.2,-0.2);}
  % spring
  \draw (0,0) -- (0,0.3);
  \draw (0,0.3) -- (0.2,0.4) -- (-0.2,0.55) -- (0.2,0.7) -- (-0.2,0.85) -- (0.2,1.0) -- (-0.2,1.15) -- (0.2,1.3) -- (0,1.4);
  \draw (0,1.4) -- (0,1.8);
  % dashpot
  \draw (2,0) -- (2,0.6);
  \draw (1.75,0.6) -- (1.75,1.2) (2.25,0.6) -- (2.25,1.2) (1.75,0.6) -- (2.25,0.6);
  \draw (1.85,1.0) -- (2.15,1.0); \draw (2,1.0) -- (2,1.8);
  % mass
  \draw[thick,fill=gray!15] (-0.6,1.8) rectangle (2.6,2.6);
  \node at (1,2.2) {mass $m$};
  % forces
  \draw[->,thick] (1,2.6) -- (1,3.4) node[above] {$F(t)$ (driving force)};
  \draw[->] (-0.6,0.9) -- (-0.6,1.5) node[left] {$-ky$ (restoring)};
  \draw[->] (2.6,0.9) -- (2.6,1.5) node[right] {$-b\dot y$ (damping)};
  \draw[->] (-1.4,2.0) -- (-1.4,2.9) node[left] {$y(t)$};
\end{tikzpicture}
\end{document}
```
*A mass on a spring (restoring force $-ky$) and a damper (damping force $-b\dot y$), driven by $F(t)$; $y(t)$ is the displacement from equilibrium.*

Newton's second law:
$$m\ddot y=\sum\text{forces}=-ky-b\dot y+F(t),\qquad\text{i.e.}\qquad m\ddot y+b\dot y+ky=F(t),$$
with $m,b,k$ positive constants ($k$ is the spring constant).

For $F(t)=0$ and $b=0$: SHM at angular frequency $\omega_0=\sqrt{k/m}$.

For convenience use the dimensionless time coordinate $\tau=\omega_0t$, so $\frac{dy}{dt}=\omega_0\frac{dy}{d\tau}$. Writing $y'=\frac{dy}{d\tau}$, the equation becomes
$$y''+2\kappa y'+y=f(\tau),\qquad2\kappa=\frac{b\omega_0}k=\frac b{m\omega_0},\qquad f(\tau)=\frac{F(t)}k.$$

> [!note] Explanation
> Two different letters appear here: $k$ is the spring constant and $\kappa$ (kappa) is the damping parameter. Substituting $\frac{d}{dt}=\omega_0\frac{d}{d\tau}$ gives $m\omega_0^2y''+b\omega_0y'+ky=F$; since $m\omega_0^2=k$, dividing by $k$ leaves $y''+\frac{b\omega_0}ky'+y=\frac Fk$. The coefficient $\frac{b\omega_0}k=\frac b{m\omega_0}$ has no units, which is why $\kappa$ is called dimensionless.

### Free response — light, critical and heavy damping

The free ("unforced" or "natural") response is described by one dimensionless parameter $\kappa$:
$$y''+2\kappa y'+y=0.$$
Trying $y\propto e^{\lambda\tau}$ gives the characteristic equation $\lambda^2+2\kappa\lambda+1=0$, so
$$\lambda_1,\lambda_2=-\kappa\pm\sqrt{\kappa^2-1}.$$

**1) Light damping ("underdamping"), $\kappa<1$.** $\lambda_1,\lambda_2$ are complex: $-\kappa\pm i\sqrt{1-\kappa^2}$. General solution:
$$y(\tau)=e^{-\kappa\tau}\Big(A\sin\big(\sqrt{1-\kappa^2}\,\tau\big)+B\cos\big(\sqrt{1-\kappa^2}\,\tau\big)\Big).$$

```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[>=latex,xscale=0.55,yscale=1.4]
  \draw[->] (0,0) -- (20.5,0) node[right] {$\tau$};
  \draw[->] (0,-1.3) -- (0,1.4) node[above] {$y(\tau)$};
  \draw[red,thick,domain=0:20,samples=100] plot (\x,{exp(-0.15*\x)});
  \node[red] at (4.5,0.75) {$e^{-\kappa\tau}$};
  \draw[red,thick,domain=0:20,samples=100] plot (\x,{-exp(-0.15*\x)});
  \draw[blue,thick,domain=0:20,samples=300] plot (\x,{exp(-0.15*\x)*(0.5*sin(deg(0.989*\x))+0.6*cos(deg(0.989*\x)))});
\end{tikzpicture}
\end{document}
```
*Damped oscillator ($\kappa<1$, here $\kappa=0.15$): oscillation inside the decaying envelope $\pm e^{-\kappa\tau}$.*

The oscillations are at (angular) frequency
$$\omega_{\text{freq}}=\sqrt{1-\kappa^2}\,\omega_0\ \to\ \omega_0\quad\text{as }\kappa\to0,\qquad\text{period}=\frac{2\pi}{\omega_0\sqrt{1-\kappa^2}}.$$

**2) Critical damping, $\kappa=1$.** Degenerate case $\lambda_1=\lambda_2=-\kappa=-1$. General solution:
$$y(\tau)=e^{-\kappa\tau}(A+B\tau)=e^{-\tau}(A+B\tau).$$

```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[>=latex,xscale=0.8,yscale=2]
  \draw[->] (0,0) -- (8.5,0) node[right] {$\tau$};
  \draw[->] (0,-0.1) -- (0,1.2) node[above] {$y(\tau)$};
  \draw[blue,thick,domain=0:8,samples=100] plot (\x,{exp(-\x)*(0.6+1.6*\x)});
\end{tikzpicture}
\end{document}
```
*Critical damping (here $A=0.6$, $B=1.6$): at most one rise, then decay with no oscillation.*

**3) Heavy damping ("overdamping"), $\kappa>1$.** $\lambda_1$ and $\lambda_2$ are real; take $|\lambda_1|<|\lambda_2|$ without loss of generality:
$$\lambda_1=\underbrace{-\kappa+\sqrt{\kappa^2-1}}_{<0},\qquad\lambda_2=\underbrace{-\kappa-\sqrt{\kappa^2-1}}_{<0}.$$
General solution:
$$y(\tau)=\underbrace{Ae^{-|\lambda_1|\tau}}_{\text{dominates long-term motion (if present)}}+Be^{-|\lambda_2|\tau}.$$

```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[>=latex,xscale=0.8,yscale=1.6]
  \draw[->] (0,0) -- (8.5,0) node[right] {$\tau$};
  \draw[->] (0,-1.1) -- (0,1.3) node[above] {$y(\tau)$};
  \draw[blue,thick,domain=0:8,samples=100] plot (\x,{1.0*exp(-0.27*\x)});
  \node[blue] at (3.2,0.75) {$Ae^{-|\lambda_1|\tau}$};
  \draw[red,thick,domain=0:8,samples=100] plot (\x,{-0.7*exp(-3.73*\x)});
  \node[red] at (1.3,-0.6) {$Be^{-|\lambda_2|\tau}$};
  \draw[green!60!black,thick,domain=0:8,samples=150] plot (\x,{1.0*exp(-0.27*\x)-0.7*exp(-3.73*\x)});
\end{tikzpicture}
\end{document}
```
*Heavy damping (here $\kappa=2$, $A=1$, $B=-0.7$): the sum (green) of a slowly decaying term (blue) and a quickly decaying term (red); the slow one dominates at large $\tau$.*

**Note.** The unforced response eventually decays to zero (in all three cases).

### Forced response — transient and steady state

Initially the solution is C.F. + P.I. (the "**transient**" response), but the system settles down to a specific P.I. (the "**steady-state**" response) for any choice of initial conditions. Take $F(t)=F_0\sin\omega t$.

**Example.**
$$\ddot y+\mu\dot y+\omega_0^2y=\frac{F_0}m\sin\omega t,\qquad\mu=\frac bm,\qquad\kappa=\frac\mu{2\omega_0}.$$
Assume light damping ($\kappa<1\Rightarrow\mu<2\omega_0$). The C.F. is
$$y_c(t)=e^{-\mu t/2}\big(A\sin\omega_{\text{freq}}t+B\cos\omega_{\text{freq}}t\big),\qquad\omega_{\text{freq}}=\sqrt{\omega_0^2-\mu^2/4}.$$

> [!note] Explanation
> This is the same as case 1 in the original time $t$: $\kappa\tau=\frac\mu{2\omega_0}\cdot\omega_0t=\frac{\mu t}2$, and $\sqrt{1-\kappa^2}\,\omega_0=\sqrt{\omega_0^2-\mu^2/4}$. The factor $e^{-\mu t/2}$ is why the C.F. (transient) dies away, leaving only the P.I.

Try $y_p(t)=\frac{F_0}m(C\sin\omega t+D\cos\omega t)$. This gives
$$y_p(t)=\frac{F_0/m}{(\omega_0^2-\omega^2)^2+\mu^2\omega^2}\Big((\omega_0^2-\omega^2)\sin\omega t-\mu\omega\cos\omega t\Big).$$

> [!note] Explanation
> Substituting and comparing coefficients of $\sin\omega t$ and $\cos\omega t$ gives $(\omega_0^2-\omega^2)C-\mu\omega D=1$ and $\mu\omega C+(\omega_0^2-\omega^2)D=0$. Solving this pair of linear equations gives $C=\frac{\omega_0^2-\omega^2}\Delta$ and $D=-\frac{\mu\omega}\Delta$ with $\Delta=(\omega_0^2-\omega^2)^2+\mu^2\omega^2$. The amplitude of $y_p$ is $\frac{F_0/m}{\sqrt\Delta}$, which does not depend on the initial conditions.

```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[>=latex,xscale=0.32,yscale=0.9]
  \draw[->] (0,0) -- (31,0) node[right] {$t$};
  \draw[->] (0,-2.6) -- (0,2.8);
  \draw[dashed] (0,2.08) -- (30,2.08) node[right] {\small amplitude of $y_p$};
  \draw[dashed] (0,-2.08) -- (30,-2.08);
  \draw[red,thick,domain=0:20,samples=200] plot (\x,{1.38*exp(-0.2*\x)*cos(deg(0.98*\x))});
  \draw[red,dotted,domain=0:20,samples=100] plot (\x,{1.38*exp(-0.2*\x)});
  \draw[red,dotted,domain=0:20,samples=100] plot (\x,{-1.38*exp(-0.2*\x)});
  \node[red] at (-1.2,1.3) {$y_c$};
  \draw[blue,thick,domain=0:30,samples=400] plot (\x,{(0.36*sin(deg(0.8*\x))-0.32*cos(deg(0.8*\x)))/0.232+1.38*exp(-0.2*\x)*cos(deg(0.98*\x))});
  \node[blue] at (24,-2.45) {$y_p+y_c$};
\end{tikzpicture}
\end{document}
```
*Transient and steady state (here $\omega_0=1$, $\mu=0.4$, $\omega=0.8$, $y(0)=0$). The C.F. $y_c$ (red) dies away inside its envelope, and the full solution $y_p+y_c$ (blue) settles onto the steady-state oscillation between the dashed lines.*

## 5. Impulses and point forces

### Impulses and point forces

Consider a system that experiences a sudden force $F(t;\varepsilon)$ between $t=T-\varepsilon$ and $t=T+\varepsilon$, e.g. striking a mass on a spring:
$$m\ddot y+b\dot y+ky=F(t;\varepsilon)\qquad(\text{forced, damped oscillator}).$$

```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[>=latex,xscale=1.2,yscale=1.4]
  \draw[->] (0,0) -- (5,0) node[right] {$t$};
  \draw[->] (0,0) -- (0,1.6) node[above] {$F(t;\varepsilon)$};
  \draw[blue,thick,domain=1.5:3.5,samples=80] plot (\x,{1.2*(cos(deg(pi*(\x-2.5)))+1)/2});
  \foreach \x/\l in {1.5/T-\varepsilon,2.5/T,3.5/T+\varepsilon} {\draw (\x,0.05) -- (\x,-0.05) node[below] {$\l$};}
\end{tikzpicture}
\end{document}
```
*A sudden force acting only for $T-\varepsilon<t<T+\varepsilon$.*

It is mathematically convenient to consider the limit of a sudden impulse, $\varepsilon\to0$, with the **impulse**
$$I=\int_{T-\varepsilon}^{T+\varepsilon}F(t;\varepsilon)\,dt$$
held constant. Integrate the ODE from $T-\varepsilon$ to $T+\varepsilon$ and take the limit $\varepsilon\to0^+$:
$$\lim_{\varepsilon\to0^+}\Big(m\big[\dot y\big]_{T-\varepsilon}^{T+\varepsilon}+\underbrace{b\big[y\big]_{T-\varepsilon}^{T+\varepsilon}}_{\to0\text{ if }y\text{ continuous}}+\underbrace{k\int_{T-\varepsilon}^{T+\varepsilon}y\,dt}_{\to0\text{ if }y\text{ remains finite}}\Big)=\lim_{\varepsilon\to0^+}\int_{T-\varepsilon}^{T+\varepsilon}F(t;\varepsilon)\,dt=I.$$
Therefore
$$\lim_{\varepsilon\to0^+}\Big(m\big[\dot y\big]_{T-\varepsilon}^{T+\varepsilon}\Big)=I:$$
the **velocity is discontinuous** at $t=T$.

**Note.** As $\varepsilon\to0$, only the impulse $I$ matters for the subsequent motion (not the details of $F(t;\varepsilon)$).

```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[>=latex,xscale=0.45,yscale=1.2]
  \draw[->] (0,0) -- (21,0) node[right] {$t$};
  \draw[->] (0,-1.1) -- (0,1.3) node[above] {$y(t)$};
  \draw[blue,thick] (0,0) -- (4,0);
  \draw[blue,thick,domain=4:20,samples=200] plot (\x,{exp(-0.15*(\x-4))*sin(deg(0.9*(\x-4)))});
  \draw (4,0.05) -- (4,-0.05) node[below] {$T$};
\end{tikzpicture}
\end{document}
```
*An oscillator at rest is struck at $t=T$: $y$ stays continuous but $\dot y$ jumps, and the motion afterwards is a free (damped) oscillation.*

## 5.1 Dirac delta function

The Dirac delta function formalises the idea of an impulsive force. Consider a family of functions $D(t;\varepsilon)$ such that
$$\lim_{\varepsilon\to0}D(t;\varepsilon)=0\quad\text{for all }t\ne0,\qquad\int_{-\infty}^\infty D(t;\varepsilon)\,dt=1\quad(\text{unit impulse}).$$
(The impulsive force considered earlier is $F(t;\varepsilon)=I\,D(t-T;\varepsilon)$.) One example is
$$D(t;\varepsilon)=\frac{e^{-t^2/\varepsilon^2}}{\varepsilon\sqrt\pi}.$$

```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[>=latex,xscale=1.4,yscale=0.9]
  \draw[->] (-3,0) -- (3.2,0) node[right] {$t$};
  \draw[->] (0,0) -- (0,3.2) node[above] {$D(t;\varepsilon)$};
  \draw[blue,thick,domain=-1.2:1.2,samples=120] plot (\x,{exp(-(\x/0.2)^2)/(0.2*sqrt(pi))});
  \draw[red,thick,domain=-2.9:2.9,samples=120] plot (\x,{exp(-(\x/1.2)^2)/(1.2*sqrt(pi))});
  \node[blue] at (0.7,2.5) {\small small $\varepsilon$};
  \node[red] at (2.1,0.55) {\small large $\varepsilon$};
\end{tikzpicture}
\end{document}
```
*$D(t;\varepsilon)=\frac{e^{-t^2/\varepsilon^2}}{\varepsilon\sqrt\pi}$ for two values of $\varepsilon$: as $\varepsilon\to0$ the spike gets taller and narrower while its area stays $1$.*

The family is not unique, but for any such family, $\lim_{\varepsilon\to0}$ yields the Dirac delta function. (Precisely, the unit area must concentrate at $0$: take $D\ge0$ with the area outside any interval $(-a,a)$ tending to $0$, as for the Gaussian above; a unit-area bump sliding off to infinity also satisfies the two conditions but does not give $\delta$.)

### Definition — Dirac delta function

The **Dirac delta function** is defined by
$$\delta(t)=\lim_{\varepsilon\to0}D(t;\varepsilon).$$
(Technically it is a distribution, not a function: it only makes sense inside an integral.)

**Properties.**
1. $\delta(t)=0$ for all $t\ne0$.
2. $\int_{-\infty}^\infty\delta(t)\,dt=1$.
3. For all functions $g(t)$ that are continuous at $t=0$,
$$\int_{-\infty}^\infty g(t)\delta(t)\,dt=\lim_{\varepsilon\to0}\int_{-\infty}^\infty g(t)D(t;\varepsilon)\,dt=g(0)\lim_{\varepsilon\to0}\int_{-\infty}^\infty D(t;\varepsilon)\,dt=g(0).$$

More generally, for $g$ continuous at $t=t_0$,
$$\int_a^bg(t)\,\delta(t-t_0)\,dt=\begin{cases}g(t_0)&\text{if }a<t_0<b,\\0&\text{if }t_0<a\text{ or }t_0>b,\\\text{undefined}&\text{otherwise.}\end{cases}$$

> [!note] Explanation
> Property 3 works because for small $\varepsilon$, $D(t;\varepsilon)$ is non-negligible only very close to $t=0$, where $g(t)\approx g(0)$; so $g$ can be taken outside the integral as the constant $g(0)$. "Undefined otherwise" covers $t_0=a$ or $t_0=b$, where the spike sits exactly on an endpoint.

## 5.2 Delta-function forcing

### Delta-function forcing and the jump condition

Consider
$$y''+p(x)y'+q(x)y=\delta(x),\tag{$*$}$$
with $p,q$ continuous. For $x<0$ and $x>0$, $y''+p(x)y'+q(x)y=0$. But there is a discontinuity in $y'$ at $x=0$: integrating $(*)$,
$$\lim_{\varepsilon\to0^+}\int_{-\varepsilon}^\varepsilon(*)\,dx:\qquad\lim_{\varepsilon\to0^+}\big[y'\big]_{-\varepsilon}^\varepsilon+p(0)\underbrace{\lim_{\varepsilon\to0^+}\big[y\big]_{-\varepsilon}^\varepsilon}_{\to0\text{ if }y\text{ continuous}}+\underbrace{\lim_{\varepsilon\to0^+}\int_{-\varepsilon}^\varepsilon qy\,dx}_{\to0\text{ if finite}}=1,$$
so
$$\lim_{\varepsilon\to0^+}\big[y'\big]_{-\varepsilon}^\varepsilon=1\qquad(\text{the "jump condition"}).$$

**Note.** Continuity of $y$ at $x=0$ is required: otherwise $y'\propto\delta(x)$ (see later) around $x=0$, and $y''$ is even worse behaved.

**General rule.** The highest-order term in the ODE deals with the $\delta$-function forcing: for a second-order equation $y''$ contains the $\delta$, so $y'$ jumps while $y$ stays continuous (for an $n$th-order equation, the $(n-1)$th derivative jumps).

**Example.** $y''-y=3\delta\big(x-\frac\pi2\big)$, with $y=0$ at $x=0$ and $x=\pi$.
- For $0\le x<\frac\pi2$: $y''-y=0$, so $y=A\sinh x$ ($A$ constant, since $y(0)=0$).
- For $\frac\pi2<x\le\pi$: $y''-y=0$, so $y=C\sinh(\pi-x)$ ($C$ constant, since $y(\pi)=0$).

Join at $x=\frac\pi2$:
- $y$ continuous $\Rightarrow$ $A\sinh\frac\pi2=C\sinh\frac\pi2$, so $A=C$.
- Jump condition, $\lim_{\varepsilon\to0^+}\big[y'\big]_{\pi/2-\varepsilon}^{\pi/2+\varepsilon}=3$:
$$-C\cosh\Big(\pi-\frac\pi2\Big)-A\cosh\frac\pi2=3.$$

Therefore
$$A=C=-\frac3{2\cosh\frac\pi2}.$$

```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[>=latex,xscale=1.4,yscale=1.2]
  \draw[->] (0,0) -- (3.5,0) node[right] {$x$};
  \draw[->] (0,-1.6) -- (0,0.6) node[above] {$y$};
  \draw[blue,thick,domain=0:1.5708,samples=60] plot (\x,{-3/(2*cosh(1.5708))*sinh(\x)});
  \draw[blue,thick,domain=1.5708:3.1416,samples=60] plot (\x,{-3/(2*cosh(1.5708))*sinh(3.1416-\x)});
  \draw[dotted] (1.5708,0) -- (1.5708,-1.37);
  \draw (1.5708,0.05) -- (1.5708,-0.05); \node[above] at (1.5708,0) {$\frac\pi2$};
  \draw (3.1416,0.05) -- (3.1416,-0.05); \node[above] at (3.1416,0) {$\pi$};
\end{tikzpicture}
\end{document}
```
*The solution is continuous with a corner at $x=\frac\pi2$ (where $y=-\frac32\tanh\frac\pi2$); the slope jumps by $3$, from $-\frac32$ to $+\frac32$.*
