**Motivation**: the property of fundamental solution [[Laplace's Equation]] as a solution to Poisson's equation after convolution is a perfect example illustrating advantage of distributional derivative over functional derivative. Such case is pervasive across the study of PDE, and a formal theory of distribution would help a lot both in theory and application.

---
## Distribution
Given some open $\Omega\subset\mathbb R^d$, define the space of **test functions** as $$\mathcal D(\Omega)=C_c^\infty(\Omega)=\set{(f:\Omega\to\mathbb C):f\text{ compactly supported and smooth}}$$A **distribution** on $\Omega$ is a functional ([[Dual Space]]) $T\in\mathcal D^*(\Omega)$ that satisfies any one of the following two equivalent statements:
1. **Boundedness**: for every compact $K\subset U$ there exists $C>0,N\in\mathbb N$ s.t. $$|T(f)|\le C\sup\set{|\partial^\alpha f(x)|:x\in\Omega,|\alpha|\le N},\quad\forall f\in\mathcal D(K)$$Here $C$ is sometimes taken to be the norm on $\mathcal D^*$.
2. **Continuity**: for any compact $K\subset\Omega$ and any sequence $\set{f_i}_{i=1}^\infty$ with $\supp f_i\subset K$, we have $$\partial^\alpha f_i\to0\text{ uniformly on }\Omega,\quad\forall\alpha\quad\Longrightarrow\quad T(f_i)\to0$$This is exactly how we define continuity in $\mathcal D^*$.
Motivations for such definition can be found in [[Hölder Space]].
- **Calculation axioms**: we define the following calculations for distributions
	- **Summation**: $(f+g)[\varphi]=f[\varphi]+g[\varphi]$.
	- **product by multiplicator**: $(\chi f)[\varphi]=f[\chi\varphi]$.
	- We say that $f=0$ on interval $I$ if $f[\varphi]=0$ for all $\varphi\in\mathcal S,\supp\varphi\subset I$.
- **Derivative**: define $f'[\varphi]=-f[\varphi']$ and call $f'$ the derivative of $f$. Its intuitive comes from the ordinary integration by parts formula.
	- By definition we deduce $(\chi f)'=\chi'f+\chi f'$.
	- A test function $\varphi\in\mathcal S$ is the derivative of another function in $\mathcal S$ iff $\int_\mathbb R\varphi(x)dx=0$.
	- For $f\in\mathcal S'$, we have $f'=0\iff f\equiv C$.
- **Convergence**: we say that $f_i\xrightarrow{\mathcal S'}f$ if $\lim_{i\to\infty}f_i[\varphi]=f[\varphi]$ for all $\varphi\in\mathcal S$.
- **Convolution**: for $f\in\mathcal S,\varphi\in\mathcal S'$ the definition and properties of [[Convolution]] still applies.
## Fourier transform of distribution
In this section we develop some results of [[FT on L1]] generalized to distribution theory.
- **$\mathcal F$ on $\mathcal S$**: the FT $\mathcal F$ is a continuous bijection of space $\mathcal S$ onto itself.
  **Proof**: since $\varphi^{(k)}\in L^1,\forall k\in\mathbb N$ for any $\varphi\in\mathcal S$, their FT are well-defined, and any $\varphi$ can also be put into the inversion formula since it decays fast enough. For continuity the reasoning is similar based on definition of convergence.
- **$\mathcal F$ on $\mathcal S'$**: define $\hat f[\varphi]=f[\hat\varphi]$, then $\hat f\in\mathcal S'$ since it's linear, and its continuity follows from the (uniform) continuity of FT. 
	- Inspired by the polarized Plancherel formula $\int_\mathbb Rf(x)\hat g(x)dx=\int_\mathbb R\hat f(\xi)g(\xi)d\xi$.
	- $f$ is even/odd $\iff$ $\hat f$ is even/odd.
	- $\mathcal F(f')=2\pi i\xi\hat f$.
- **Unifying Fourier analysis**: define the **delta comb** (or **pulse train**) as $$\Shah=\sum_{n\in\mathbb Z}\delta_n\quad\text{or}\quad\Shah(x)=\sum_{n\in\mathbb Z}\delta(x-n)$$then obviously $\Shah[\varphi]=\sum_{n\in\mathbb Z}\varphi(n)$. Using this Fourier series can be represented as a periodic version of FT.