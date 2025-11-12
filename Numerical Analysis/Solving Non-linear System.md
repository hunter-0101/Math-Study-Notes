We're mainly interested in finding the (real, isolated) solution to a non-linear system $$f_i(x_1,\cdots,x_n)=0,\quad 1\le i\le n$$We'll mainly focus on iterative methods.
## Non-linear equation
We'll try to solve the equation $$f(x)=0$$given that $f$ is non-linear.
- **Simple iterative method**: if we somehow find $f(x)=0\iff x=\phi(x)$, then finding solution to $f(x)=0$ is equivalent to finding fixed point of $\phi(x)$.
- **Newton's method**: given $f(x)$ and an initial value $x_k$ we construct $$y=f(x_k)+f'(x_k)(x-x_k)$$and take its zero as the next initial value.
	- **Revised versions**: linear approximation may be replaced by Taylor series of any order, and coefficients may be fixed to simplify the calculation.
### Convergence of iterative method
Given $x^*$ the unknown solution, if there exists some $B_\varepsilon(x_0)$ s.t. any initial value lying inside $B_\varepsilon(x_0)$ eventually converges to $x^*$ then it's called **locally convergent**; if the given interval $[a,b]\subset B_\varepsilon(x_0)$ then it's called **globally convergent**.
- **Simple iterative method**: for $\phi\in C^1,\phi([a,b])\subset[a,b]$ and $|\phi'|\le\delta<1$ then the method is globally convergent with estimation of error $$|x^*-x_k|\le\frac{\delta^k}{1-\delta}|x_1-x_0|$$Existence & uniqueness of fixed point is obvious, and the estimation is a simple application of triangle inequality.
	- **Local convergence**: discarding the condition $\im\phi\subset[a,b]$ yields local convergence, since the value might be "thrown away" from $[a,b]$ after just one iteration.
	- **Necessity of $\delta<1$**: since $[a,b]$ is compact there is no possibility for $|\phi'|$ to approach $1$, but if $|\phi'|=1$ is allowed a simple counterexample is $y=1-x$.
- **Newton's method**: since Newton's method is equivalent to simple iterative method taking $$\phi(x)=x-\frac{f(x)}{f'(x)},\quad\phi'(x)=\frac{f(x)f''(x)}{(f'(x))^2}$$Hence by above we have that Newton's method is locally convergent as long as $f'(x^*)\neq0$.
	- **Global convergence**: given $f\in C^2,f(a)f(b)<0,f'(x)\neq0,f''(x)$ doesn't changes sign and $f(x_0)f''(x_0)>0$ we have the method converging globally (and monotonically). The proof is geometrically obvious.
### Convergence speed
An iterative series is said to have order of convergence $p\ge1$ with error constant $c>0$ if $$\lim_{k\to\infty}\frac{|x^*-x_{k+1}|}{|x^*-x_k|^p}=c\neq0$$In particular, we call $p=1$ as linear convergence, $p>1$ as hyper-linear convergence, and $p=2$ as quadratic convergence.
**Convergence order theorem**: given $\phi\in C^p$ the iterative series $\set{x_n}$ has convergence order $p$ iff $$\phi'(x^*)=\phi''(x^*)=\cdots=\phi^{(p-1)}(x^*)=0,\phi^{(p)}(x^*)\neq0$$Sufficiency is a direct application of Taylor's theorem ([[Differential Calculus on Euclidean Space]]), since we can verify that $c=\frac{1}{p!}|\phi^{(p)}(x^*)|$; necessity is a simple argument of contradiction.
### Convergence acceleration
- **Relaxation**: given the **relaxation factor** $\omega$ we write $$x=\phi(x)\iff x-\omega x=\phi(x)-\omega x\iff x=\frac{\phi(x)-\omega x}{1-\omega }$$Denote $\psi(x)=\frac{\phi(x)-\omega x}{1-\omega}$, then $\psi'(x)=\frac{1}{1-\omega}(\phi'(x)-\omega)$. By picking $\omega\approx\phi'(x^*)$ we accelerate the convergence to order $2$.
- **Aitken acceleration**: if $\set{x_n}\to x^*$ with $p=1$ we have $$\frac{x^*-x_{k+1}}{x^*-x_k}\approx\frac{x^*-x_k}{x^*-x_{k-1}}\iff x^*\approx x_{k+1}-\frac{(x_{k+1}-x_k)^2}{x_{k+1}-2x_k+x_{k-1}}$$Then $\overline x_{k+1}=\text{RHS}$ would converge faster.
	- **Steffensen acceleration algorithm**: starting from $x_0$ we take $x_1=\phi(x_0),x_2=\phi(x_1)$ and check the error bound. If not satisfied we use the Aitken acceleration to calculate $\overline x$ and start again with $x_0=\overline x$.
## Non-linear system
Given a system $$f_i(x_1,\cdots,x_n)=0,\quad 1\le i\le n$$with at least on $f_i$ non-linear, we try to solve the system via iterative method.
- **Simple iterative method**: similar to one single equation, if we manage to find $$f_i(x_1,\cdots,x_n)=0\quad\iff\quad x_i=\phi(x_1,\cdots,x_n)$$then iterative method could be applied to find the fixed point $x^*=(x_1^*,\cdots,x_n^*)^T$.
	- **Gauss-Seidel method**: similar to [[Solving Linear System]] we also have the iteration $$x_i^{(k+1)}=\phi_i(x_1^{(k+1)},\cdots,x_{i-1}^{(k+1)},x_i^{(k)},\cdots,x_n^{(k)})$$
	- **Convergence**: we can similarly define the order and error constant in this case with $|\cdot|$ replaced by $\|\cdot\|$ and $|\phi'|$ replaced by $|J_\phi|$.
		- **Global convergence**: if $\|\phi(x)-\phi(y)\|\le\delta\|x-y\|,\delta<1$ then the theorem holds.
		- **Local convergence**: if $\rho(J_\phi(x^*))<1$ then it convergence locally. [[Matrix]]
- **Newton's method**: by Taylor's theorem of higher dimension ([[Differential Calculus on Euclidean Space]]) we can establish the iteration $$x^{(k+1)}=x^{(k)}-J_f^{-1}(x^{(k)})f(x^{(k)})\iff\begin{cases}x^{(k+1)}=x^{(k)}-\Delta x\\ J_f(x^{(k)})\Delta x=f(x^{(k)})\end{cases}$$the principle is essentially the same.