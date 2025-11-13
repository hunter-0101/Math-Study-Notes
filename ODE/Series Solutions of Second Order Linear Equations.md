**Motivation**: in cases where ordinary methods cannot be applied (say, even for an homogeneous equation we cannot easily get its solution), we make a drawback and consider to only get a series solution that sufficiently approximates the true solution. This method can be applied to ODE of any order, although for those with order higher than $3$ it's usually not the most efficient way.
Below we focus on the solution to second order equation $$y''+p(x)y'+q(x)y=0$$
## Series solutions near an ordinary point
- **Ordinary point**: is a point where the functions $p(x)$ and $q(x)$ are analytic. For an ordinary point $x_0$, we assume a solution of the form$$y(x) = \sum_{n=0}^{\infty}a_n(x-x_0)^n$$
	1. **Substitute** this series into the differential equation.
	2. **Collect like powers** of $(x - x_0)$ to derive a recurrence relation for the coefficients $a_n$.
	3. The **radius of convergence** of the series is determined by the distance to the nearest **singular point**.
> [!info] Superposition of series solution
> For equations of the above form, if $p,q$ are analytic at $x_0$, then the general solution is $$y=\sum_{n=0}^\infty a_n(x-x_0)^n=a_0y_1(x)+a_1y_2(x)$$ where $a_0,a_1$ are arbitrary and $y_1,y_2$ are two power series solutions that are analytic at $x_0$. $y_1,y_2$ form a fundamental set of solutions, and the radius of convergence for each is at least as large as the minimum of the radii of convergence of the series for $p,q$.
## Series Solutions Near a Regular Singular Point
**Regular singular point**: for the equation of the form $P(x)y''+Q(x)y'+R(x)=0$, consider the point $x_0$ in which the limit $$\lim_{x\to x_0}(x-x_0)\frac{Q(x)}{P(x)},\quad \lim_{x\to x_0}(x-x_0)^2\frac{R(x)}{P(x)}\text{ are finite.}$$this condition ensures a "weak singularity", on which the series method can be applied. Singular points that do not satisfy this condition are called **irregular**.
- **Euler equation**: Euler equation has the form $$x^2y'' + axy' + by = 0$$This type of equation is characterized by having a **regular singular point** at $x=0$. 
- By transforming the equation, we assume a solution of the form $$y(x) = x^r$$ and solve for $r$ by substituting into the Euler equation.
#### Solutions for different cases:
1. **Real, distinct roots**: When the characteristic equation has real, distinct roots $r_1, r_2$, the solution is $$y(x) = c_1x^{r_1} + c_2x^{r_2}$$
2. **Equal roots**: When the characteristic equation has a repeated root $r$, the solution is $$y(x) = c_1x^r + c_2x^r\ln(x)$$
3. **Complex roots**: If the roots are complex $r = \alpha \pm i\beta$, the general solution is $$y(x) = x^\alpha(c_1\cos(\beta\ln(x)) + c_2\sin(\beta\ln(x)))$$
For equations with a **regular singular point**, we can extend the series method:
1. Assume a solution of the form $$y(x) = \sum_{n=0}^{\infty}a_nx^{n+r}$$ where $r$ is found from the **indicial equation**.
2. Depending on the nature of the roots of the indicial equation, the solution varies:
   - **Equal roots**: Solution is of the form $$y(x) = c_1x^r + c_2x^r\ln(x)$$
   - **Roots differing by an integer**: One solution is straightforward, but the second solution involves logarithmic terms, similar to the case of equal roots.
## Bessel's Equation
**Bessel's equation** is an important second-order equation that arises in many physical problems, especially in cylindrical coordinates. The standard form is:
$$x^2y'' + xy' + (x^2 - n^2)y = 0$$
- **Bessel equation of order zero**: $$x^2y'' + xy' + x^2y = 0$$The solution is given by **Bessel functions of the first kind**, denoted as $J_0(x)$, and is of the form $$J_0(x) = \sum_{m=0}^{\infty} \frac{(-1)^m}{m!\Gamma(m+1)}\left(\frac{x}{2}\right)^{2m}$$
- **Bessel function of the first kind of order zero**: $J_0(x)$, represents oscillatory solutions and is often used in problems involving wave propagation and vibrations.
- **Bessel equation of order one-half**: the solutions involve trigonometric functions and can be expressed in terms of sine and cosine.
- **Bessel equation of order one**: $$x^2y'' + xy' + (x^2 - 1)y = 0$$The solution is the **Bessel function of the first kind of order one**, denoted $J_1(x)$, which is given by $$J_1(x) = \sum_{m=0}^{\infty} \frac{(-1)^m}{m!(m+1)!}\left(\frac{x}{2}\right)^{2m+1}$$
