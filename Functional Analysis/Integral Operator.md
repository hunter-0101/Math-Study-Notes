**Motivation**: when solving PDEs we're frequently using [[FT on L1]] or [[FT on L2]] to simplify the equation into an ordinary one, and to bring it back to the original domain we need to apply $\mathcal F^{-1}$. In practice solutions of ODE are often of the form $A(x)K(x,y)$, hence by convolution theorem the original solution is of the form $A*K$, which can be simply written as an integral operator.
Let $\mathcal H=L^2(\mathbb R^d)$, define $T:\mathcal H\to\mathcal H$ by $$Tf(x)=\int_{\mathbb R^d}K(x,y)f(y)dy,\quad f\in L^2$$then $T$ is called an **integral operator**, and $K$ the associated **kernel**.
- **Schur test**: for $w$ measurable on $\mathbb R^d$ s.t. $0<w<\infty\ae$, and $K$ measurable on $\mathbb R^{2d}$ with:
  1. $\int|K(x,y)|w(y)dy\le Aw(x),\ae x\in\mathbb R^d$.
  2. $\int|K(x,y)|w(x)dx\le Bw(y),\ae y\in\mathbb R^d$.
  then the integral operator defined by $$Tf(x)=\int_{\mathbb R^d}K(x,y)f(y)dy,\quad x\in\mathbb R^d$$satisfies $\|T\|\le\sqrt{AB}$. In particular if $\|K_x\|_1\le A,\|K_y\|_1\le B,\forall x,y$ then $\|T\|\le \sqrt{AB}$.
  **Proof**: by Cauchy-Schwarz inequality we have $$\int|K(x,y)||f(y)|dy\le A^{\frac{1}{2}}w^{\frac{1}{2}}(x)\left(\int|K(x,y)||f(y)|^2w^{-1}(y)dy\right)^{1/2}$$we can verify using Tonelli's theorem that $\|T\|\le\sqrt{AB}$.
	- This can be seen as a generalization of the property of $2$-norm of [[Matrix]]. 
- **Identity operator**: $I$ on $L^2(\mathbb R^d)$ cannot be expressed as an (absolutely) convergent integral operator. Otherwise there exists $K(x,y)$ measurable on $\mathbb R^d\times\mathbb R^d$ s.t. $$\int K(x,y)f(y)dy\to f(x)\ae x,\quad\forall f\in L^2$$Take $f=\chi_{B_1}$ for any ball $B_1$ and consider any ball $B_2$ disjoint from $B_1$, then we know that $K(x,y)=0\ae \in B_1\times B_2$, hence $K=0\ae$, a contradiction.
## Hilbert-Schmidt integral operator
All integral operator $T$ with kernel $K$ satisfying $K\in L^2(\mathbb R^d\times\mathbb R^d)$ is called a Hilbert-Schmidt integral operator.
- **Norm**: $\|T\|\le\|K\|_2$.
  **Proof**: by Fubini's theorem for $\ae x$ the function $y\mapsto |K(x,y)|^2$ is integrable, hence by Cauchy-Schwarz inequality $y\mapsto K(x,y)f(y)$ is integrable for $\ae x$. Further by C-S inequality we have $\|Tf\|_2^2\le\|K\|_2^2\|f\|_2^2$, hence $\|T\|\le\|K\|_2$.
- Kernel of $T^*$ is $\overline{K(y,x)}$ by Fubini's theorem.
- **Compactness**: the compact follows directly from the fact that $T$ is an Hilbert-Schmidt operator, considering the expansion of $K(x,y)$ under the basis $\set{\phi_{kj}(x,y)=\phi_k(x)\phi_j(y)}$ where $\phi_k$ is any orthonormal basis of $L^2$. [[Operator on Hilbert Space]]