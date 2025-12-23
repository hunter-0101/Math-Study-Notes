## Path
A **path** in topological space ([[Topological Space]]) $X$ is a map $f\in C(I,X)$ where $I=[0,1]$. A **homotopy** of paths in $X$ is a family of functions $f_t:I\to X,t\in[0,1]$ satisfying: 
1. $f_t(0)=x_0,f_t(1)=x_1,\forall t\in[0,1]$.
2. The associated map $F:I\times I\to X$ defined by $F(s,t)=f_t(s)$ is continuous.
When paths $f_0,f_1$ are connected in this way by a homotopy $f_t$ we say that they're **homotopic**, denoted $f_0\simeq f_1$. Notice that this is obviously an equivalence relation ([[Set Theory]]), and we refer to the equivalence class as **homotopy class**.
- **Composition (product) path**: given two paths $f,g:I\to X$ with $f(1)=g(0)$ define $$f\cdot g(s)=\begin{cases}f(2s),&0\le s\le1/2\\g(2s-1),&1/2\le s\le1\end{cases}$$as their composition, which traverses first $f$ and then $g$.
	- **Homotopy under composition**: obviously we have $$f_0\simeq f_1,g_0\simeq g_1\quad\Longrightarrow\quad f_0\cdot g_0\simeq f_1\cdot g_1$$It suffices to attack the corresponding homotopy together.
- **Basepoint**: for a **loop** $f(0)=f(1)$ we define $f(0)$ as the basepoint. The set of all homotopy classes $[f]$ of loops $f:I\to X$ at the basepoint $x_0$ is denoted $\pi_1(X,x_0)$.
### Fundamental group
$\pi_1(X,x_0)$ defined above forms a [[Group]] under composition (re-parametrization for associativity), which is referred to as the **fundamental group** of $X$ at the basepoint $x_0$.
- **Change of basepoint**: given a path $h$ connecting $x_0,x_1\in X$ we have the isomorphism $$\beta_h:\pi_1(X,x_1)\to\pi_1(X,x_0),\quad [f]\mapsto[hfh^{-1}]$$**Proof**: $\beta_h$ is obviously well-defined, and is a homomorphism because $$\beta_h[fg]=[hfg h^{-1}]=[(hfh^{-1})(hgh^{-1})]=\beta_h[f]\beta_h[g]$$Further it's an isomorphism with inverse map $\beta_{h^{-1}}$ because $$\beta_h\beta_{h^{-1}}[f]=[hh^{-1}fhh^{-1}]=[f]\quad\Longrightarrow\quad\beta_h\beta_{h^{-1}}=\id$$and similarly we have $\beta_{h^{-1}}\beta_h=\id$. 
	- **Corollary**: for a path-connected space the fundamental group is independent of choice of basepoint. In such case the fundamental group is usually abbreviated as $\pi_1(X)$.
- **Simply-connected space**: space $X$ is called simply-connected if it's path-connected and has trivial fundamental group. This condition holds iff there is a unique homotopy class of paths connecting any two points in $X$.
  **Proof**: $\Leftarrow$ is obvious, while $\Rightarrow$ follows from the lemma above.
- **Examples**
	- **Circle**: we have the isomorphism ([[Group Homomorphism]]) $$\Phi:\mathbb Z\to\pi_1(S^1),\quad n\mapsto[\omega_n(s)]=[(\cos2\pi ns,\sin2\pi ns)]$$**Proof**: obviously $\Phi$ is a homomorphism, and is surjective by counting the winding number ([[Geometry of Holomorphic Function]]). For injectivity assume that $\Phi(m)=\Phi(n)$, then there exists a homotopy $f_t$ with $f_0=\Phi(m),f_1=\Phi(n)$. Since winding number is invariant under homotopy we have $\Phi(m)\cong\phi(n)$, hence belonging to the same homotopy class.