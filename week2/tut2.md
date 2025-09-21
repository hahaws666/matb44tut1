# MATB44 - Week 2 Tutorial Teaching Notes

## Week 2 Topics

### Separable Ordinary Differential Equations

- Definition and identification
- Solution method
- Initial value problems
- Key examples

## Definition and Method

### What is a Separable ODE?

A **separable ODE** has the form:
$$\frac{dy}{dx} = f(x)g(y)$$

### Homogeneous First Order ODEs

A **homogeneous first order ODE** has the form:
$$\frac{dy}{dx} = F\left(\frac{y}{x}\right)$$

where $F$ is a function of the ratio $\frac{y}{x}$ only.

**Solution Method for Homogeneous ODEs**:
1. **Substitution**: Let $v = \frac{y}{x}$, so $y = vx$
2. **Differentiate**: $\frac{dy}{dx} = v + x\frac{dv}{dx}$
3. **Substitute**: $v + x\frac{dv}{dx} = F(v)$
4. **Separate**: $\frac{dv}{F(v) - v} = \frac{dx}{x}$
5. **Integrate and solve**

**Solution Method for Separable ODEs**:
1. **Separate**: $\frac{dy}{g(y)} = f(x)dx$
2. **Integrate**: $\int \frac{dy}{g(y)} = \int f(x)dx$
3. **Solve for $y$**

## Summary of ODE Types (i made huge mistake in the last tutorial because that there is difference between the first oder ode and linear ode)

| Type | General Form | Standard Form|
|------|-------------|---------------|
| **Autonomous** | $y' = F(x,y)$ | $F(x,y) = F(y)$  |
| **Separable** | $F(x,y) = P(x) \cdot Q(y)$ | $P(x,y) = P(x)$; $Q(x,y) = Q(y)$ |
| **Homogeneous** | $F = F(x,y)$: homogeneous of degree 0 | $P(x,y), Q(x,y)$: homogeneous of degree n |
| **Linear Coefficient** | | $P(x,y) = ax + by + c$; $Q(x,y) = a'x + b'y + c'$ where $\begin{vmatrix} a & b \\ a' & b' \end{vmatrix} \neq 0$ |

## Key Examples

### Example 1: Separable ODE with Rational Functions
**Solve**: 
$$\begin{cases}
y' = \frac{2x^2 + 3x + 1}{y^2 + 2y + 2}, \\
y(0) = 0
\end{cases}$$

**Solution**:
This is separable: $(y^2 + 2y + 2)dy = (2x^2 + 3x + 1)dx$

Integrating both sides:
$$\int (y^2 + 2y + 2)dy = \int (2x^2 + 3x + 1)dx$$
$$\frac{y^3}{3} + y^2 + 2y = \frac{2x^3}{3} + \frac{3x^2}{2} + x + C$$

Using initial condition $y(0) = 0$: $C = 0$

**Final solution**: $\frac{y^3}{3} + y^2 + 2y = \frac{2x^3}{3} + \frac{3x^2}{2} + x$

### Example 2: Separable ODE with Trigonometric Functions
**Solve**: 
$$\begin{cases}
y' = \frac{xy^3}{\sqrt{1 + x^2}}, \\
y(0) = -2
\end{cases}$$

**Solution**:
This is separable: $\frac{dy}{y^3} = \frac{x dx}{\sqrt{1 + x^2}}$

Integrating both sides:
$$\int y^{-3} dy = \int \frac{x dx}{\sqrt{1 + x^2}}$$
$$-\frac{1}{2y^2} = \sqrt{1 + x^2} + C$$

Using initial condition $y(0) = -2$: $-\frac{1}{8} = 1 + C \Rightarrow C = -\frac{9}{8}$

**Final solution**: $-\frac{1}{2y^2} = \sqrt{1 + x^2} - \frac{9}{8}$

Solving for $y$: $y^2 = \frac{-4}{\sqrt{1 + x^2} - \frac{9}{8}}$

**Domain**: Solution exists where $\sqrt{1 + x^2} < \frac{9}{8}$, which gives $|x| < \frac{5}{8}$

### Example 3: Homogeneous ODE Method
**Solve**: $(x + 4y)dx - (x + y)dy = 0$

**Method for Homogeneous ODEs**:
1. **Check if homogeneous**: Verify that $P(x,y)$ and $Q(x,y)$ are homogeneous of the same degree
2. **Use substitution**: Let $v = \frac{y}{x}$, so $y = vx$
3. **Find derivative**: $dy = x dv + v dx$
4. **Substitute and simplify**: Replace $y$ and $dy$ in the original equation
5. **Separate variables**: Get equation in terms of $v$ and $x$ only
6. **Integrate**: Solve the separated equation
7. **Back-substitute**: Replace $v$ with $\frac{y}{x}$ to get final solution

**Solution**:
Here $P(x,y) = x + 4y$ and $Q(x,y) = x + y$ are both homogeneous of degree 1.

Let $v = \frac{y}{x}$, so $y = vx$ and $dy = x dv + v dx$

Substituting: $(x + 4vx)dx - (x + vx)(x dv + v dx) = 0$

Simplifying: $(x + 4vx)dx - (x + vx)x dv - (x + vx)v dx = 0$

Factor out $x$: $x[(1 + 4v)dx - (1 + v)x dv - (1 + v)v dx] = 0$

Rearranging: $x[(1 + 4v - v - v^2)dx - (1 + v)x dv] = 0$

Simplifying: $(1 + 3v - v^2)dx = (1 + v)x dv$

Separating: $\frac{dx}{x} = \frac{(1 + v)dv}{1 + 3v - v^2}$

**Final form**: $\ln|x| = \int \frac{(1 + v)dv}{1 + 3v - v^2} + C$

### Example 4: Similar Homogeneous ODE
**Solve**: $(2x + 3y)dx - (x + 2y)dy = 0$

**Solution**:
$P(x,y) = 2x + 3y$ and $Q(x,y) = x + 2y$ are homogeneous of degree 1.

Let $v = \frac{y}{x}$, so $y = vx$ and $dy = x dv + v dx$

Substituting: $(2x + 3vx)dx - (x + 2vx)(x dv + v dx) = 0$

Expanding: $(2x + 3vx)dx - (x + 2vx)x dv - (x + 2vx)v dx = 0$

Factor out $x$: $x[(2 + 3v)dx - (1 + 2v)x dv - (1 + 2v)v dx] = 0$

Simplifying: $(2 + 3v - v - 2v^2)dx = (1 + 2v)x dv$

Rearranging: $(2 + 2v - 2v^2)dx = (1 + 2v)x dv$

Separating: $\frac{dx}{x} = \frac{(1 + 2v)dv}{2 + 2v - 2v^2} = \frac{(1 + 2v)dv}{2(1 + v - v^2)}$

Integrating: $\ln|x| = \frac{1}{2}\int \frac{(1 + 2v)dv}{1 + v - v^2} + C$

**Final solution**: $\ln|x| = \frac{1}{2}\ln|1 + v - v^2| + C$, where $v = \frac{y}{x}$

##