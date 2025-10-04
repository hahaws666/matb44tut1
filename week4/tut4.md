# MATB44 - Week 4 Tutorial Teaching Notes

## Week 4 Topics

### Exact Differential Equations

#### Definition and Recognition
- General form: $M(x,y)dx + N(x,y)dy = 0$
- Exactness condition: $\frac{\partial M}{\partial y} = \frac{\partial N}{\partial x}$
- Solution method: finding potential function $\phi(x,y)$
- Integration techniques and path independence

#### Method of Finding Integrating Factors
- When equations are not exact
- Types of integrating factors: $\mu(x)$, $\mu(y)$, $\mu(xy)$, $\mu(x^2 + y^2)$
- Systematic approach to finding appropriate integrating factors
- Reduction to exact form and solution

## Definition and Theory

### What are Exact Differential Equations?

An **exact differential equation** has the form:
$$M(x,y)dx + N(x,y)dy = 0$$

where there exists a function $\phi(x,y)$ such that:
$$\frac{\partial \phi}{\partial x} = M(x,y) \quad \text{and} \quad \frac{\partial \phi}{\partial y} = N(x,y)$$

### Exactness Condition

The equation $M(x,y)dx + N(x,y)dy = 0$ is **exact** if and only if:
$$\frac{\partial M}{\partial y} = \frac{\partial N}{\partial x}$$

### Solution Method for Exact Equations

1. **Verify exactness**: Check that $\frac{\partial M}{\partial y} = \frac{\partial N}{\partial x}$
2. **Find potential function**: Integrate $M$ with respect to $x$ or $N$ with respect to $y$
3. **Determine arbitrary function**: Use the other partial derivative condition
4. **Write general solution**: $\phi(x,y) = C$

### Integrating Factors

When an equation is **not exact**, we can sometimes find an **integrating factor** $\mu(x,y)$ such that:
$$\mu(x,y)M(x,y)dx + \mu(x,y)N(x,y)dy = 0$$

is exact.

#### Methods for Finding Integrating Factors

**Method 1**: $\mu = \mu(x)$ (depends only on $x$)
- Condition: $\frac{P_y - Q_x}{Q} = F(x)$
- Formula: $I(x) = e^{\int F(x)dx}$

**Method 2**: $\mu = \mu(y)$ (depends only on $y$)
- Condition: $\frac{P_y - Q_x}{P} = F(y)$
- Formula: $I(y) = e^{-\int F(y)dy}$

**Method 3**: $\mu = \mu(x/y)$ (depends on ratio $x/y$)
- Condition: $y^2 \cdot \frac{P_y - Q_x}{xP + yQ} = F(x/y)$
- Formula: $I(x/y) = e^{\int F(u)du}$ where $u = x/y$

**Method 4**: $\mu = \mu(xy)$ (depends on product $xy$)
- Condition: $\frac{P_y - Q_x}{yQ - xP} = F(xy)$
- Formula: $I(xy) = I(u) = e^{\int F(u)du}$ where $u = xy$

**Method 5**: Monomial Integrating Factor
- For equations with monomial terms $x^a y^b$
- General form: $P(x,y)dx + Q(x,y)dy = 0$
- Where $P = (x^{a_1} y^{a_2} + x^{b_1} y^{b_2})$ and $Q = (x^{c_0} y^{c_2} + x^{d_0} y^{d_2})$
- Integrating factor: $I = x^a y^b$ where $a, b$ are to be determined

## Key Examples

### example 1 exact 
**Solve**: $(2xy + 3x^2)dx + (x^2 + 2y)dy = 0$

**Solution**:
**Step 1**: Check exactness
- $P(x,y) = 2xy + 3x^2$, $Q(x,y) = x^2 + 2y$
- $P_y = 2x$, $Q_x = 2x$

Since $P_y = Q_x = 2x$, the equation is **exact**.

**Step 2**: Find potential function
From $\frac{\partial \phi}{\partial x} = P = 2xy + 3x^2$:
$$\phi(x,y) = \int (2xy + 3x^2)dx = x^2y + x^3 + h(y)$$

**Step 3**: Determine $h(y)$
From $\frac{\partial \phi}{\partial y} = Q = x^2 + 2y$:
$$\frac{\partial}{\partial y}(x^2y + x^3 + h(y)) = x^2 + h'(y) = x^2 + 2y$$

Therefore: $h'(y) = 2y$, so $h(y) = y^2 + C$

**Final solution**: $x^2y + x^3 + y^2 = C$

### example 2 applying method 1
**Solve**: $((x^2+1)y + x)\,dx + x(x^2+1)\,dy = 0$

