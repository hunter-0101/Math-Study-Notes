**Motivation**: to solve $y'+y=f(t)$ we may write it with the differential operator $D$ as $$(D+1)y=f(t)\Rightarrow y=(D+1)^{-1}f(t)$$with the integrating factor $e^t$ we have $(e^ty)'=e^tf(t)\Rightarrow y=e^{-1}\int e^tf(t)dt$. Similarly, to solve $y''-y=f(t)$ we may rewrite it as $$(D^2-1)y=f(t)\Rightarrow y=(D^2-1)^{-1}f(t)$$if we somehow "break" the denominator and write $\frac{1}{D^2-1}=\frac{1}{2}(\frac{1}{D-1}-\frac{1}{D+1})$, then similar expressions can be obtained, and (surprisingly) it's the correct solution to the DE. All these observations motivates a formal theory of operational calculus that proved to be consistent by the analysis of the Laplace transform.

---
For a given function $f(t)$, its Laplace transform $F(s)$ is defined as:$$ \mathcal{L}[f(t)] = F(s) = \int_0^{\infty} e^{-st}f(t)dt,\quad s\in\mathbb C,\Re s>\limsup_{t\to\infty}\frac{\ln|f(t)|}{t}$$This can be seen as a conversion from time domain (differential equation) to frequency domain (algebraic equation).
- **Existence & uniqueness**: for a piecewise continuous function $f$, the Laplace transform $\mathcal{L}\set{f(t)}=F(s)$ exists for $\Re s$ greater than the above limit, and if $F(s)=G(s),\forall s\in\mathbb R,s>C$ for some $C$ constant, then $f(t)=g(t),\forall t>0$.
- **Inversion formula**: if we write $s=\sigma+(2\pi\xi)i$, then by [[FT on L1]] we have $$\mathcal L[f]=\int_\mathbb Rf(t)e^{-\sigma t}e^{-2\pi i\xi t}dt=\mathcal F[f(t)e^{-\sigma t}]$$Assume that Fourier inversion formula can be applied, then $$f(t)=e^{\sigma t}\int_\mathbb R\tilde f(s)e^{2\pi i\xi t}d\xi=\frac{1}{2\pi i}\int_{\sigma+i\mathbb R}\tilde f(s)e^{st}ds$$Given $\tilde f$, the formula may be used to find $f$ using [[Contour Integral]].
## Properties
- **Linearity**: $\mathcal L\set{\alpha f+\beta g}(s)=\alpha\tilde f+\beta\tilde g$.
- **Shifting property**: we have $\mathcal{L}\set{e^{at}f(t)}=\tilde f(s-a)$.
- $\mathcal L\set{f(at)}(s)=\frac{1}{a}\tilde f(s/a)$.
- **Delaying property**: $\mathcal L\set{f(t-a)}(s)=e^{-as}\tilde f(s)$.
	- If we define a **unit step function** (or **Heaviside function**) as $$u_c(t)=\begin{cases}0&\text{if }t<c\\1 & \text{if } t\geq c\end{cases}$$then we have $$ \mathcal{L}\set{u_c(t)f(t - c)} = e^{-cs}F(s) $$This is actually another way of putting the shifting property.
- **Uniqueness**: if $\tilde f(s)=\tilde g(s)$ for all accepted $s$, then $f(t)=g(t)$ for all $t$ where both $f,g$ are continuous.
  **Proof**: it suffices to show that $\mathcal L f(s)=0,\forall s>s_0\Rightarrow f\equiv0$. Notice its similarity with the known $\int x^nf(x)dx=0\Rightarrow f\equiv0$ argument ([[Functional Approximation]]), we let $u=e^{-t},=s_0+n+1$ and transform the condition into $$0=\mathcal Lf(s)=\int_0^\infty f(t)e^{-nt}e^{-s_0t}e^{-t}dt=\int_0^1u^n(u^{s_0}f(-\ln u))du$$now let $h(u)=u^{s_0}f(-\ln u)$ then $h$ is piecewise continuous on $(0,1]$ and $\lim_u\to0^+h(u)=0$. Define $h(0)=0$, and apply the above argument we know that $h(u)\equiv0$, thus $f(t)\equiv0$. 
