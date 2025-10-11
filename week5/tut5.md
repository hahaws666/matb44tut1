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


## Quick Reminder

- **Midterm exam:** Next week.
- **Assignment 1 result:** Will be released before Oct. 18 (the day before the midterm).
- **Next tutorial:** Will be a review session for the midterm.