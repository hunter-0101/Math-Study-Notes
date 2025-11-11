**Holomorphic function**: For a function $f$ on $X\subset\mathbb{C}$, we say that it's holomorphic at $x_0$ if $$f'(z_0)=\lim_{z\to z_0}\frac{f(z)-f(z_0)}{z-z_0}$$exists and denote it as $f'(z_0)$, the **derivative** of $f$ at $z_0$. A function that is holomorphic at every point on its domain is said to be holomorphic. Set of functions holomorphic on $\Omega$ is usually denoted as $\mathcal O(\Omega)$.
- **Order**: for entire $f$ we define its order of growth by $$\rho=\limsup_{r\to\infty}\frac{\ln(\ln\|f\|_{\infty,B_r})}{\ln r}$$where $B_r=\set{z:|z|\le r}$. i.e., $\rho$ is the infimum of all $m$ such that $|f(z)|=O(\exp(|z|^m)),z\to\infty$.
	- $\rho(fg)=\max\set{\rho_f,\rho_g}$.
	- If the Taylor expansion $f(z)=\sum_{n\in\mathbb N}a_nz^n$ is given then $$\rho=\limsup_{n\to\infty}\frac{n\ln n}{-\ln|a_n|}$$The converse also holds by some estimation.
	  **Proof**: notice that by Cauchy's inequality, when $|F(z)|\le A\exp(a|z|^\rho)$ we have $$\limsup_{n\to\infty}|a_n|^{1/n}n^{1/\rho}<\infty$$simplifying this expression to get the estimation.
- **Type**: for $0<\rho<\infty$ we can further define the type as $$\sigma=\limsup_{r\to\infty}\frac{\ln\|f\|_{\infty,B_r}}{r^\rho}$$
- **Little Picard's theorem**: any entire function omitting at least two values in $\mathbb C$ is constant.
  **Proof**: if $f$ misses $c_1,c_2$, then $f-c_1$ is non-vanishing, hence $f-c_1=\exp g$, and now since $\exp g+c_1$ misses $c_2$ we know that $g$ must be constant. [[Zero of Holomorphic Function]]
