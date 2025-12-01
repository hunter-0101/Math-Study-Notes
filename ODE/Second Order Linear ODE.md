The general form of **second order ODE** is $$\frac{d^2y}{dt^2}=f(t,y,\frac{dy}{dt})$$When $f$ has the form $$f(t,y,\frac{dy}{dt})=g(t)-p(t)\frac{dy}{dt}-q(t)y$$then it is called **linear** equation. Sometimes also written as $P(t)y''+Q(t)y'+R(t)y=G(t)$.
An initial value, in this case, is $y(t_0)=y_0,y'(t_0)=y_0'$.
### Homogeneous second order ODE
A second order linear equation is **homogeneous** if $g(t)=0$. When the coefficients are constant, the general form becomes $$ay''+by'+cy=0$$Assuming that $y=e^{rt}$, the equation can be reduced to $ar^2+br+c=0$, which is called the **characteristic equation** of the differential equation. Using roots of characteristic equation we can construct the general solution.
> [!info] Existence and Uniqueness Theorem
> Consider the initial value problem$$y''+p(t)y'+q(t)y=g(t),\quad y(t_0)=y_0,\quad y''(t_0)=y_0'$$where $p,q,g$ are continuous on an open interval $I$ that contains the point $t_0$. Then there is exactly one solution $y=\phi(t)$ of this problem, and the solution exists throughout the interval $I$.

**Principle of superposition**: the linear combination of two solutions of a second order homogeneous equation is also a solution.
Based on the principle of superposition, once we have two solutions $y_1,y_2$, we can construct infinitely many solutions. Considering the initial value problem, we have $$\begin{align}c_1y_1(t_0)+c_2y_2(t_0)=y_0\\c_1y_1'(t_0)+c_2y_2'(t_0)=y_0'\end{align}$$Then the existence of solution depend of the so-called **Wronskian determinant** $$W(y_1,y_2)(t_0) =\begin{vmatrix}y_1(t_0)&y_2(t_0)\\y_1'(t_0)&y_2'(t_0)\end{vmatrix}$$
> Assume $y_1,y_2$ to be two solutions of a second order homogeneous equation, then their linear combination includes every solution iff there is a point $t_0$ where $W(y_1,y_2)(t_0)\neq0$.

Solutions satisfying $W(y_1,y_2)(t_0)\neq0$ can be found by solving the initial value problem $y(t_0)=1,y'(t_0)=0$ and $y(t_0)=0, y'(t_0)=1$. Such solution pair is called **a fundamental set of solutions.**
> For complex solutions of a homogeneous second order equation, its real/imagery parts are also solutions; its complex conjugate is also a solution due to superposition theorem.

> [!info] Abel's theorem
> If $y_1,y_2$ are solutions of $y''+p(t)y'+q(t)y=0$, then $$W(y_1,y_2)(t)=c\exp\Big[-\int p(t)dt\Big]$$This can be proven with definition of Wronskian and its derivative.
> From this we know that the **Wronskian of any two fundamental sets of solutions can only differ by a multiplicative constant**.

Combined with the existence of solutions, we know that $W$ is **either always zero or never zero** (**This only applies to ODEs of the form above**).
- **Exact equations**: the equation $P(x)y''+Q(x)y'+R(x)y=0$ is exact if it can be written in the form $$[P(x)y']'+[f(x)y]'=0$$This kind of equation can be easily solved by integrating both parts and solve a first order equation.
	- exactness $\iff P''(x)-Q'(x)+R(x)=0$.
- **Adjoint equation**: a non-exact second order linear homogenous equation can be made exact by multiplying a integrating factor $\mu(x)$. The final result is $$[\mu P(x)y']'+[f(x)y]'=0$$where $\mu(x)$ should satisfy $$P\mu''+(2P'-Q)\mu'+(P''-Q'+R)\mu=0$$
### Complex roots of characteristic equations
With Euler's formula we define $e^{(\lambda+i\mu)t}=e^{\lambda t}(\cos\mu t+i\sin\mu t)$. It can be verified that $\frac{d}{dt}(e^{rt})=re^{rt}$.
Exponential solution still applied in this case
- When trying to find real solutions, use the properties of complex solutions.
- Use Wronskian to verify fundamental set of solutions.
### Repeated roots of characteristic equations
After determining $y_1$ from the root, we consider $y_2=v(t)y_1$. By substituting it into the equation we get $v(t)=c_1+c_2t$.
- Their Wronskian is nonzero, thus making up a fundamental set of solutions.
- **Reduction of order**: the above procedure is generally applicable in many cases, which will result in a first order equation of $v(t)$.
### Non-homogenous equations
For a generation equation $y''+p(t)y'+q(t)y=g(t)$, denoting two of its solutions as $Y_1,Y_2$, and a fundamental set of solutions of its homogeneous form as $y_1,y_2$, then $$Y_1(t)-Y_2(t)=c_1y_1(t)+c_2y_2(t)$$
## Other note
- **Abel's trick**: by Abel's theorem we can always work out $W$ first without solving the solution itself. If one of the solution $y_1$ is known, then notice that $$\frac{W}{y_1^2}=\frac{y_1y_2'-y_2y_1'}{y_1^2}=\frac{d}{dx}\frac{y_2}{y_1}$$and in this way we can directly integrate two sides and then multiply by $y_1$ to get $y_2$. 