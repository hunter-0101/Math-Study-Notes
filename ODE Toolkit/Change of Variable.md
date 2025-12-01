Similar to its counterpart in [[Integral Calculus on Euclidean Space]], change of variable makes no change to the dynamic of the DE itself, but rather reformulate it under a different coordinate for which explicit integral formula can be observed. 
- **Intuition**: change of variable can be visualized as a **re-labeling** or **stretching/compressing** the vertical $y$-axis to create a new $z$-axis. It simplifies the equation by controlling the **slope**, which would usually cancels out the complicated **non-linear** term in the original ODE,  so that the relationship between $z,z'$ linear (or separable). 
- **Invariance and canonical forms**: while the dynamic of the ODE is preserved, change of variable alters the **mathematical representation** of that dynamic. In particular, ODE often possesses a **symmetry**, and the goal is to find the **canonical coordinate system** where the ODE's symmetry becomes explicit and trivial. 
## General formulation
### Via composition
Assuming that the solution is denoted $y=y(x)$. In general two different directions can be observed in this method:
1. **Change in $x$**: by replacing $x$ with another variable $t$ we can get $$x=f(t)\quad\Longrightarrow\quad\begin{cases}\dfrac{dy}{dt}=f'(t)\dfrac{dy}{dx}\\\dfrac{d^2y}{dt^2}=f''(t)\dfrac{dy}{dx}+(f'(t))^2\dfrac{d^2y}{dx^2}\\\quad\quad\vdots\end{cases}$$and we can solve for $\frac{dy}{dx}$ via $\frac{dy}{dt}$. In this way we introduces **derivatives** $f^{(k)}(t)$ (also as functions of $t$) as coefficients.
2. **Change in $y$**: by replacing $y$ with another function $z$ we can get $$z=f(y)\quad\Longrightarrow\quad\begin{cases}\dfrac{dz}{dx}=f'(y)\dfrac{dy}{dx}\\\dfrac{d^2z}{dx^2}=f''(y)\left(\dfrac{dy}{dx}\right)^2+f'(y)\dfrac{dy}{dx}\\\quad\quad\vdots\end{cases}$$and we can solve for $\frac{dy}{dx}$ via $\frac{dz}{dx}$. In this way we're introducing two categories of terms:
	1. **Powers of first order derivatives $(dy/dx)^k$** are introduced to replace higher order derivatives.
	2. **Functions of $y$** are introduced as coefficients. 
These two different methods of introducing new variants are quite useful for solving a wide range of ODEs. 
### Via other forms 

## Example
Below we list some specific classes of ODEs that can be solved via change of variable. 
- **Euler's equation**: Euler's equation is an ODE of the form  $$\sum_{i=0}^na_ix^iy^{(i)}=0,\quad a_i\in\mathbb R$$Consider $x=e^t$ which realizes $\frac{dx}{dt}=x$, hence further we have $$\frac{dy}{dt}=x\frac{dy}{dx}\quad\Longrightarrow\quad\frac{d^2y}{dt^2}=x\frac{dy}{dx}+x^2\frac{d^2y}{dx^2}\quad\Longrightarrow\quad\cdots$$In this way we can solve $x^iy^{(i)}$ using $\frac{dy}{dt}$, and by substitution we transform the original equation into a homogeneous [[Linear ODE]] one with constant coefficients, hence solvable. 
- **Bernoulli's equation**: this refers to equations of the form $$y'+p(x)y=q(x)y^n,\quad n\in\mathbb Z_{\ge2}$$Consider $z=y^{1-n}$, then the equation is transformed into a linear one as above.
- **Riccati equation**: consider an ODE of the form $$y'=q_0(x)+q_1(x)y+q_2(x)y^2$$By setting $v=q_2y$ we get $$v'=q_0q_2+\left(q_1+\frac{q_2'}{q_2}\right)v+v^2$$and by further setting $v=-u'/u$ we get $$u''-R(x)u'+S(x)u=0\where R=q_1+\frac{q_2'}{q_2},\quad S=q_0q_2$$which is a [[Linear ODE]], hence can be easily solved. 
- **Fractional homogeneous equation**: consider equations of the form $$\frac{dy}{dx}=\frac{a_1y+b_1x+c_1}{a_2y+b_2x+c_2}$$