**Solution**:
**Step 1**: Check exactness
- $P = (x^2+1)y + x$, $Q = x(x^2+1)$
- $P_y = x^2 + 1$, $Q_x = 3x^2 + 1$

Since $P_y \ne Q_x$, the equation is not exact.

**Step 2**: Try $\mu = \mu(x)$
Compute
$$\frac{P_y - Q_x}{Q} = \frac{(x^2+1) - (3x^2+1)}{x(x^2+1)} = \frac{-2x^2}{x(x^2+1)} = -\frac{2x}{x^2+1} = F(x)$$
This depends only on $x$, so Method 1 applies.

Find the integrating factor:
$$\mu(x) = e^{\int F(x)\,dx} = e^{\int -\frac{2x}{x^2+1}dx} = e^{-\ln(x^2+1)} = \frac{1}{x^2+1}$$

**Step 3**: Multiply by $\mu(x)$ and solve as exact
Multiply the equation by $\mu(x) = \frac{1}{x^2+1}$:
$$\Big(y + \frac{x}{x^2+1}\Big)dx + x\,dy = 0$$
Now $\tilde P = y + \frac{x}{x^2+1}$, $\tilde Q = x$ with
$\tilde P_y = 1$, $\tilde Q_x = 1$ so it is exact.

Integrate $\tilde P$ with respect to $x$:
$$\phi(x,y) = \int \Big(y + \frac{x}{x^2+1}\Big)dx = xy + \tfrac{1}{2}\ln(x^2+1) + h(y)$$
Differentiate with respect to $y$ and match $\tilde Q$:
$$\phi_y = x + h'(y) = \tilde Q = x \;\Rightarrow\; h'(y)=0 \Rightarrow h(y)=C$$

**Final solution**: 
$$xy + \tfrac{1}{2}\ln(x^2+1) = C$$


### example 3 applying method 2
**Solve**: $((y^2+1))\,dx + (xy)\,dy = 0$ with $P(y)=y^2+1$, $Q(x,y)=xy$

**Solution**:
**Step 1**: Check condition for $\mu(y)$
- $P_y = 2y$, $Q_x = y$
- Compute $\dfrac{P_y - Q_x}{P} = \dfrac{2y - y}{y^2 + 1} = \dfrac{y}{y^2 + 1} = F(y)$, which depends only on $y$.

**Step 2**: Find integrating factor $\mu(y)$ (Method 2)
$$\mu(y) = e^{-\int F(y)\,dy} = e^{-\int \frac{y}{y^2+1}dy} = e^{-\tfrac{1}{2}\ln(y^2+1)} = \frac{1}{\sqrt{y^2+1}}$$

**Step 3**: Multiply and check exactness
After multiplying by $\mu(y)$:
- $\tilde P = \mu P = \dfrac{y^2+1}{\sqrt{y^2+1}} = \sqrt{y^2+1}$
- $\tilde Q = \mu Q = \dfrac{xy}{\sqrt{y^2+1}}$
Then $\tilde P_y = \dfrac{y}{\sqrt{y^2+1}}$ and $\tilde Q_x = \dfrac{y}{\sqrt{y^2+1}}$, so the equation is exact.

**Step 4**: Solve the exact equation
Integrate $\tilde P$ with respect to $x$:
$$\phi(x,y) = \int \sqrt{y^2+1}\,dx = x\sqrt{y^2+1} + h(y)$$
Differentiate w.r.t. $y$ and match $\tilde Q$:
$$\phi_y = x\frac{y}{\sqrt{y^2+1}} + h'(y) = \tilde Q = \frac{xy}{\sqrt{y^2+1}} \Rightarrow h'(y)=0$$
Thus $h(y)=C$.

**Final solution**:
$$x\sqrt{y^2+1} = C$$


### example 4 applying method 3
**Solve**: $\displaystyle \frac{x^2}{y}\,dx + x\,dy = 0$ with $P(x,y)=\frac{x^2}{y}$, $Q(x,y)=x$

**Solution (Method 3: $\mu=\mu(x/y)$)**:
**Step 1**: Verify the condition depends only on $u=x/y$
- $P_y = -\dfrac{x^2}{y^2}$, $Q_x = 1$ (non-exact)
- Compute
$$y^2\,\frac{P_y - Q_x}{xP + yQ} = y^2\,\frac{-\dfrac{x^2}{y^2} - 1}{x\cdot \dfrac{x^2}{y} + y\cdot x} = \frac{-(x^2+y^2)}{x^3/ y + xy} = -\frac{x^2+y^2}{x^2(x/y)+y^2(x/y)} = -\frac{u^2+1}{u(u^2+1)} = -\frac{1}{u} = F(u)$$
This depends only on $u=x/y$, so Method 3 applies.

