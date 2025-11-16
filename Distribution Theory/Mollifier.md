A **mollifier** is a smooth function $\varphi\in C_c^\infty(\mathbb R^n)$ with $\varphi_\varepsilon(x)=\varepsilon^{-n}\varphi(\varepsilon^{-1}x),\varepsilon\in\mathbb R_{>0}$ satisfying $$\int_{\mathbb R^n}\varphi=1,\quad\lim_{\varepsilon\to0}\varphi_\varepsilon=\delta$$A mollifier is **positive** if $\varphi\ge0$, and is **symmetric** if $\varphi(x)=\mu(|x|)$ for some $\mu\in C_c^\infty(\mathbb R^+)$.
- **Standard mollifier**: define $\eta\in C_c^\infty(\mathbb R^n)$ by $$\eta(x)=\begin{cases}C\exp\left(\dfrac{1}{|x|^2-1}\right),&|x|<1\\0,&|x|\ge1\end{cases}$$It can be verified directly that $\eta$ is a mollifier supported on $\overline{B(0,1)}$. 
- **Mollification**: given $f:U\to\mathbb R$ locally integrable, define its mollification as $f_\varepsilon=f*\eta_\varepsilon$ on the domain $U_\varepsilon=\set{x\in U:d(x,\partial U)>\varepsilon}$, then by [[Convolution#Good kernel]] we have that 
  1. $f_\varepsilon\in C^\infty(U_\varepsilon)$.
  2. $f_\varepsilon\xto\ae f,\varepsilon\to0$.
  3. For $f\in C(U)$ the convergence is uniform.
  4. For $f\in L^p_{loc}(U),1\le p<\infty$ we have $f_\varepsilon\xto{L^p_{loc}}f$.