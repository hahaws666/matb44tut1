# MATB44 - Week 5 Tutorial Teaching Notes

## Week 5 Topics

### Homogeneous Linear ODEs with Constant Coefficients

## Definition and Theory

### Linear Homogeneous ODE with Constant Coefficients

An nth-order linear homogeneous ODE with constant coefficients has the form:
$$a_n \frac{d^n y}{dx^n} + a_{n-1} \frac{d^{n-1} y}{dx^{n-1}} + \cdots + a_1 \frac{dy}{dx} + a_0 y = 0, \quad a_n \neq 0,$$
where $a_0,\dots,a_n$ are constants.

### Principle of Superposition

- If $y_1,\dots,y_k$ are solutions, then any linear combination $c_1 y_1 + \cdots + c_k y_k$ is also a solution.
- A fundamental solution set consists of $n$ linearly independent solutions; the general solution is their linear combination.

### Characteristic Equation

- Seek solutions of the form $y = e^{rx}$.
- Substitution gives the characteristic polynomial:
$$a_n r^n + a_{n-1} r^{n-1} + \cdots + a_1 r + a_0 = 0.$$
- Roots (including multiplicities) determine the shape of the general solution.

### Root Cases and General Solution Forms

- Distinct real roots $r_1,\dots,r_n$:
  $$y(x) = C_1 e^{r_1 x} + \cdots + C_n e^{r_n x}.$$
- Repeated real root $r$ of multiplicity $m$:
  $$y(x) = e^{rx}\big(C_0 + C_1 x + \cdots + C_{m-1} x^{m-1}\big).$$
- Complex conjugate pair $r = \alpha \pm i\beta$ ($\beta \neq 0$):
  $$y(x) = e^{\alpha x}\big(C_1 \cos(\beta x) + C_2 \sin(\beta x)\big).$$
- Complex pair with multiplicity $m$:
  $$y(x) = e^{\alpha x}\sum_{k=0}^{m-1}\big( A_k x^k \cos(\beta x) + B_k x^k \sin(\beta x) \big).$$



## Key Examples

### Example 1: Distinct Real Roots
Solve $y'' - 3y' + 2y = 0$ with $y(0) = 2$, $y'(0) = 0$.

Characteristic: $r^2 - 3r + 2 = 0 \;\Rightarrow\; r = 1, 2$.
General solution: $y = C_1 e^{x} + C_2 e^{2x}$.

Apply IVP:
- $y(0) = C_1 + C_2 = 2$
- $y'(x) = C_1 e^{x} + 2 C_2 e^{2x} \Rightarrow y'(0) = C_1 + 2C_2 = 0$

Solve: from $C_1 + 2C_2 = 0$ we get $C_1 = -2C_2$; then $-2C_2 + C_2 = 2 \Rightarrow C_2 = -2$, $C_1 = 4$.

Final: $y(x) = 4 e^{x} - 2 e^{2x}$.

### Example 2: Repeated Real Root
Solve $y'' - 4y' + 4y = 0$.

Characteristic: $(r - 2)^2 = 0$.
General solution: $y(x) = (C_1 + C_2 x) e^{2x}$.

### Example 3: Complex Conjugate Roots
Solve $y'' + 4y' + 13y = 0$.

Characteristic: $r = -2 \pm 3i$.
General solution: $y(x) = e^{-2x}\big(C_1 \cos 3x + C_2 \sin 3x\big)$.

### Example 4: Higher Order, Mixed Roots
Solve $y''' - y' = 0$.

Characteristic: $r(r^2 - 1) = 0 \Rightarrow r \in \{0, 1, -1\}$.
General solution: $y(x) = C_1 + C_2 e^{x} + C_3 e^{-x}$.

### Example 5: Repeated Complex Roots
Solve $\dfrac{d^4 y}{dx^4} + 8\dfrac{d^3 y}{dx^3} + 42\dfrac{d^2 y}{dx^2} + 104\dfrac{dy}{dx} + 169\,y = 0$.

Characteristic: $(r^2 + 4r + 13)^2 = 0$ (i.e., $r = -2 \pm 3i$ with multiplicity 2).
General solution: $y(x) = e^{-2x}\Big[(C_1 + C_3 x)\cos(3x) + (C_2 + C_4 x)\sin(3x)\Big]$.


## Bernoulli Equation (Supplement)

### Definition

- A Bernoulli equation is a first-order nonlinear ODE of the form
  $$\frac{dy}{dx} + P(x)\,y = Q(x)\,y^n,\quad n\neq 0,1.$$

### Method (Linearization by substitution)

1. Let $v = y^{1-n}$.
2. Then $\dfrac{dv}{dx} = (1-n)\,y^{-n}\,\dfrac{dy}{dx}$, and the equation becomes a linear ODE in $v$:
   $$\frac{dv}{dx} + (1-n)P(x)\,v = (1-n)Q(x).$$
3. Solve the linear equation for $v(x)$ using an integrating factor; recover $y$ from $y = v^{\tfrac{1}{1-n}}$.

### Example: Solve with $n=3$

Solve
$$\frac{dy}{dx} + \frac{2}{x}y = x^2 y^3,\quad x>0.$$

Here $n=3$, $P(x)=\tfrac{2}{x}$, $Q(x)=x^2$. Let $v = y^{1-3} = y^{-2}$. Then
$$\frac{dv}{dx} + (1-3)P(x)\,v = (1-3)Q(x) \;\Rightarrow\; \frac{dv}{dx} - \frac{4}{x}v = -2x^2.$$
Integrating factor: $\mu(x) = e^{\int -\tfrac{4}{x}dx} = x^{-4}$.
Then
$$\big(x^{-4}v\big)' = -2x^2\cdot x^{-4} = -2x^{-2} \;\Rightarrow\; x^{-4}v = \int -2x^{-2} dx = 2x^{-1} + C.$$
Hence $v = y^{-2} = 2x^{3} + Cx^{4}$, and
$$y(x) = \big(2x^{3} + Cx^{4}\big)^{-1/2},\quad x>0.$$

### Practice

Solve for $x>0$:
$$\frac{dy}{dx} - \frac{1}{x}y = x\,y^2.$$

## Quick Reminder

- **Midterm exam:** Next week.
- **Assignment 1 result:** Will be released before Oct. 18 (the day before the midterm).
- **Next tutorial:** Will be a review session for the midterm.