## Laurent series
The Laurent series of a function $f$ holomorphic on $V=\set{z\in\mathbb C:r<|z-c|<R}$ for some $0\le r<R$ could be represented by the Laurent series$$f(z)=\sum_{n=-\infty}^\infty a_n(z-c)^n,\quad a_n=\frac{f^{(n)}(z_0)}{n!}=\frac{1}{2\pi i}\int_\gamma\frac{f(z)}{(z-c)^{n+1}}dz$$where $\gamma$ is a counterclockwise Jordan curve. Terms with non-negative/negative powers are called **regular/principal parts**.
**Proof**: choose a smaller annulus with the same center $V'=\set{z\in\mathbb C:r'<|z-c|<R'}$, and denote $\partial V'=\Gamma'+\gamma'$. Then by Cauchy's integral formula we have $$f(z)=\frac{1}{2\pi i}\int_{\Gamma'}\frac{f(\xi)d\xi}{\xi-c}-\frac{1}{2\pi i}\int_{\gamma'}\frac{f(\xi)d\xi}{\xi-c}$$The first integral expands exactly into Taylor series, while the second integral can be transformed similarly, with $(z-c)$ rather than $(\xi-c)$ factored out, to yield a geometric expansion $\sum\frac{(\xi-c)^n}{(z-c)^{n+1}}f(\xi)$. As the convergence is uniform on any compact subset (by Weierstrass test) we may exchange the integral and summation, resulting in the principal part, with expression of coefficients totally the same as the regular part in form. 
- **Intuition**: Laurent series goes one step further than the analyticity of holomorphic function ([[Complex Function]]). It takes into consideration that some function might be holomorphic only on a annulus rather than a simply connected domain, and utilize [[Cauchy Integral]] to derive a corresponding series expression.
- **Domain of convergence**: for the above expression denote $$1/R=\limsup_{n\to\infty}|a_n|^{1/n},\quad r=\limsup_{n\to\infty}|a_{-n}|^{1/n}$$then the domain of convergence is $V=\set{z\in\mathbb C:r<|z-c|<R}$, and the **convergence is absolute on $V$ and uniform on compact subset of $V$**. Note that it could happen that $r>R$, in which case $V=\varnothing$.
	- **Domain of convergence extends to the nearest singularity**: assume that the boundary of disc of convergence contains no singularity, then we may find, for each $\omega\in\partial V$, a small domain on which a new function can be defined that agrees with $f$. Since the boundary is compact, a finite sub over can be found, thus we extends the domain of convergence (by identity theorem), which is a contradiction.
	- **Cauchy inequality for Laurent series**: let holomorphic $f$ be bounded by $M$ on $\gamma_\rho$, then$$|a_n|\le\frac{M}{\rho^n},\quad n\in\mathbb Z$$its derivation is similar to the original Cauchy inequality. [[Cauchy Integral]]
- **Uniqueness**: by term-wise differentiation of [[Complex Series]] we can verify that for any identity $f(z)=\sum b_nz^n$ the coefficient must takes the above form. 
- **Relation with [[Fourier Series]]**: the Fourier series in complex form is $$\phi(x)=\sum_{n=-\infty}^\infty c_ne^{inx},\quad c_n=\frac{1}{2\pi}\int_0^{2\pi}\phi(t)e^{-int}dt$$If we set $e^{it}=z,\phi(t)=f(e^{it})=f(z)$, then the above expression is exactly the same as Laurent series. Conversely, the Laurent series of $f(z)$ on the unit circle (by fixing $r=1$ in $f(re^{i\theta})$) is the Fourier series of $f(z)=\phi(t)$ on $[0,2\pi]$. More specifically, their coefficients are connected via the [[Cauchy Integral]] by $c_n=a_nR^n$. 
## Singularities
**Isolated singularity**: a point $c\in\overline{\mathbb C}$ is an isolated singularity of $f$ if there exists a punctured neighborhood of $c$ where $f$ is holomorphic. There are three types of singularities:
- **Removable singularity**: $c$ such that $\lim_{z\to c}f(z)$ exists and is finite. $c$ is removable iff Laurent expansion of $f$ contains no principal part, justified by Cauchy's inequality. 
	- **Riemann's analytic continuation theorem**: for $D\subset\mathbb C$ open, $a\in D$, and $f$ holomorphic on $D\backslash\set{c}$, the following are equivalent:
	  1. $f$ is homomorphically/continuously extendable over $a$.
	  2. There exists a neighborhood of $a$ on which $f$ is bounded.
	  3. $\lim_{z\to c}(z-c)f(z)=0$ (this can be weakened to $|f|\le A|z-c|^{-1+\varepsilon},\varepsilon>0$).
	  **Proof**: $1\Rightarrow2\Rightarrow3$ is obvious. To show $3\Rightarrow1$ we only need to apply Cauchy's inequality ([[Cauchy Integral]]), and use the fact that analyticity $\iff$ holomorphicity. [[Complex Function]]
- **Pole**: see [[Pole of Holomorphic Function]].
- **Essential singularity**: $f$ is neither a finite or infinite limit as $z\to a$, like $e^{1/z}$ at $z=0$, illustrated by the figures below. ![[Pasted image 20250301174826.png]]
	- **Criterion by Laurent series**: $z=c$ is essential iff the Laurent expansion contains infinitely many non-zero terms. This is direct from the above two results.
		- If we perform $z\to1/z$ to the principal part, we'll get a holomorphic function on a  co-circle $C_r^C=\set{|z|>r}$. Then Weierstrass theorem below shows that such function attains range dense in $\mathbb C$. 
	- **Casorati-Weierstrass theorem**: if $c$ is an essential singularity of $f$ and $U$ is a neighborhood of $c$, then $f(U\backslash\set{c})$ is dense in $\overline{\mathbb C}$.
	  **Proof**: if there is some $A$ with $|f(z)-A|>\epsilon$, then $g(z)=1/(f(z)-b)$ is bounded on a neighborhood of $c$, hence by Riemann's analytic continuation theorem $c$ is a removable singularity, a contradiction. 
	- **Great Picard's theorem**: on any punctured neighborhood of essential singularity $c$, $f(z)$ takes on all possible complex values infinitely often with at most one single exception.
	  **Proof**: 
Based on the above knowledge we may classify some common functions.
- **Entire function**: obviously we only need to discuss the behavior of $f$ at $\infty$:
	- **$\lim_{z\to\infty} f(z)$ exists**: by Liouville's theorem such $f$ must be constant. [[Cauchy Integral]]
	- **$\infty$ is a pole**: consider the Laurent expansion of $1/f$ we have $f$ being a polynomial.
	- **$\infty$ is an essential singularity**: we call such function as **transcendental entire function**. 
- **Meromorphic function**: a meromorphic function $f$ on $\mathbb C$ is a rational function.
  **Proof**: number of poles must be finite, otherwise there will be limit point of poles since $\overline{\mathbb C}$ is compact. Denote them as $c_k,1\le k\le n$ and let $g_k(z)=\sum_{i=1}^{N_k}a_i^{(k)}(z-c_k)^{-i}$ be the principal part of $f$ near the pole $c_k$. Also denote $g(z)=\sum_{i=1}^Na_iz^i$ the principal part of $f$ at $\infty$, then $$\phi(z)=f(z)-g(z)-\sum_{k=1}^ng_k(z)$$has no singularities in $\overline{\mathbb C}$, thus $\phi(z)=c_0$. Therefore $f(z)=\phi(z)+g(z)+\sum_{k=1}^ng_k(z)$ is rational.
	- **Corollary**: any rational function is determined up to a multiplicative constant by prescribing the locations and multiplicities of its zeros and poles.
	- **Number of poles/zeros**: notice that in a rational function finite zeros/poles correspond to a poles/zeros at $\infty$, hence their overall counts (multiplicity included) equals.
	- **Transcendental meromorphic function**: a meromorphic on $\mathbb C$ that is not rational is called a transcendental meromorphic function. 
## Real/Imaginary part
For holomorphic $f=u+iv$ on simply connected domain $D$, both $u(x,y),v(x,y)$ are [[Harmonic function]]. Note that the converse also holds ([[Harmonic function]]).
- **Borel-Carathéodory theorem**: for $f$ analytic on $\overline{D_R}$, for $r<R$ we have $$\max_{|z|=r}|f(z)|\le\frac{2r}{R-r}\max_{|z|\le R}\Re f(z)+\frac{R+r}{R-r}|f(0)|$$**Proof**: denote $A=\sup_{|z|\le R}\Re f(z)$. For $f$ non-constant first assume that $f(0)=0$, then obviously $A>0$. Since $\im f\subset\set{z:\Re z\le A}$, consider two mappings $$g:z\mapsto\frac{z}{A}-1,\quad h:z\mapsto\frac{R(z+1)}{z-1}\quad\Longrightarrow\quad h\circ g:z\mapsto\frac{Rz}{z-2A}$$then $h\circ g\circ f$ sends $0$ to $0$ and sends the half plane $\set{z:\Re z\le A}$ to $D_R$. By Schwarz's lemma we have $|Rf(z)|/|f(z)-2A|\le |z|=r$, simplified (with triangle inequality) to the desired inequality. For $f(0)\neq0$ we use translation to get the general result.
	- **Intuition**: the proof is actually generalizing the application of Schwarz's lemma from a circle to a half plane, utilizing Möbius transform to serve as a bridge between two shapes ([[Complex Geometry]]). More related on this technique can be found in [[Domain-Range Regularization]].
	- **Alternative proof**: by the following theorem we can bound $f^{(n)}(0)$, and Taylor expansion would yield the result.
	- **Shortcoming**: an obvious problem it that RHS explodes as $r\to R$, making it almost useless near the boundary. This is way weaker than Schwarz's lemma itself because, intuitively it only restricts the range into half plane, causing an under-kill in the Möbius transform. 
		- **Example**: take $z/(1+\varepsilon-z)$, which contains a complex inversion w.r.t $|z-1-\varepsilon|=1$, then obviously as $\varepsilon\searrow0$ the unit disk will be mapped to almost entire $\Re z<0$. 
		- **Partial remedy**: if $f$ is entire we can increase $R$ to arbitrarily large, which allows for some useful discussion of bounds of $|f(z)|$.
- **Cauchy's inequality for real/imaginary part**: for $f$ holomorphic on $D_{R+\varepsilon}$ for some $\varepsilon>0$ and $u\le M$ on $\partial D$, we have $$|f^{(n)}(0)|\le\frac{2n!}{R^n}(M-u(0)),\quad\forall n\ge1$$and similar for $v$. 
  **Proof**: WLOG assume $f(0)=0$, then by Cauchy integral formula $\frac{f^{(n)}(0)}{n!}=\frac{1}{2\pi}\int_0^{2\pi}\frac{f(Re^{i\theta})}{R^ne^{in\theta}}d\theta$. Also notice that $$\begin{align}&\int_0^{2\pi}f(Re^{i\theta})e^{in\theta}d\theta=\frac{1}{iR^n}\int_{C_R} f(z)z^{n-1}dz=0\\&\int_0^{2\pi}f(Re^{i\theta})d\theta=\frac{1}{i}\int_{C_R}f(z)z^{-1}dz=0\end{align}$$Pick a proper rotation $e^{-i\theta_0}f^{(n)}(0)=|f^{(n)}(0)|$, then combining the above three integrals yields $$\int_0^{2\pi} f(Re^{i\theta})(1+\cos(n\theta+\theta_0))d\theta=\frac{2\pi R^n|f^{(n)}(0)|}{2n!}$$Now the imaginary part vanishes, while $\int_0^{2\pi}(1+\cos(n\theta+\theta_0))=2\pi$, hence the result follows.
	- **Alternative proof**: instead of manually taking a rotation we could also deduce an identity for the real part only, and then perform the estimation. Notice that by Cauchy's inequality ([[Cauchy Integral]]) applied on $f(z)z^{n-1}$ we have $\int f(Re^{i\theta})e^{in\theta}d\theta=0$, and if we take a conjugate and add it into Cauchy integral formula we have $$\frac{1}{\pi R^n}\int_0^{2\pi}u(Re^{i\theta})e^{-in\theta}d\theta=\frac{f^{(n)}(0)}{n!}$$Now that $\int e^{-in\theta}=0$, we add in $M$ to dominate the real part term: $$\frac{1}{\pi R^n}\int_0^{2\pi}(M-u(Re^{i\theta}))e^{-in\theta}d\theta=-\frac{f^{(n)}(0)}{n!}$$Now triangle inequality can be applied, and by dropping $e^{-in\theta}$ term and use the mean value property of [[Harmonic function]] we get the same inequality.
## Anisotropic and isotropic
**Anisotropy** refers to the property of behaving differently along different directions. It's observed that a holomorphic function would usually behave isotropically in very small or large scale, but somehow anisotropically in intermediate scale. ![[Pasted image 20250514135444.png]]![[Pasted image 20250514135900.png]]That is, if we define a measure of anisotropy by $$\rho_f(R)=\max_{u\perp v}\left|\frac{\diam_uf(C_R)}{\diam_vf(C_R)}\right|\quad\text{where}\quad \diam_uf(\Omega)=\diam f(\Omega\cap \set{ru}),r\in\mathbb R$$Then we can notice that $\rho_f(R)$ is close to $1$ for very small/large $R$, but is relatively large for intermediate $R$.
- **Intuition**: consider $f(z)=\sum a_nz^n$. 
  - **$R$ small**: a holomorphic function is locally conformal, hence we have $\rho_f(R)\to1,R\to0$.
  - **$R$ intermediate**: in this stage lower-degree terms interfere with dominant higher-degree terms, causing a distortion.
  - **$R$ large**: higher-degree terms dominates at large $R$, and their rotationally symmetry makes $\rho_f(R)\to1$ again.
Code: 
```mathematica
ParametricPlot[ReIm[Exp[100*(Cos[t] + I*Sin[t])]], {t, 0, 2*Pi}, 
 PlotRange -> All] 

f[z_] := z + z^2 - z^4;
GraphicsGrid[{Table[
 ParametricPlot[
    ReIm[f[r * Exp[I t]]], {t, 0, 2 Pi}, PlotRange -> All], 
   {r, {0.25, 0.5, 1, 2}}]}]
```