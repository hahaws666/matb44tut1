# MATB44 - Week 13 Tutorial Teaching Notes

## Week 13 Topics

### Laplace Transform Method

- Definition and basic properties of Laplace transforms
- Solving ODEs using Laplace transforms
- Initial value problems and convolution
- Inverse Laplace transforms and partial fractions

### Frobenius Method

- Power series solutions for regular singular points
- Indicial equation and roots
- Finding series solutions near singular points
- Cases: distinct roots, repeated roots, roots differing by an integer

---

# 1. Laplace Transform Method

## 1.1 Definition

The Laplace transform of a function $f(t)$ (defined for $t \geq 0$) is:

$$
\mathcal{L}\{f(t)\} = F(s) = \int_0^{\infty} e^{-st} f(t)\,dt,
$$

where $s$ is a complex variable, and the integral converges for sufficiently large $\text{Re}(s)$.

### Basic Laplace Transforms

| $f(t)$                       | $F(s) = \mathcal{L}\{f(t)\}$ |
| ------------------------------ | ------------------------------ |
| $1$                          | $\frac{1}{s}$                |
| $t^n$ ($n \in \mathbb{N}$) | $\frac{n!}{s^{n+1}}$         |
| $e^{at}$                     | $\frac{1}{s-a}$              |
| $\sin(bt)$                   | $\frac{b}{s^2+b^2}$          |
| $\cos(bt)$                   | $\frac{s}{s^2+b^2}$          |
| $t^n e^{at}$                 | $\frac{n!}{(s-a)^{n+1}}$     |
| $e^{at}\sin(bt)$             | $\frac{b}{(s-a)^2+b^2}$      |
| $e^{at}\cos(bt)$             | $\frac{s-a}{(s-a)^2+b^2}$    |
| $\delta(t-a)$ (Dirac delta)  | $e^{-as}$                    |

---

## 1.2 Key Properties

### Linearity

$$
\mathcal{L}\{af(t) + bg(t)\} = aF(s) + bG(s)
$$

### First Derivative

