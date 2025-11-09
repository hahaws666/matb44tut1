# MATB44 - Week 9 Tutorial Teaching Notes

## Week 9 Topics

### Non-Homogeneous Linear ODEs with Constant Coefficients
- Methods: Undetermined Coefficients, Variation of Parameters, (optional) Annihilators
- Resonance and multiplicity adjustments
- RHS types: polynomials, exponentials, sines/cosines, and their products

## Definition and Theory

### General Form and Structure
- Linear ODE (constant coefficients):

  $$
  a_n \frac{d^n y}{dx^n} + a_{n-1} \frac{d^{n-1} y}{dx^{n-1}} + \cdots + a_1 \frac{dy}{dx} + a_0 y = g(x),\quad a_n\neq 0.
  $$
- Homogeneous part:

  $$
  a_n \frac{d^n y}{dx^n} + \cdots + a_0 y = 0 \quad\Rightarrow\quad y_h \text{ from characteristic roots}.
  $$
- Particular solution \(y_p\) satisfies the full equation. The general solution is \(y = y_h + y_p\).
- Superposition for RHS: if \(g(x)=g_1(x)+g_2(x)\), then \(y_p = y_{p,1}+y_{p,2}\) where each solves its part.

### Method of Undetermined Coefficients
- Choose a trial form similar to the RHS:
  - \(g(x)=P_m(x)\) (polynomial of degree \(m\)):
    try \(y_p = Q_m(x)\) (degree \(m\)).
  - \(g(x)=e^{ax}P_m(x)\): try \(y_p = e^{ax} Q_m(x)\).
  - $g(x)=\cos(bx)$ or $\sin(bx)$:
    try $y_p = A\cos(bx)+B\sin(bx)$.
  - $g(x)=e^{ax}\cos(bx)$ or $e^{ax}\sin(bx)$:
    try $y_p = e^{ax}\big(A\cos bx + B\sin bx\big)$.
- Resonance rule: if the trial form overlaps \(y_h\), multiply by \(x^s\), where \(s\) = multiplicity of the overlapping root (or conjugate pair) in the characteristic equation.
- Determine coefficients by substitution.

### Variation of Parameters (2nd order, standard form)
For \(y'' + p(x) y' + q(x) y = g(x)\), with a fundamental pair \(y_1,y_2\) and Wronskian \(W=y_1 y_2'-y_1' y_2\),
one particular solution is
$$
y_p = -y_1 \int \frac{y_2\,g}{W}\,dx + y_2 \int \frac{y_1\,g}{W}\,dx.
$$
Works for general RHS, even when undetermined coefficients is not applicable.

#### Proof (sketch)

Take a particular solution of the form
\[
y_p(x) = u_1(x)\,y_1(x) + u_2(x)\,y_2(x),
\]
with \(u_1,u_2\) differentiable. Impose the auxiliary condition
$$
u_1'(x)\,y_1(x) + u_2'(x)\,y_2(x) = 0
$$
to avoid second derivatives of \(u_1,u_2\). Then
$$
y_p' = u_1 y_1' + u_2 y_2',\qquad
y_p'' = u_1' y_1' + u_2' y_2' + u_1 y_1'' + u_2 y_2''.
$$
Substitute into \(y'' + p y' + q y = g\) and use that \(y_j\) (\(j=1,2\)) solve the homogeneous equation \(y_j'' + p y_j' + q y_j = 0\). This yields
$$
u_1' y_1' + u_2' y_2' = g.
$$
Together with the auxiliary condition we have the linear system for \(u_1',u_2'\):
$$
\begin{cases}
u_1' y_1 + u_2' y_2 = 0,\\
u_1' y_1' + u_2' y_2' = g.
\end{cases}
$$
Let the Wronskian be $W = y_1 y_2' - y_1' y_2 \neq 0$. By Cramer's rule,
$$
u_1' = -\,\frac{y_2 g}{W},\qquad
u_2' = \frac{y_1 g}{W}.
$$
Integrating gives
$$
u_1 = -\int \frac{y_2 g}{W}\,dx,\qquad
u_2 = \int \frac{y_1 g}{W}\,dx,
$$
and hence
\[
y_p = -y_1 \int \frac{y_2 g}{W}\,dx + y_2 \int \frac{y_1 g}{W}\,dx.
\]

### (Optional) Annihilator Method
- Idea: find a differential operator \(L\) that annihilates \(g(x)\) (i.e., \(L[g]=0\)).
- Apply \(L\) to both sides to obtain a higher-order homogeneous ODE, solve it, and then select the part corresponding to \(y_p\).

## Key Examples

### Example 1: First-Order Equation
Solve:
\[
y' + 2y = e^{-2x}
\]

Solution:
1) \(y_h: y' + 2y = 0 \Rightarrow y_h = C e^{-2x}\)
2) Particular (details). Try \(y_p = A x e^{-2x}\) (resonance):
   \[
   y_p' = A e^{-2x} - 2A x e^{-2x}.
   \]
   Substitute into LHS:
   \[
   (y_p' + 2y_p) = \big(A e^{-2x} - 2A x e^{-2x}\big) + 2\big(A x e^{-2x}\big) = A e^{-2x}.
   \]
   Match RHS \(e^{-2x}\) ⇒ \(A = 1\). Hence \(y_p = x e^{-2x}\).
3) \(y = C e^{-2x} + x e^{-2x}\)

