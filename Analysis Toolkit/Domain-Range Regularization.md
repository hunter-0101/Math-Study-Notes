**Key idea**: in general for a mathematical object there are usually some theorems that can greatly decrease the range of discussion assuming condition on boundedness over a specific domain or range. However in practice the domain of object under discussion is sometimes "bad" or "irregular". In such cases we may consider to somehow regularize the domain.
## Basic tools
- **Möbius transform** ([[Complex Geometry]]): this is related to holomorphic transformation between unit disk $\mathbb D$ and upper half plane. The mostly used one is the **Cayley transform** $$\begin{align}&\mathbb D\to \mathbb R_+^2,\quad z\mapsto-i\frac{z+1}{z-1},\quad(1,-i,i)\mapsto(\infty,1,-1)\\&\mathbb R_+^2\to\mathbb D,\quad z\mapsto\frac{z-i}{z+i},\quad(\infty,1,-1)\mapsto(1,-i,i)\end{align}$$
	- **Key characteristics**: Möbius transform is useful because it's exceptionally well-behaved, say: conformal-ness, invertibility, compactification, etc..
	- **Schwarz-Christoffel Maps**: used when we're looking at domain with corners.
- **Exponentiation**: $e^x$ is entire, and has many other great properties that can be utilize to strengthen the boundedness condition:
	- **Positivity on $\mathbb R$**: basic real part version of Liouville's theorem ([[Holomorphic Function]]), 
	- **Holomorphic bijection from $-\pi<\Im z\le\pi$ to $\mathbb C\backslash\set{0}$**: this is sometimes useful, but note that this transformation is more complicated than Möbius transform, limiting its usage.
  Note that $\ln z$ is also sometimes used, with careful restriction of its single-valued domain.
- **Riemann mapping theorem ([[Complex Geometry]])**: although not constructive, it provide a conceptual guarantee of existence of homomorphism between simply connected domains.
Note that **algebraic closure under transformation** is of particular importance for this idea. The effectiveness of above tools hinges on the fact that **function class in questions is stable under composition with transformations**.
- **Order of composition**: given a transform $T$ and some object $f$, $f\circ T$ changes the domain, while $T\circ f$ changes the range.
## Domain regularization
Given $f\in\mathcal O(E)$ we would like to adjust $E$ into canonical shapes $D$. To this end we'll try to find proper $T\in\mathcal O(D)$ with $T(D)\subset E$ and set $g=f\circ T$, i.e., 
<p align="center"><img align="center" src="https://i.upmath.me/svg/%0A%5Cbegin%7Btikzcd%7D%0AD%20%5Carrow%5Br%2C%20%22T%22'%5D%20%5Carrow%5Brr%2C%20%22g%22%2C%20bend%20left%5D%20%26%20E%20%5Carrow%5Br%2C%20%22f%22'%5D%20%26%20f(E)%0A%5Cend%7Btikzcd%7D%0A"/></p>
Several examples are listed below.
- **Poisson kernel on $\mathbb R^2$ ([[Convolution]])**: we're given the Poisson kernel on $\mathbb D$, and would like to get its counterpart on $\mathbb R^2$. It's worth noting that a change in Jacobian is required. 
## Range regularization
Given $f\in\mathcal O(E)$ we would like to transform $f(E)$ into canonical shapes $F$. To this end we'll try to find proper $T\in\mathcal O(f(E))$ whose range is $F$ (usually $\mathbb {D,C,C^+}$) and set $g=T\circ f$, i.e., 
<p align="center"><img align="center" src="https://i.upmath.me/svg/%0A%5Cbegin%7Btikzcd%7D%0AE%20%5Carrow%5Br%2C%20%22f%22'%5D%20%5Carrow%5Brr%2C%20%22g%22%2C%20bend%20left%5D%20%26%20f(E)%20%5Carrow%5Br%2C%20%22T%22'%5D%20%26%20F%0A%5Cend%7Btikzcd%7D%0A" /></p>
Several examples are listed below.
- **Borel-Carathéodory theorem ([[Holomorphic Function]])**: when trying to bound $|f(z)|$ with $|\Re f|$ we use Cayley transform to send $\mathbb C_+$ to $\mathbb D_R$, for which the Schwarz's lemma can be applied to yield a bound.
- **Phragmén-Lindelöf principle**: the technique employs an auxiliary parametrized function to prove the boundedness of a holomorphic function $f$ on an unbounded domain $\Omega$ with mild conditions constraining the growth of $|f|$. The key idea is. to construct an auxiliary that vanishes at infinity, and then use the maximum modulus principle to find the supremum of $|f|$.
	- **Paley-Wiener theorem ([[Analytic Continuation]])**: an auxiliary lemma used is that when $F\in C(\overline S)\cap\mathcal O(S)$ is bounded on $\partial S$ of exponential type, then it's actually bounded on $S$.
	- **Three-lines lemma ([[Riesz Interpolation Theorem]])**: this is the strip version of the principle, with essentially the same kind of argument.