# MATB44 - Week 12 Tutorial Teaching Notes

## Week 12 Topics

### Linear Systems, Straight-Line Solutions, and Operator Elimination

- Converting a linear system into dy/dx form
- Determining straight-line trajectories $y = cx$
- Solving the quadratic equation for the slope c
- Using the discriminant to classify linear solutions
- Connection with eigenvalues and eigenvectors
- Operator elimination method: reducing a 2×2 first-order system to a single higher-order equation

---

# 1. Linear Systems and Straight-Line Solutions

## 1.1 Starting Linear System

Consider a linear system:
$$
\begin{cases}
\dot x = a_1 x + b_1 y, \\
\dot y = a_2 x + b_2 y.
\end{cases}
$$

As long as $\dot x \neq 0$, we can write:
$$
\frac{dy}{dx} = 
\frac{a_2 x + b_2 y}{a_1 x + b_1 y}.
$$

We want to determine whether there exists a straight-line solution of the form:
$$
y = c x.
$$

---

## 1.2 Substituting $y = cx$

If a trajectory is a straight line through the origin, then:
$$
\frac{dy}{dx} = c.
$$

Substitute $y = cx$ into the slope formula:
$$
c = \frac{a_2 + b_2 c}{a_1 + b_1 c}.
$$

Multiply both sides:
$$
c(a_1 + b_1 c) = a_2 + b_2 c.
$$

This simplifies to a quadratic equation for c:
$$
b_1 c^2 + (a_1 - b_2)c - a_2 = 0.
$$

**Roots c are slopes of straight-line solutions.**

---

## 1.3 Discriminant and Classification

Let the discriminant be:
$$
\Delta = (a_1 - b_2)^2 + 4 a_2 b_1.
$$

Equivalent expression using system determinant:
$$
D = a_1 b_2 - a_2 b_1,
$$
$$
\Delta = (a_2 + b_1)^2 + 4D.
$$

### Interpretation:

| Case | Δ | Straight-line solutions? | Interpretation |
|------|----|---------------------------|----------------|
| 1 | Δ > 0 | Two distinct straight lines | Two real eigenvectors |
| 2 | Δ = 0 | One straight line (repeated root) | Defective matrix, one eigenvector |
| 3 | Δ < 0 | No straight-line solution | Complex eigenvalues (spiral/center) |

---

## 1.4 Geometric Meaning

- Straight lines $y = cx$ correspond to **eigenvector directions**, i.e., invariant lines.
- If Δ > 0: two real eigenvectors → node or saddle.
- If Δ = 0: only one direction → repeated eigenvalue, defective.
- If Δ < 0: no invariant straight lines → spirals/centers.

---

# 2. Operator Elimination Method

A central technique:  
**Convert a 2×2 first-order system into a single higher-order ODE by eliminating one variable.**

Given:
$$
\begin{cases}
P_1(D)x + Q_1(D)y = f_1(t) \quad (e_1)\\
P_2(D)x + Q_2(D)y = f_2(t) \quad (e_2)
\end{cases}
$$

Goal: eliminate y.

### Key idea
Find operators $A(D)$, $B(D)$ such that:
$$
A(D)Q_1(D) + B(D)Q_2(D) = 0,
$$
so that:
$$
A(D)e_1 + B(D)e_2
$$
eliminates y, leaving an equation in x only.

This parallells row operations in linear algebra — but using differential operators.

---

# 3. Example Set (from tutorial)

## Example 1 — Operator Elimination (from your notes)

$$
\begin{cases}
(D+4)x - (D-1)y = 3t \quad (e_1)\\
(D^2-D)x + y = e^t \quad (e_2)
\end{cases}
$$

Use:
$$
e_1 \to e_1 + (D-1)e_2.
$$

Then y is eliminated and we obtain:
$$
(D^3 - 2D^2 + 2D + 4)x = 3t.
$$

---

## Example 2 — Operator Elimination

$$
\begin{cases}
(D^2 + 2D)x + (D-5)y = 0 \quad (e_1)\\
(D+1)x + y = \sin t \quad (e_2)
\end{cases}
$$

Use:
$$
e_1 \to e_1 - (D-5)e_2.
$$

Eliminate y:
$$
(6D + 5)x = -\cos t + 5\sin t.
$$

---

## Example 3 — Operator Elimination

$$
\begin{cases}
(D-2)x + (2D+1)y = t^3 \\
(D+3)x - (D+1)y = e^{2t}
\end{cases}
$$

Use:
$$
e_1 \to (D+1)e_1 + (2D+1)e_2.
$$

Result:
$$
(3D^2 + 6D + 1)x = t^3 + 3t^2 + 5e^{2t}.
$$

---

# 4. Example — Straight-Line Solutions

Consider:
$$
\begin{cases}
\dot x = 3x + 2y,\\
\dot y = -4x + y.
\end{cases}
$$

Solve:
$$
c = \frac{-4 + c}{3 + 2c}.
$$

We get:
$$
2c^2 + 3c + 4 = 0,\quad \Delta < 0.
$$

**No straight-line solutions (complex eigenvalues).**

---

# 5. Example — Straight-Line Solutions (Two Lines)

$$
\begin{cases}
\dot x = 2x + y,\\
\dot y = x + 3y.
\end{cases}
$$

Equation:
$$
c = \frac{1 + 3c}{2 + c}
\Rightarrow c^2 - c - 1 = 0.
$$

Two real roots:
$$
c = \frac{1\pm \sqrt{5}}{2}.
$$

→ **two invariant lines**.

---

# 6. Example — Direction Ratio y(t)/x(t)

Suppose:
$$
x(t) = e^t + 2t e^t, \quad 
y(t) = 3e^t + 5t e^t.
$$

Then:
$$
\frac{y(t)}{x(t)}
= \frac{3 + 5t}{1 + 2t}
\to \frac{5}{2}.
$$

Interpretation:  
As $t\to \infty$, solution approaches direction:
$$
y = \frac52 x.
$$

This is exactly the eigenvector direction corresponding to the dominant eigenvalue.

---

# 7. Practice Problems

1. Determine whether the system  
   $\dot x = 4x + y,\;\dot y = -2x + y$  
   has any straight-line solutions $y = cx$.

2. For the system  
   $\dot x = x + 4y,\;\dot y = 2x + y$,  
   compute the two invariant lines.

3. Use operator elimination to eliminate y:  
$$
\begin{cases}
(D+2)x + Dy = t,\\
(D-3)x - (D+1)y = e^t.
\end{cases}
$$

4. For  
   $$
   x(t)=3e^{2t}+ t e^{2t},\quad 
   y(t)=5e^{2t}+ 4t e^{2t},
   $$  
   compute $\lim_{t\to\infty} y(t)/x(t)$.

5. Show that  
   $$
   c = \frac{a_2 + b_2 c}{a_1 + b_1 c}
   $$  
   is equivalent to the eigenvector equation for  
   $\begin{pmatrix}a_1&b_1\\a_2&b_2\end{pmatrix}$.

---