- **Transform of integral**: by changing order of integration it can be shown that $$\mathcal{L}\Set{\int_0^tf(\tau)d\tau}=\frac{1}{s}F(s)\quad\Rightarrow\quad\int_0^tf(\tau)d\tau=\mathcal{L}^{-1}\Set{\frac{1}{s}F(s)}$$This basically states that taking an integral for $f(x)$ would result in a $\frac{1}{s}$ in its Laplace transform. Thus we have $$\mathcal L\set{f'(x)}=sF(s)-f(0)$$which can also be directly verified using differentiation under the integral sign.
- Using differentiation under the integral sign we also have $$\mathcal L\set{x^nf(x)}=(-1)^n\frac{d^n}{ds^n}F(s)$$
- **Transform of convolution**: for two functions $f,g$ of exponential order, we have $$\mathcal{L}\set{(f*g)(t)}=\mathcal{L}\Set{\int_0^tf(\tau)g(t-\tau)d\tau}=\mathcal{L}\set{f(t)}\mathcal{L}\set{g(t)}$$which can be shown by basic techniques in [[Integral Calculus on Euclidean Space]]. [[Convolution]]
	- Notice that if $f\in\mathcal E_{k_1},g\in\mathcal E_{k_2}$, then $f*g\in\mathcal E_k$ for all $k>\max\set{k_1,k_2}$, which ensures that the above integral in well-defined.
	- This can be used for solving ODE in which case the solution obtained involves a known function and an unknown Laplace transform.
- **Transform of delta function**: by definition of delta function its Laplace transform is $$ \mathcal{L}\{\delta(t - c)\} = e^{-cs} $$
	- **Derivative of step function**: note that $$\mathcal{L}\set{u_c(t)}=\frac{e^{-cs}}{s}\quad\Rightarrow\quad s\mathcal{L}\set{u_c(t)}=\mathcal{L}\set{\delta(t-c)}\quad\Rightarrow\quad\frac{d}{dt}[u_c(t)]=\delta(t-c)$$Thus in some sense we can say that the derivative of functions at jump discontinuities is the delta function. Note that this can also be obtained from $\int_0^t\delta(s-c)ds=u_c(t)$. [[Special Function Gallery]]
## Solution of ODE
The Laplace transform is particularly useful for solving linear DE with constant coefficients. The general procedure involves:
1. **Taking the Laplace transform** of both sides of the differential equation.
2. Using the properties of the Laplace transform to handle derivatives $$\mathcal{L}\{f'(t)\} = sF(s) - f(0)$$
3. Solving the resulting algebraic equation for $F(s)$.
4. **Taking the inverse Laplace transform** to find $f(t)$.
Note that we can derive the Laplace transform for higher order derivatives recursively. Suppose that the functions $f,f',\cdots,f^{(n-1)}$ are continuous and $f^{(n)}$ is piecewise continuous on any interval $[0,A]$. Further suppose that the above functions are all of exponential order with the same parameters, then $$\mathcal{L}\{f^{(n)}(t)\}=s^n\mathcal{L}\{f(t)\}-s^{n-1}f(0)-\cdots-sf^{(n-2)}(0)-f^{(n-1)}(0)$$
## Z transform
Z transform is a discrete analogy of Laplace transform. Given a sequence $\set{a_n}_{n=0}^\infty$ we define $$\mathcal Z[a](z)=A(z)=\sum_{n=0}^\infty\frac{a_n}{z^n}=\sum_{n=0}^\infty a_nz^{-n}$$as its Z transform. Its domain of convergence is a co-disc $|z|>\sigma$ due to [[Complex Series]]. Also since Laurent series is unique w.r.t the function ([[Holomorphic Function]]), correspondence between a series and its Z transform is bijective.
- **Why $z^{-n}$ not $z^n$**: although two definitions are mathematically equivalent with slight very in domain of convergence (which doesn't matter that much), use $z^{-n}$ fits into the convention that the system is **causal**, i.e., the output at present is determined by input at present and before, not the future. 
- **Properties**
	- **Linearity**: $\mathcal Z[\lambda a]=\lambda\mathcal Z[a],\forall |z|>\sigma_a$, and $\mathcal Z[a+b]=\mathcal Z[a]+\mathcal Z[b],\forall |z|>\max(\sigma_a,\sigma_b)$.
	- **Scaling**: for $\lambda\in\mathbb Z$ and $b_n=\lambda^n a_n$ we have $B(z)=A(z/\lambda),\forall |z|>\lambda\sigma_a$.
	- **Dilated index**: for $k\in\mathbb N$ and $b_n=a_{n+k}$ we have $$B(z)=z^kA(z)-a_0z^k-a_1z^{k-1}-\cdots-a_{k-1}z$$Conversely, if $b_n=a_{n-k}$ and $b_n=0$ for $n<k$, then $B(z)=z^{-k}A(z)$.
	- **Scaling by index**: if $f_n=na_n$ we have $B(z)=-zA'(z),\forall |z|>\sigma_a$.
	- **Z transform of convolution**: for $c=a*b$ the discrete convolution of two sequences we have $C(z)=A(z)B(z)$. [[Convolution]]
- **Inversion formula**: by knowledge from [[Contour Integral]] we have $$a_n=\frac{1}{2\pi i}\int_{C_r}A(z)z^{n-1}dz$$where $C_r$ is a circle centering at the origin with radius $r>0$.
- **Application**: similar to how Laplace transform helps to solve ODEs, Z transform helps to solve difference equation, i.e., by multiplying a specific power of $z$ and sum over all $n\in\mathbb N$, then what's left is to solve an algebraic equation and expand the solution back to its Laurent series.
	- Note that to solve recurrence relation we can also assume its general term expressible by $z^n$, and get an equation of $z$.