**Step 2**: Find integrating factor $\mu(u)$
$$\mu(u) = e^{\int F(u)\,du} = e^{\int -\frac{1}{u} du} = e^{-\ln|u|} = \frac{1}{|u|}$$
We take $\mu(x,y) = \dfrac{1}{x/y} = \dfrac{y}{x}$ (up to a constant factor).

**Step 3**: Multiply and check exactness
Multiply by $\mu=\dfrac{y}{x}$:
- $\tilde P = \dfrac{y}{x}\cdot \dfrac{x^2}{y} = x$
- $\tilde Q = \dfrac{y}{x}\cdot x = y$
Then $\tilde P_y = 0$, $\tilde Q_x = 0$, so it is exact.

**Step 4**: Solve
Integrate $\tilde P$ with respect to $x$:
$$\phi(x,y) = \int x\,dx = \tfrac{1}{2}x^2 + h(y)$$
Differentiate and match $\tilde Q$:
$$\phi_y = h'(y) = y \Rightarrow h(y) = \tfrac{1}{2}y^2 + C$$

**Final solution**:
$$\tfrac{1}{2}x^2 + \tfrac{1}{2}y^2 = C $$

### example 5 applying method 4
**Solve**: $x\big(1+(xy)^2\big)\,dx + y\big(1+(xy)^2\big)\,dy = 0$ with $P=x(1+(xy)^2)$, $Q=y(1+(xy)^2)$

**Solution (Method 4: $\mu=\mu(xy)$)**:
**Step 1**: Verify the condition depends only on $u=xy$
- $P_y = \partial_y\big[x(1+u^2)\big] = x\cdot 2u\,u_y = x\cdot 2u\cdot x = 2x^2u = 2x^3y$
- $Q_x = \partial_x\big[y(1+u^2)\big] = y\cdot 2u\,u_x = y\cdot 2u\cdot y = 2y^2u = 2xy^3$
- Compute
$$\frac{P_y - Q_x}{yQ - xP} = \frac{2xy(x^2 - y^2)}{\,(y^2 - x^2)(1+u^2)\,} = -\frac{2u}{1+u^2} = F(u)$$
This depends only on $u=xy$, so Method 4 applies.

**Step 2**: Find integrating factor $\mu(u)$
$$\mu(u) = e^{\int F(u)\,du} = e^{\int -\frac{2u}{1+u^2}du} = e^{-\ln(1+u^2)} = \frac{1}{1+u^2}$$

**Step 3**: Multiply and solve as exact
Multiply by $\mu=\dfrac{1}{1+(xy)^2}$:
- $\tilde P = \dfrac{x(1+(xy)^2)}{1+(xy)^2} = x$
- $\tilde Q = \dfrac{y(1+(xy)^2)}{1+(xy)^2} = y$
Then the equation becomes $x\,dx + y\,dy = 0$, which is exact with potential
$$\phi(x,y) = \tfrac{1}{2}x^2 + \tfrac{1}{2}y^2 = C$$

**Final solution**:
$$\tfrac{1}{2}x^2 + \tfrac{1}{2}y^2 = C$$


### example 6 applying method 5

**Solve**: $(y^2 + x^2y)\,dx + (x^2 + xy^2)\,dy = 0$ with $P=y^2+x^2y$, $Q=x^2+xy^2$.

**Solution (Method 5: Monomial Integrating Factor)**:

**Step 1**: Check exactness
$$P_y = 2y + x^2, \qquad Q_x = 2x + y^2 \;(\neq)$$

**Step 2**: Assume a monomial integrating factor
$$\mu(x,y) = x^a y^b$$
and require exactness of $\mu P\,dx + \mu Q\,dy=0$.

**Step 3**: Expand $\mu P$ and $\mu Q$
$$x^a y^b P = x^a y^{b+2} + x^{a+2}y^{b+1}, \qquad x^a y^b Q = x^{a+2}y^{b} + x^{a+1}y^{b+2}.$$

**Step 4**: Differentiate
$$\partial_y(x^a y^b P) = (b+2)x^a y^{b+1} + (b+1)x^{a+2}y^{b},$$
$$\partial_x(x^a y^b Q) = (a+2)x^{a+1}y^{b} + (a+1)x^{a}y^{b+2}.$$

**Step 5**: Match coefficients
The monomials $\{x^a y^{b+1},\, x^{a+2}y^{b}\}$ and $\{x^{a+1}y^{b},\, x^{a}y^{b+2}\}$ cannot be paired to have identical exponents in $x$ and $y$ for any constants $a,b$. Equivalently, using
$$M_y - N_x = a\,\frac{N}{x} - b\,\frac{M}{y} \;(M=P,\;N=Q),$$
the resulting linear system for $a,b$ is inconsistent.

