# MATB44 - Week 6 Review Notes

## Scope

- Review of Weeks 1–5: core concepts, methods, quick recipes, pitfalls, and practice.

## Quick Map of Topics

- First-order ODEs:
  - Separable ODEs
  - Homogeneous first-order ODEs
  - Linear coefficient ODEs in differential form
  - Exact equations and integrating factors
  - Bernoulli equation (supplement)
- Linear homogeneous ODEs with constant coefficients (higher order)

## Core Definitions and Forms

### Separable ODEs

- Form: $\dfrac{dy}{dx} = f(x)\,g(y)$.
- Method: separate variables and integrate
  $$\int \dfrac{dy}{g(y)} = \int f(x)\,dx.$$

### Homogeneous First-Order ODEs

- Form: $\dfrac{dy}{dx} = F\!\left(\dfrac{y}{x}\right)$.
- Substitution: $v = \dfrac{y}{x}$, so $y = vx$, $\dfrac{dy}{dx} = v + x\dfrac{dv}{dx}$.
- Reduce to separable in $(v,x)$ and integrate.

### Linear Coefficient ODEs (Differential Form)

- Form: $(ax + by + c)\,dx + (dx + ey + f)\,dy = 0$, with $\begin{vmatrix} a & b \\ d & e \end{vmatrix} = det$.
- Strategy:
  - If $c = f = 0$: homogeneous in $(x,y)$, use $v = y/x$.
  - Else if $\det \neq 0$: using substitution setting $ah + bk + c = u$, $dh + ek + f = v$, to homogenize.
  - Else: substitution with $y = y$, $ah + bk + c = u$.

### Exact Differential Equations

- Form: $M(x,y)\,dx + N(x,y)\,dy = 0$.
- Exactness: $\dfrac{\partial M}{\partial y} = \dfrac{\partial N}{\partial x}$.
- Solve via potential function $\phi$: find $\phi_x=M$, $\phi_y=N$, then $\phi(x,y)=C$.
- Integrating factors (when not exact): common patterns
  - $\mu(x)$ if $\dfrac{M_y - N_x}{N} = F(x)$
  - $\mu(y)$ if $\dfrac{M_y - N_x}{M} = F(y)$
  - $\mu(x/y)$ if $y^2\dfrac{M_y - N_x}{xM + yN} = F(x/y)$
  - $\mu(xy)$ if $\dfrac{M_y - N_x}{yN - xM} = F(xy)$
  - Monomial factor $\mu = x^a y^b$ for monomial structures

### Bernoulli Equation (Supplement)

- Form: $\dfrac{dy}{dx} + P(x)\,y = Q(x)\,y^n$, $n\neq 0,1$.
- Substitution: $v = y^{1-n}$ $\Rightarrow$ linear ODE in $v$:
  $$\frac{dv}{dx} + (1-n)P(x)\,v = (1-n)Q(x).$$

### Linear Homogeneous ODEs with Constant Coefficients

- Form: $a_n\,\dfrac{d^n y}{dx^n} + a_{n-1}\,\dfrac{d^{n-1} y}{dx^{n-1}} + \cdots + a_1\,\dfrac{dy}{dx} + a_0\,y = 0$.
- Characteristic polynomial: $a_n r^n + a_{n-1} r^{n-1} + \cdots + a_1 r + a_0 = 0$.
- Solution shapes:
  - Distinct real roots $r_j$: $\sum C_j e^{r_j x}$
  - Repeated real root $r$ of multiplicity $m$: $e^{rx}\sum_{k=0}^{m-1} C_k x^k$
  - Complex $r=\alpha\pm i\beta$: $e^{\alpha x}(C_1\cos \beta x + C_2\sin \beta x)$
  - Repeated complex roots: multiply by powers of $x$

## Quick Recipes (Checklists)

- Separable: move all $y$ terms to LHS, $x$ terms to RHS, integrate both sides, apply ICs.
- Homogeneous first-order: set $v=y/x$, compute $dy/dx=v + x\,dv/dx$, separate in $(v,x)$.
- Linear coefficient: translate to critical point if needed, then solve as homogeneous in $(u,v)$.
- Exact: check exactness; if not exact, try a simple integrating factor; find potential $\phi$.
- Bernoulli: $v=y^{1-n}$ to linearize, solve for $v$, convert back to $y$.
- Constant coefficients: write characteristic equation, find roots with multiplicities, assemble general solution, fit constants via ICs.


## Mini Examples (No full solutions)

1. Separable: $\dfrac{dy}{dx} = \dfrac{2x}{1+y^2}$.
2. Homogeneous first-order: $(x + 4y)\,dx - (x + y)\,dy = 0$.
3. Linear coefficient: $(2x + y - 1)\,dx + (x + 2y - 3)\,dy = 0$.
4. Exact (check): $(2xy + 3x^2)\,dx + (x^2 + 2y)\,dy = 0$.
5. Integrating factor $\mu(x)$: $((x^2+1)y + x)\,dx + x(x^2+1)\,dy = 0$.
6. Bernoulli: $\dfrac{dy}{dx} + \dfrac{2}{x}y = x^2 y^3$ ($x>0$).
7. Constant coeff.: $y'' - 3y' + 2y = 0$.
8. Constant coeff. (complex): $y'' + 4y' + 13y = 0$.

## Practice for Review

1. Separable: $y' = (1+x)\sqrt{1-y^2}$, $y(0)=0$.
2. Homogeneous first-order: $\dfrac{dy}{dx} = \dfrac{y - x}{y + x}$.
3. Linear coefficient: $(x + 2y - 3)\,dx + (2x + 4y + 1)\,dy = 0$.
4. Exact vs integrating factor: $\dfrac{x^2}{y}\,dx + x\,dy = 0$.
5. Bernoulli: $y' - \dfrac{1}{x}y = x\,y^2$ ($x>0$).
6. Constant coeff.: $y'' + y' - 6y = 0$.
7. Constant coeff. (repeated): $y'' + 6y' + 9y = 0$.
8. Constant coeff. (complex): $y'' + 2y' + 10y = 0$.



