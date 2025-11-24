## Orthonormal basis
- **Maximal orthonormal subset**: for pre-Hilbert $\mathcal H_0$ an orthonormal subset $\{e_\lambda\}_{\lambda\in\Lambda}$ is maximal if $\langle u,e_\lambda\rangle=0,\forall\lambda\iff u=0$. Such set always exists assuming AoC ([[Set Theory]]). 
	- **Gram-Schmidt process**: this is a standardized process to obtain the orthonormal basis of a linear space. The essential idea is the vector projection:$$\mathrm{proj}_u( v)=\frac{\braket{v,u}}{\braket{u,u}}u$$and the process can be formalized as below:$$\begin{align}u_1&=v_1, & e_1&=\frac{u_1}{\|u_1\|}\\u_2 & = v_2-\operatorname{proj}_{u_1} (v_2),& e_2 & = \frac{u_2}{\|u_2\|} \\u_3 & = v_3-\operatorname{proj}_{u_1} (v_3) - \operatorname{proj}_{u_2} (v_3),&e_3 & = \frac{u_3 }{\|u_3\|} \\& \ \ \vdots & & \ \ \vdots \\u_k & = v_k - \sum_{j=1}^{k-1}\operatorname{proj}_{u_j} (v_k),&e_k & = \frac{u_k}{\|u_k\|}\end{align}$$The resulting basis is usually denoted as $\set{e_\lambda}=\mathrm{GS}(v_n)$.
- **Orthonormal basis**: for separable Hilbert space $H$ an (complete) orthonormal basis is a countable maximal orthonormal subset $\set{e_n}$. Equivalent characterizations include:
  - Finite linear combinations of $\set{e_n}$ is dense in $H$.
  - $\langle f,e_n\rangle=0,\forall n\in\mathbb N$ then $f=0$.
  - $\|f\|^2=\sum|\langle f,e_n\rangle|^2$.
  - $\sum_{n=1}^N\langle f,e_n\rangle e_n\to f$ in norm.
  The proofs are simple and straightforward.
	- **Existence**: separable $H$ always have an orthonormal basis.
	  **Proof**: by separability we can take a countable dense subset. We first pick a linear independent subset (iteratively by discarding all elements that are linearly dependent of the already chosen ones) and then use the Gram-Schmidt process.
	- **Converse**: if Hilbert space $H$ has an orthonormal basis, then $H$ is separable, since set $$S=\bigcup_{m\in\mathbb N}\Set{\sum_{n=1}^mq_ne_n:q_n\in\mathbb Q[i]}$$is countable, and dense in $H$ by the completeness of basis. Hence **separability is equivalent to having an orthonormal basis**.
	- **Non-separable Hilbert spaces**
		- $\ell^\infty(\mathbb N)$ is non-separable. To see this, notice that $d_\infty(\mathbb 1_I,\mathbb 1_J)=1$ for all $I\neq J$, thus $\set{B(e_I,\frac{1}{2}):I\subset\mathbb N}$ is an uncountably infinite collection of disjoint open balls in $\ell^\infty$. Any dense subset have to intersect with all these balls, thus is uncountable. $\ell^2(\mathbb R)$ is also non-separable since $\set{f_y(x)=\delta_{xy}:y\in\mathbb R}$ is uncountable.
		- Consider $\mathcal H_0=\span(\set{e^{i\lambda x}:\lambda\in\mathbb R})$, and denote its completion as $\mathcal H$. Then $\mathcal H$ is a Hilbert space with inner product $$\braket{f,g}=\lim_{T\to\infty}\frac{1}{2T}\int_{-T}^T f(x)\overline{g(x)}dx$$The space is non-separable since $\set{e^{i\lambda x}:\lambda\in\mathbb R}$ is pairwise orthogonal, but non-countable.
			- **Almost periodic function**: continuous $F$ is said to be almost periodic if it's a uniform limit of elements in $\mathcal H_0$. We have $\mathcal H_0\subset AP\subset\mathcal H$.
