# MATB44 - Week 1 tut1 Teaching Notes

## Ta Information

- **Name**: Shuang Wu
- **Email**: shuaang.wu@mail.utoronto.ca
- **Role**: Teaching Assistant

## Week 1 Topics

### 1. Introduction to Ordinary Differential Equations (ODEs)

- Basic concepts of differential equations
- Definition and classification of differential equations
- Historical context and applications

### 2. Types of Differential Equations

- Ordinary vs Partial Differential Equations
- Linear vs Nonlinear differential equations
- Classification by order (first-order, second-order, etc.)
- Autonomous vs Non-autonomous equations
- Homogeneous vs Non-homogeneous equations

## Detailed Content

### 1. Introduction to Ordinary Differential Equations (ODEs)

#### What is a Differential Equation?

A **differential equation** is an equation that relates a function with its derivatives. It describes how a quantity changes over time or space.

**General form**: $F(x, y, y', y'', ..., y^{(n)}) = 0$

**Example**: $\frac{dy}{dx} = 2x + 3$

#### Why Study Differential Equations?

- **Modeling**: Describe natural phenomena (population growth, heat transfer, motion)
- **Prediction**: Forecast future behavior
- **Control**: Design systems to achieve desired outcomes

### 2. Classification of Differential Equations

#### A. Ordinary vs Partial Differential Equations

**Ordinary Differential Equation (ODE)**:

- Contains only ordinary derivatives
- One independent variable
- Example: $\frac{dy}{dx} = x^2 + y$

**Partial Differential Equation (PDE)**:

- Contains partial derivatives
- Multiple independent variables
- Example: $\frac{\partial u}{\partial t} = k\frac{\partial^2 u}{\partial x^2}$ (heat equation)

#### B. Linear vs Nonlinear

**Linear ODE**:

- Can be written as: $a_n(x)y^{(n)} + a_{n-1}(x)y^{(n-1)} + ... + a_1(x)y' + a_0(x)y = g(x)$
- Example: $y'' + 3y' + 2y = e^x$

**Nonlinear ODE**:

- Contains products or powers of y and its derivatives
- Example: $y'' + (y')^2 + y^3 = 0$

#### C. Classification by Order

**Order**: The highest derivative present in the equation

- **First-order**: $\frac{dy}{dx} = f(x,y)$
- **Second-order**: $\frac{d^2y}{dx^2} = f(x,y,y')$
- **Higher-order**: Contains derivatives of order 3 or higher

#### D. Autonomous vs Non-autonomous

**Autonomous**: Right-hand side doesn't explicitly depend on independent variable

- Example: $\frac{dy}{dt} = y(1-y)$

**Non-autonomous**: Right-hand side explicitly depends on independent variable

- Example: $\frac{dy}{dt} = ty + \sin(t)$

#### E. Homogeneous vs Non-homogeneous

**Homogeneous**: For linear ODEs, when the right-hand side is zero

- General form: $a_n(x)y^{(n)} + a_{n-1}(x)y^{(n-1)} + ... + a_1(x)y' + a_0(x)y = 0$
- Example: $y'' + 3y' + 2y = 0$

**Non-homogeneous**: For linear ODEs, when the right-hand side is non-zero

- General form: $a_n(x)y^{(n)} + a_{n-1}(x)y^{(n-1)} + ... + a_1(x)y' + a_0(x)y = g(x)$ where $g(x) \neq 0$
- Example: $y'' + 3y' + 2y = e^x$

**Note**: The concept of homogeneous/non-homogeneous applies only to linear differential equations.

## Classification Practice Problems

**Exercise**: For each differential equation, determine:

**Order**: The highest derivative present

**Linear**: Yes/No

**Autonomous**: Yes/No

**Homogeneous**: Yes/No (only applies to linear equations)

1. $\frac{dy}{dx} = 3x^2 + 2y$
2. $\frac{d^2y}{dx^2} + 5\frac{dy}{dx} + 6y = 0$
3. $y'' + (y')^2 + y^3 = x$
4. $\frac{dy}{dt} = y^2 - 4y$
5. $\frac{d^3y}{dx^3} + 2\frac{d^2y}{dx^2} + \frac{dy}{dx} = e^x$
6. $x^2y'' + xy' + y = 0$
7. $\frac{dy}{dx} = \sqrt{x + y}$
8. $y''' + 2y'' - y' + y = \sin(x)$
9. $\frac{d^2y}{dx^2} = y^2$
10. $\frac{dy}{dt} = ty + \sin(t)$

**Solutions**:

1. **Order**: 1, **Linear**: Yes, **Autonomous**: No, **Homogeneous**: No
2. **Order**: 2, **Linear**: Yes, **Autonomous**: Yes, **Homogeneous**: Yes
3. **Order**: 2, **Linear**: No, **Autonomous**: No, **Homogeneous**: N/A
4. **Order**: 1, **Linear**: No, **Autonomous**: Yes, **Homogeneous**: N/A
5. **Order**: 3, **Linear**: Yes, **Autonomous**: No, **Homogeneous**: No
6. **Order**: 2, **Linear**: Yes, **Autonomous**: No, **Homogeneous**: Yes
7. **Order**: 1, **Linear**: No, **Autonomous**: No, **Homogeneous**: N/A
8. **Order**: 3, **Linear**: Yes, **Autonomous**: No, **Homogeneous**: No
9. **Order**: 2, **Linear**: No, **Autonomous**: Yes, **Homogeneous**: N/A
10. **Order**: 1, **Linear**: Yes, **Autonomous**: No, **Homogeneous**: No

## Advanced Exercise: Autonomous Equations Property

**Problem**: Let $x^{(k)} = f(x, x^{(1)}, ..., x^{(k-1)})$ be an autonomous equation (or system).

Show that if $\phi(t)$ is a solution, so is $\phi(t-t_0)$.

**Solution**:

Since the equation is autonomous, the right-hand side $f$ does not explicitly depend on the independent variable $t$. 

Given that $\phi(t)$ is a solution, we have:
$$\phi^{(k)}(t) = f(\phi(t), \phi^{(1)}(t), ..., \phi^{(k-1)}(t))$$

Now consider $\psi(t) = \phi(t-t_0)$. We need to show that $\psi(t)$ is also a solution.

Taking derivatives of $\psi(t)$:
- $\psi^{(1)}(t) = \phi^{(1)}(t-t_0)$
- $\psi^{(2)}(t) = \phi^{(2)}(t-t_0)$
- ...
- $\psi^{(k)}(t) = \phi^{(k)}(t-t_0)$

Substituting into the original equation:
$$\psi^{(k)}(t) = \phi^{(k)}(t-t_0) = f(\phi(t-t_0), \phi^{(1)}(t-t_0), ..., \phi^{(k-1)}(t-t_0))$$

Since $\phi(t-t_0) = \psi(t)$, $\phi^{(1)}(t-t_0) = \psi^{(1)}(t)$, etc., we have:
$$\psi^{(k)}(t) = f(\psi(t), \psi^{(1)}(t), ..., \psi^{(k-1)}(t))$$

Therefore, $\psi(t) = \phi(t-t_0)$ is indeed a solution.

**Interpretation**: This property means that autonomous equations are time-invariant - if we shift a solution in time, we get another valid solution. This is a fundamental characteristic of autonomous systems.