---

### Example 2: First-Order with Exponential RHS (non-resonant)
Solve:
\[
y' + 2y = e^{-x}
\]

Solution:
1) Homogeneous: \(y' + 2y = 0 \Rightarrow y_h = C e^{-2x}\).
2) Particular (details). Try \(y_p = A e^{-x}\) (non-resonant with \(e^{-2x}\)):
   \[
   y_p' = -A e^{-x}.
   \]
   LHS:
   \[
   y_p' + 2y_p = \big(-A + 2A\big)e^{-x} = A e^{-x}.
   \]
   Match RHS \(e^{-x}\) ⇒ \(A = 1\). Hence \(y_p = e^{-x}\).
3) \(y = C e^{-2x} + e^{-x}\)

---

### Example 3: Trigonometric RHS via Variation of Parameters
Solve:
\[
y'' + y = \sin x
\]

Solution:
1) Homogeneous:
\[
y'' + y = 0 \Rightarrow y_h = C_1\cos x + C_2\sin x
\]
\[
y_1 = \cos x,\quad y_2 = \sin x,\quad W = y_1y_2' - y_1'y_2 = 1
\]

2) Particular via VOP:
\[
y_p = -y_1\int \frac{y_2g}{W}\,dx + y_2\int \frac{y_1g}{W}\,dx
\]
Substitute \( g = \sin x, W = 1 \):
\[
y_p = -\cos x\int \sin^2x\,dx + \sin x\int \sin x\cos x\,dx
\]

3) Integrate and simplify:
\[
\int \sin^2x\,dx = \frac{x}{2} - \frac{\sin(2x)}{4},\quad 
\int \sin x\cos x\,dx = \frac{\sin^2x}{2}
\]
\[
\Rightarrow\;
y_p = -\frac{x}{2}\cos x\quad(\text{terms in }\sin x\ \text{can be absorbed by }y_h)
\]

4) Final solution:
\[
y = C_1\cos x + C_2\sin x - \frac{1}{2}x\cos x
\]

---
### Example 4: Resonance with Mixed Polynomial–Trig–Exponential Forcing (Harder)
Solve:
\[
y'' - 2y' + 2y = e^{x}(1+x)\cos x
\]

Solution:
1) Homogeneous: characteristic \(r^2 - 2r + 2=0 \Rightarrow r=1\pm i\).
\[
y_h = e^{x}(C_1\cos x + C_2\sin x)
\]

2) Substitute \(y=e^{x}u\):
\[
y' = e^{x}(u'+u),\quad y'' = e^{x}(u''+2u'+u),
\]
so the ODE reduces to
\[
u'' + u = (1+x)\cos x.
\]

3) Undetermined coefficients with resonance. Try
\[
u_p = x\big[(a x + b)\sin x + (c x + d)\cos x\big].
\]
Matching coefficients in \(u_p''+u_p = (1+x)\cos x\) gives
\[
a=\tfrac{1}{4},\quad b=\tfrac{1}{2},\quad c=0,\quad d=\tfrac{1}{4},
\]
hence
\[
u_p = \frac{x}{4}\cos x + \left(\frac{x^2}{4} + \frac{x}{2}\right)\sin x.
\]

4) Transform back:
\[
y_p = e^{x}u_p
     = e^{x}\left[\frac{x}{4}\cos x + \left(\frac{x^2}{4} + \frac{x}{2}\right)\sin x\right].
\]
Final solution:
\[
y = e^{x}(C_1\cos x + C_2\sin x) + y_p.
\]