- **Parseval's identity**: for orthonormal basis of a separable Hilbert space we have the identity $$\sum_n|\langle x,e_n\rangle|^2=\|x\|^2$$Based on this we deduce the Bessel's inequality.
- **Uniqueness issue**: for orthonormal basis the representation of any vector is unique, since $0$ can only be represented by $(0)_H$, but this uniqueness may fail for non-Schauder basis:
	- $\set{x^n}_{n\in\mathbb N}$ has a dense span in $C[0,1]$, but $\sqrt x$ cannot be represented by any converging polynomial sequence (Weierstrass theorem only provide existence of uniform convergence, not converging sequence). [[Functional Approximation]]
	- For orthonormal basis $\set{e_n}_{n\ge1}$ of separable Hilbert space define $f_0=-\frac{e_1}{2},f_n=e_n-\frac{2_{n+1}}{2}$ for all $n\ge1$, then $0=\sum_{n\in\mathbb N}2^{-n}f_n$. 
	- The representation of $e^z$ in [[Complex Function]].
## Riesz basis & frame
- **Riesz basis**: a collection $\set{x_k}_k$ is a Riesz basis for Hilbert $H$ if there exists invertible linear transform $T$ and an orthonormal basis $\set{e_k}_k$ such that $x_k=Te_k,\forall k$.
	- **Biorthogonal system**: for any Riesz basis $\set{x_k}$ there is a unique set $\set{y_k}$ such that $\langle x_i,y_j\rangle=\delta_{ij}$. In such case $\set{y_k}$ is also a Riesz basis. This can be constructed using oblique projection ([[Generalized Sampling Theorem]]) or orthogonal subspace.
	- **Frame inequality**: there exists $0<A\le B<\infty$ such that $$A\|x\|^2\le\sum_k|\langle x,x_k\rangle|^2\le B\|x\|^2,\quad\forall x\in H$$We could define the **analysis operator** $T(x)=(\langle x,x_k\rangle)_k$.
	- **Criterion for Riesz basis**: $\set{x_k}$ is a Riesz basis iff it's $\omega$-independent, and there exists $0<A\le B$ such that $$A\|\alpha\|_2^2\le\left\|\sum_k\alpha_kx_k\right\|^2\le B\|\alpha\|_2^2,\quad\forall \alpha\in\ell^2$$We could define the **synthesis operator** $T^*:\set{a_k}\mapsto\sum\alpha_kx_k$.
	- **Representation**: for all $x\in H$ there is a unique $\set{\alpha_k}\in\ell^2$ such that $x=\sum\alpha_kx_k$.
- **Frame**: any collection $\set{x_k}$ satisfying the frame inequality is called a frame. When $A=B$ the frame is **tight**, and when it ceases to be a frame whenever any single element is deleted it's **exact**.
	- **Frame operator**: define $Sx=\sum\langle x,x_k\rangle x_k$, then $\set{x_k}$ is a frame iff $AI\le S\le BI$.
	- **Dual frame**: since $B^{-1}I\le S^{-1}\le A^{-1}I$, $\set{S^{-1}x_k}$ is also a frame with bounds $B^{-1},A^{-1}$, called the dual frame. Notice that $$x=S^{-1}Sx=\sum\langle s,S^{-1}x_k\rangle x_k=\sum\langle x,x_k\rangle S^{-1}x_k$$
	- **Removing element**: if $\langle x_s,S^{-1}x_s\rangle\neq1$ then $\set{s_k}_{k\neq s}$ is a frame, otherwise $\set{s_k}_{k\neq s}$ is not a complete set. Thus when $\set{x_k}$ is an exact frame, then $\set{x_k},\set{S^{-1}s_k}$ are biorthogonal.
	- Exact frame $\iff$ Riesz basis. A frame that is not a Riesz basis is called **over-complete** or **redundant**, with **redundancy factors** $A,B$ as measurement.