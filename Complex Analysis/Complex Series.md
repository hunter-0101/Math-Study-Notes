Complex sequence inherits all properties from [[Series]] form real analysis, with the metric defined by $d(z,w)=|z-w|$.
## Complex power series
A complex power series is of the form $\sum_{n=0}^\infty a_nz^n,a_n\in\mathbb C$. Define the partial sum $S_N=\sum_{n=0}^N a_nz^n$, and the real partial sum $S_N^*=\sum_{n=0}^N|a_n|r^n$ where $r=|z|$.
- **Radius of convergence**: there exists $\rho$ given by the **Hadamard formula**:$$\rho=\frac{1}{\limsup|a_n|^{1/n}}$$such that $\sum a_nz^n$ converges absolutely on $\set{|z|<\rho}$ and diverges for $|z|>\rho$. This follows from comparison test ([[Series]]), similar to that of [[Function on Euclidean Space]]. Moreover the convergence is uniform on any compact subset of disk of convergence, mimicking Abel test.
	- $\rho$ is non-decreasing under addition and Cauchy product of series.
- **Term-wise differentiation**: for $f=\sum_{n=0}^\infty a_nz^n$, its derivative on disk of convergence is given by term-by-term differentiation$$f'(z)=\sum_{n=0}^\infty na_nz^{n-1}$$**Proof**: first notice that the new series has the same radius of convergence with the original one, hence sharing the same disk of convergence. To show the equality we only need to bound $|\frac{f(z_0+h)-f(z_0)}{h}-\sum na_nz^{n-1}|$ using decomposition $f(z)=S_N(z)+E_N(z)$.
	- **Higher order derivative**: by repeating the above process we can get arbitrary order of derivative.
	- As a direct consequence, $f$ is holomorphic in its disc of convergence.
- **Coefficient convergence**: for a sequence of power series with coefficients $\set{(a_n^k)_{n\in\mathbb N}}_{k\in\mathbb N}$ s.t. $$|a_n^{k}|\le|b_n|,\forall n,k\in\mathbb N\quad\text{and}\quad\lim_{k\to\infty}|a_n^k|=0,\forall n\in\mathbb N$$for a convergent $f=\sum b_nz^n$ on $D$ then $\sum a_n^kz^n\to0,k\to\infty$ uniformly on $D$.
  **Proof**: denote the circle of convergence of $f_k=\sum a_n^k z^n$ as $D_k$, then $D_k\subset D$ by modulus domination. Now pick any $\varepsilon>0$. By convergence of $f$ we can pick $N\in\mathbb N$ large s.t. $$\sum_{n=N}^\infty |a_n^k|\cdot|z|^k<\varepsilon,\quad\forall k\in\mathbb N$$Meanwhile for the finitely many terms $\sum_{n=1}^N a_n^kz^n$ by $\lim |a_n^k|=0$ we can pick $K\in\mathbb N$ large s.t. $$\sum_{n=1}^N|a_n^k|\cdot|z|^n<\varepsilon,\quad\forall k\ge K$$Combining the above two expressions we have $$\sum_{n\in\mathbb Z_+}|a_n^k|\cdot|z|^n<2\varepsilon,\quad\forall n\ge N,k\ge K$$which yields the desired result by arbitrariness of $z\in D_1$.
	- This is a partial converse to the fact that the expression of $0$ is not unique on the space of holomorphic functions. [[Basis in Hilbert Space]].
## Behavior on boundary of convergence
- **Regular point**: given $f(z)=\sum a_nz^n$ with boundary of convergence $C$, a point $w\in C$ is called regular if there exists an open neighborhood $U$ of $w$ on which a holomorphic $g$ can be defined as a continuation of $f$.
- **Examples**
	- $\ln(1-z)$ is divergent at $1$ and convergent everywhere on $\mathbb D$ by Abel's test ([[Series]]). Hence it can be used to construct function that converges on some prescribed points.
	- $\sum_{n=0}^\infty\frac{1}{n}z^{2^n}$ diverges on a dense subset of $\partial\mathbb D$.
- **Divergent point**: if $f(z)=\sum a_nz^n$ is holomorphic on an open set containing $\overline{\mathbb D}$ except for a pole $z_0$ on the unit circle, then $\lim\frac{a_n}{a_{n+1}}=z_0$.
  **Proof**: if $\limsup|\frac{a_n}{a_{n+1}}|>|z_0|$ then $f(z)$ cannot be holomorphic on open set containing $\mathbb D$; if $\liminf|\frac{a_n}{a_{n+1}}|<|z_0|$ then $f(z)$ is convergent at $z_0$. The same reasoning can be applied to $\arg\frac{a_n}{a_{n+1}}$ for convergence to $\arg z_0$.
More can be found in [[Hardy Space]]
## Product series
A complex series $$\set{p_n}:p_n=(1+u_1)\cdots(1+u_n),\quad n\in\mathbb n,u_n\in\mathbb C$$is said to converge to $p$ if $p=\lim p_n$. We'll denote $p_n^*=(1+|u_1|)\cdots(1+|u_n|)$.
- We have $$p^*_N\le e^{|u_1|+\cdots+|u_N|},\quad|p_N-1|\le p_N^*-1$$which is easy to proof by induction.
- **Uniform convergence**: for $u_n=u_n(z)$ a series of bounded functions with $\sum|u_n|$ converging uniformly, then $p_n(z)$ converges uniformly which is invariant under rearrangement $\sigma$, and $p(z_0)=0$ iff $u_n(z)=-1$ for some $n$.
  **Proof**: this is a standard result utilizing uniforming bound $\sup_z u_n(z)=c_n$ and the exponential trick $\prod(1+c_n)=\exp\left(\sum\ln(1+c_n)\right)$ to estimate the limit.
