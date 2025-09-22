# MATB44 - Week 3 Tutorial Teaching Notes

## Week 3 Topics

### Linear Coefficient ODEs

#### Definition and Recognition
- General form: $(ax + by + c)dx + (dx + ey + f)dy = 0$
- When $\begin{vmatrix} a & b \\ d & e \end{vmatrix} \neq 0$
- Solution strategies based on coefficient relationships

#### Solution Methods
- **Case 1**: When $c = f = 0$ (homogeneous coefficients)
- **Case 2**: When $c \neq 0$ or $f \neq 0$ (non-homogeneous coefficients)
- Substitution techniques: $u = x - h$, $v = y - k$
- Finding critical points and transformations

#### Special Cases
- Exact equations
- Integrating factors
- Reduction to separable or homogeneous forms

## Definition and Theory

### What are Linear Coefficient ODEs?

A **linear coefficient ODE** has the form:
$$(ax + by + c)dx + (dx + ey + f)dy = 0$$

where $a, b, c, d, e, f$ are constants and the coefficient matrix is non-singular:
$$\begin{vmatrix} a & b \\ d & e \end{vmatrix} = ae - bd \neq 0$$

### Solution Strategy

The solution method depends on whether the constant terms are zero:

#### Case 1: Homogeneous Coefficients ($c = f = 0$)
When $c = f = 0$, the equation becomes:
$$(ax + by)dx + (dx + ey)dy = 0$$

This is **homogeneous** and can be solved using the substitution $v = \frac{y}{x}$.

#### Case 2: Non-Homogeneous Coefficients ($c \neq 0$ or $f \neq 0$)
When constant terms are present, we find the **critical point** $(h, k)$ by solving:
$$\begin{cases}
ah + bk + c = 0 \\
dh + ek + f = 0
\end{cases}$$

Then use the substitution: $u = x - h$, $v = y - k$

This transforms the equation to homogeneous form in $(u, v)$.

### Critical Point Method

**Step 1**: Check the coefficient matrix determinant:
$$\begin{vmatrix} a & b \\ d & e \end{vmatrix} = ae - bd$$

- If $ae - bd \neq 0$: Unique critical point exists, proceed to Step 2
- If $ae - bd = 0$: No unique critical point, use different methods (homogeneous or special substitutions)

**Step 2**: Find critical point $(h, k)$ from:
$$\begin{cases}
ah + bk + c = 0 \\
dh + ek + f = 0
\end{cases}$$

**Step 2**: Substitute $u = x - h$, $v = y - k$ (so $du = dx$, $dv = dy$)

**Step 3**: The equation becomes:
$$(au + bv)du + (du + ev)dv = 0$$

**Step 4**: Solve this homogeneous equation using $w = \frac{v}{u}$

**Step 5**: Back-substitute to get solution in terms of $x$ and $y$

## Key Examples

### Example 1: Non-Homogeneous Coefficients
**Solve**: $(2x + y - 1)dx + (x + 2y - 3)dy = 0$

**Solution**:
**Step 1**: Make the substitution directly:
Let $u = 2x - y + 1$ and $v = x + y$

From these equations:
- $u = 2x - y + 1$ ... (1)
- $v = x + 2y -3$ ... (2)

Solving for $x$ and $y$:
From the system:
- $u = 2x - y + 1$ ... (1)
- $v = x + 2y - 3$ ... (2)

From (1): $y = 2x - u + 1$
Substitute into (2): $v = x + 2(2x - u + 1) - 3 = x + 4x - 2u + 2 - 3 = 5x - 2u - 1$
So: $x = \frac{v + 2u + 1}{5}$

And: $y = 2x - u + 1 = 2 \cdot \frac{v + 2u + 1}{5} - u + 1 = \frac{2v + 4u + 2}{5} - u + 1 = \frac{2v + 4u + 2 - 5u + 5}{5} = \frac{2v - u + 7}{5}$

**Step 2**: Find the differentials:
$dx = \frac{2}{5}du + \frac{1}{5}dv$ and $dy = -\frac{1}{5}du + \frac{2}{5}dv$

**Step 3**: Substitute into the original equation:
$(2x + y - 1)dx + (x + 2y - 3)dy = 0$

Notice that:
- $2x + y - 1 = u$ (by our substitution)
- $x + 2y - 3 = v$ (by our substitution)

**Step 4**: The equation becomes:
$u \cdot dx + v \cdot dy = 0$

Substituting the differentials:
$u \cdot (\frac{2}{5}du + \frac{1}{5}dv) + v \cdot (-\frac{1}{5}du + \frac{2}{5}dv) = 0$

Expanding:
$\frac{2u}{5}du + \frac{u}{5}dv - \frac{v}{5}du + \frac{2v}{5}dv = 0$

Collecting terms:
$(\frac{2u}{5} - \frac{v}{5})du + (\frac{u}{5} + \frac{2v}{5})dv = 0$

Factoring out $\frac{1}{5}$:
$(2u - v)du + (u + 2v)dv = 0$

**Step 5**: This is now a homogeneous equation in $(u, v)$. We can solve using $w = \frac{v}{u}$:

Let $v = wu$, then $dv = w du + u dw$

$(2u - wu)du + (u + 2wu)(w du + u dw) = 0$

$u(2 - w)du + u(1 + 2w)(w du + u dw) = 0$

Dividing by $u$: $(2 - w)du + (1 + 2w)(w du + u dw) = 0$

$(2 - w + w + 2w^2)du + (1 + 2w)u dw = 0$

$(2 + 2w^2)du + (1 + 2w)u dw = 0$

Separating: $\frac{du}{u} = -\frac{(1 + 2w)dw}{2(1 + w^2)}$

**Final solution**: After integration and back-substitution, we get the relationship between $u = 2x - y + 1$ and $v = x + 2y - 3$.

### Example 2: Special Case - Determinant = 0
**Solve**: $(x + 2y - 3)dx + (2x + 4y + 1)dy = 0$

**Solution**:
**Step 1**: Check the coefficient matrix determinant:
$$\begin{vmatrix} 1 & 2 \\ 2 & 4 \end{vmatrix} = 1 \cdot 4 - 2 \cdot 2 = 4 - 4 = 0$$

Since the determinant is 0, we cannot find a unique critical point. We need a different approach.

**Step 2**: Make substitution:
Let $y = y$ and $u = x + 2y - 3$

From this: $x = u - 2y + 3$

**Step 3**: Find the differentials:
$du = dx + 2dy$, so $dx = du - 2dy$

**Step 4**: Substitute into the original equation:
$(x + 2y - 3)dx + (2x + 4y + 1)dy = 0$

Notice that:
- $x + 2y - 3 = u$
- $2x + 4y + 1 = 2(x + 2y) + 1 = 2(u + 3) + 1 = 2u + 7$

The equation becomes:
$u \cdot dx + (2u + 7)dy = 0$

Substituting $dx = du - 2dy$:
$u \cdot (du - 2dy) + (2u + 7)dy = 0$

$u \, du - 2u \, dy + (2u + 7)dy = 0$

$u \, du + (-2u + 2u + 7)dy = 0$

$u \, du + 7dy = 0$

**Step 5**: This is **separable**:
$u \, du = -7dy$

Integrating both sides:
$\int u \, du = -7 \int dy$

$\frac{u^2}{2} = -7y + C$

**Final solution**: $\frac{(x + 2y - 3)^2}{2} = -7y + C$, or $(x + 2y - 3)^2 + 14y = K$ 