$$
\mathcal{L}\{f'(t)\} = sF(s) - f(0)
$$

### Second Derivative

$$
\mathcal{L}\{f''(t)\} = s^2F(s) - sf(0) - f'(0)
$$

### $n$-th Derivative

$$
\mathcal{L}\{f^{(n)}(t)\} = s^nF(s) - s^{n-1}f(0) - s^{n-2}f'(0) - \cdots - f^{(n-1)}(0)
$$

### Shifting Property (First Shifting Theorem)

$$
\mathcal{L}\{e^{at}f(t)\} = F(s-a)
$$

### Second Shifting Theorem

$$
\mathcal{L}\{f(t-a)u(t-a)\} = e^{-as}F(s),
$$

where $u(t-a)$ is the unit step function (Heaviside function).

### Convolution

$$
\mathcal{L}\{f * g\} = \mathcal{L}\{f\} \cdot \mathcal{L}\{g\},
$$

where $(f * g)(t) = \int_0^t f(\tau)g(t-\tau)\,d\tau$.

---

## 1.3 Solving ODEs with Laplace Transform

**General Procedure:**

1. Take the Laplace transform of both sides of the ODE.
2. Use initial conditions to simplify.
3. Solve algebraically for $Y(s) = \mathcal{L}\{y(t)\}$.
4. Find the inverse Laplace transform $y(t) = \mathcal{L}^{-1}\{Y(s)\}$.

---

## 1.4 Inverse Laplace Transform

### Partial Fractions

To find $\mathcal{L}^{-1}\{F(s)\}$, often we need to decompose $F(s)$ into partial fractions.

**Common cases:**

1. **Distinct linear factors:**

   $$
   \frac{A}{s-a} + \frac{B}{s-b} \Rightarrow A e^{at} + B e^{bt}
   $$
2. **Repeated linear factors:**

   $$
   \frac{A}{(s-a)^n} \Rightarrow \frac{A}{(n-1)!} t^{n-1} e^{at}
   $$
3. **Quadratic factors:**

   $$
   \frac{As+B}{s^2+\omega^2} \Rightarrow A\cos(\omega t) + \frac{B}{\omega}\sin(\omega t)
   $$

---

## 1.5 Examples

### Example 1: First-Order ODE

Solve:

$$
y' + 2y = e^{-t}, \quad y(0) = 1
$$

**Solution:**

**Step 1.** Take Laplace transform:

$$
\mathcal{L}\{y'\} + 2\mathcal{L}\{y\} = \mathcal{L}\{e^{-t}\}
$$

**Step 2.** Apply properties:

$$
sY(s) - y(0) + 2Y(s) = \frac{1}{s+1}
$$

Substitute $y(0) = 1$:

$$
sY(s) - 1 + 2Y(s) = \frac{1}{s+1}
$$

**Step 3.** Solve for $Y(s)$:

$$
Y(s)(s+2) = 1 + \frac{1}{s+1} = \frac{s+2}{s+1}
$$

$$
Y(s) = \frac{1}{s+1}
$$

**Step 4.** Inverse transform:

$$
y(t) = \mathcal{L}^{-1}\left\{\frac{1}{s+1}\right\} = e^{-t}
$$

---

### Example 2: Second-Order ODE

Solve:

$$
y'' + 4y = \sin(2t), \quad y(0) = 0, \quad y'(0) = 1
$$

**Solution:**

**Step 1.** Take Laplace transform:

$$
\mathcal{L}\{y''\} + 4\mathcal{L}\{y\} = \mathcal{L}\{\sin(2t)\}
$$

**Step 2.** Apply properties:

$$
s^2Y(s) - sy(0) - y'(0) + 4Y(s) = \frac{2}{s^2+4}
$$

Substitute initial conditions:

$$
s^2Y(s) - 1 + 4Y(s) = \frac{2}{s^2+4}
$$

**Step 3.** Solve for $Y(s)$:

$$
Y(s)(s^2+4) = 1 + \frac{2}{s^2+4} = \frac{s^2+6}{s^2+4}
$$

$$
Y(s) = \frac{s^2+6}{(s^2+4)^2} = \frac{1}{s^2+4} + \frac{2}{(s^2+4)^2}
$$

**Step 4.** Inverse transform:

$$
y(t) = \frac{1}{2}\sin(2t) + \frac{1}{4}\left[\sin(2t) - 2t\cos(2t)\right] = \frac{3}{4}\sin(2t) - \frac{t}{2}\cos(2t)
$$

---

### Example 3: ODE with Step Function

Solve:

$$
y'' + y = u(t-1), \quad y(0) = 0, \quad y'(0) = 0
$$

where $u(t-1)$ is the unit step function.

**Solution:**

**Step 1.** Laplace transform:

$$
s^2Y(s) + Y(s) = \frac{e^{-s}}{s}
$$

**Step 2.** Solve:

$$
Y(s) = \frac{e^{-s}}{s(s^2+1)} = e^{-s}\left(\frac{1}{s} - \frac{s}{s^2+1}\right)
$$

**Step 3.** Inverse transform (using second shifting theorem):

$$
y(t) = u(t-1)\left[1 - \cos(t-1)\right]
$$

---

### Example 4: Using Convolution

Solve:

$$
y'' + y = f(t), \quad y(0) = 0, \quad y'(0) = 0
$$

**Solution:**

Taking Laplace transform:

$$
s^2Y(s) + Y(s) = F(s) \Rightarrow Y(s) = \frac{F(s)}{s^2+1}
$$

Using convolution:

$$
y(t) = \int_0^t \sin(t-\tau) f(\tau)\,d\tau
$$

---

# 2. Frobenius Method

## 2.1 Regular Singular Points

Consider a second-order linear ODE:

$$
P(x)y'' + Q(x)y' + R(x)y = 0
$$

A point $x_0$ is a **regular singular point** if:

- $(x-x_0)\frac{Q(x)}{P(x)}$ is analytic at $x_0$
- $(x-x_0)^2\frac{R(x)}{P(x)}$ is analytic at $x_0$

In standard form (dividing by $P(x)$):

$$
y'' + p(x)y' + q(x)y = 0,
$$

$x_0$ is a regular singular point if:

- $(x-x_0)p(x)$ is analytic at $x_0$
- $(x-x_0)^2q(x)$ is analytic at $x_0$

---

## 2.2 Frobenius Method Overview

**Goal:** Find power series solutions near a regular singular point $x_0$ (usually $x_0 = 0$).

**Assumption:** Solution of the form:

$$
y(x) = x^r \sum_{n=0}^{\infty} a_n x^n = \sum_{n=0}^{\infty} a_n x^{n+r}, \quad a_0 \neq 0
$$

**Steps:**

1. Substitute the series into the ODE.
2. Find the **indicial equation** (determines $r$).
3. For each root $r$, find recurrence relation for $a_n$.
4. Write the general solution.

---

## 2.3 Indicial Equation

After substitution, the lowest power of $x$ gives the **indicial equation**:

$$
r(r-1) + p_0 r + q_0 = 0,
$$

where:

- $p_0 = \lim_{x \to 0} xp(x)$
- $q_0 = \lim_{x \to 0} x^2q(x)$

This is a quadratic in $r$ with roots $r_1$ and $r_2$.

---

## 2.4 Three Cases

### Case 1: Distinct Roots Not Differing by an Integer

If $r_1 \neq r_2$ and $r_1 - r_2 \notin \mathbb{Z}$, then two linearly independent solutions:

$$
y_1(x) = x^{r_1}\sum_{n=0}^{\infty} a_n x^n, \quad y_2(x) = x^{r_2}\sum_{n=0}^{\infty} b_n x^n
$$

General solution: $y(x) = C_1 y_1(x) + C_2 y_2(x)$.

---

### Case 2: Repeated Root ($r_1 = r_2$)

If $r_1 = r_2 = r$, then:

$$
y_1(x) = x^r \sum_{n=0}^{\infty} a_n x^n
$$

Second solution:

$$
y_2(x) = y_1(x)\ln x + x^r \sum_{n=1}^{\infty} b_n x^n
$$

---

### Case 3: Roots Differing by an Integer

If $r_1 - r_2 = N \in \mathbb{Z}^+$ (assume $r_1 > r_2$), then:

**First solution:**

$$
y_1(x) = x^{r_1}\sum_{n=0}^{\infty} a_n x^n
$$

**Second solution:**

- If the recurrence relation gives a valid solution for $r_2$, then:
  $$
  y_2(x) = x^{r_2}\sum_{n=0}^{\infty} b_n x^n
  $$
- Otherwise (if $a_N$ becomes undefined), the second solution contains a logarithm:
  $$
  y_2(x) = C y_1(x)\ln x + x^{r_2}\sum_{n=0}^{\infty} b_n x^n
  $$

---

## 2.5 Examples



### Example 4: Roots Differing by an Integer

Solve the ODE near the regular singular point $x = 0$:

$$
x^{2}y'' + x y' + \left(x^{2}-\frac{1}{4}\right)y = 0
$$

**Solution:**

**Step 1.** Frobenius form and indicial equation

Assume:

$$
y(x) = \sum_{n=0}^{\infty} a_n x^{n+r}, \quad a_0 \neq 0
$$

Then:

$$
y' = \sum_{n=0}^{\infty} (n+r)a_n x^{n+r-1}, \quad
y'' = \sum_{n=0}^{\infty} (n+r)(n+r-1)a_n x^{n+r-2}
$$

Substitute into the equation:

$$
x^2 y'' + x y' + (x^2 - \tfrac{1}{4}) y = 0
$$

We get:

$$
\sum_{n=0}^{\infty} \left[(n+r)^2-\frac{1}{4}\right] a_n x^{n+r}
+\sum_{n=2}^{\infty} a_{n-2} x^{n+r} = 0
$$

Setting coefficients to zero, we obtain the recurrence relation:

$$
\left[(n+r)^2-\frac{1}{4}\right] a_n + a_{n-2} = 0, \quad n \geq 0
$$

where we define $a_{-1} = a_{-2} = 0$.

For $n = 0$, we get the **indicial equation**:

$$
r^2-\frac{1}{4} = 0 \quad\Rightarrow\quad r_1 = \frac{1}{2}, \quad r_2 = -\frac{1}{2}
$$

The roots differ by 1 (an integer).

---

**Step 2.** Solution for $r = \frac{1}{2}$

With $r = \frac{1}{2}$, the recurrence becomes:

$$
\left[(n+\tfrac{1}{2})^2-\frac{1}{4}\right] a_n + a_{n-2} = 0
\quad\Rightarrow\quad
n(n+1)a_n + a_{n-2} = 0
$$

That is:

$$
a_n = -\frac{a_{n-2}}{n(n+1)}
$$

Taking $a_0 = 1$:

- $n=1$: $1 \cdot 2 \cdot a_1 = 0 \Rightarrow a_1 = 0$ (all odd terms are 0)
- $n=2$: $a_2 = -\frac{a_0}{2 \cdot 3} = -\frac{1}{6}$
- $n=4$: $a_4 = -\frac{a_2}{4 \cdot 5} = \frac{1}{120}$
- $n=6$: $a_6 = -\frac{a_4}{6 \cdot 7} = -\frac{1}{5040}$
- ...

Therefore:

$$
\begin{aligned}
y_1(x)
&= x^{1/2}\left(a_0 + a_2 x^2 + a_4 x^4 + \cdots\right) \\
&= x^{1/2}\left(1 - \frac{x^2}{3!} + \frac{x^4}{5!} - \frac{x^6}{7!} + \cdots\right)
\end{aligned}
$$

The series in parentheses is $\frac{\sin x}{x}$, so:

$$
y_1(x) = x^{1/2} \cdot \frac{\sin x}{x} = x^{-1/2}\sin x
$$

---

**Step 3.** Solution for $r = -\frac{1}{2}$

With $r = -\frac{1}{2}$, the recurrence becomes:

$$
\left[(n-\tfrac{1}{2})^2-\frac{1}{4}\right] a_n + a_{n-2} = 0
\quad\Rightarrow\quad
n(n-1)a_n + a_{n-2} = 0
$$

That is:

$$
a_n = -\frac{a_{n-2}}{n(n-1)}
$$

For $n=0,1$, the coefficient is 0, so $a_0$ and $a_1$ are free constants.  
To get a solution linearly independent from $y_1$, we take $a_0=1, a_1=0$.

- $n=2$: $a_2 = -\frac{a_0}{2 \cdot 1} = -\frac{1}{2}$
- $n=4$: $a_4 = -\frac{a_2}{4 \cdot 3} = \frac{1}{24}$
- $n=6$: $a_6 = -\frac{a_4}{6 \cdot 5} = -\frac{1}{720}$
- ...

Therefore:

$$
\begin{aligned}
y_2(x)
&= x^{-1/2}\left(a_0 + a_2 x^2 + a_4 x^4 + \cdots\right) \\
&= x^{-1/2}\left(1 - \frac{x^2}{2!} + \frac{x^4}{4!} - \frac{x^6}{6!} + \cdots\right)
\end{aligned}
$$

The series in parentheses is $\cos x$, so:

$$
y_2(x) = x^{-1/2}\cos x
$$

**Note:** Although the indicial roots differ by an integer, the second solution is a regular Frobenius series solution and does not contain $\ln x$.

---

**Step 4.** General solution

The general solution near $x=0$ is:

$$
y(x) = C_1 x^{-1/2}\sin x + C_2 x^{-1/2}\cos x
$$

where $C_1, C_2$ are arbitrary constants.

---
