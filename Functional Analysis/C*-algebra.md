**Origin of name**: initially $B^*$-algebra is introduced to describe Banach algebra with involution satisfying $\|tt^*\|=\|t\|^2,\forall t\in\Gamma$, and it's later found that this $B^*$-condition is actually equivalent to the $C^*$-condition. At time passes the term $B^*$-algebra is rarely used in current terminology, and has been replaced by $C^*$-algebra.

---
An **involution** on a [[Banach Algebra]] $\Gamma$ is a map $*:\Gamma\to\Gamma$ satisfying:
- **Conjugate linearity**: $(\alpha s+\beta t)^*=\overline\alpha s^*+\overline\beta t^*$.
- **Anti-multiplicative**: $(st)^*=t^*s^*$.
- **Self-involution**: $t^{**}=t$.
We call $t^*$ the **adjoint** of $t$, and if further satisfies the **$C^*$-condition** $\|t^*t\|=\|t\|^2$ we call the pair $(\Gamma,*)$ a **$C^*$-algebra**. 
- **Basic properties of involution**
	- **Norm of involution**: $\|t\|=\|t^*\|,\forall t\in\Gamma$, since by sub-multiplicativity we have $\|t^*\|\ge\|t\|$, while self-involutivity yields the other half.
	- **Topological property**: $t\mapsto t^*$ is homeomorphic ([[Topological Space]]) with $0^*=0,e^*=e$.
	  **Proof**: $t$ is bijective by self-involution, and isometric by the first property, hence is a homeomorphism. The rest two follows from anti-multiplicativity and uniqueness ([[Ring]]).
	- **Inverse**: $t\in\Gamma^\times\iff t^*\in\Gamma^\times$, with $(t^*)^{-1}=(t^{-1})^*$, which follows from anti-multiplicativity.
	- **Spectrum**: $\sigma(t^*)=\set{\overline\alpha:\alpha\in\sigma(t)}$, since $$\alpha\in\sigma(t)\iff\alpha e-t\in\Gamma^\times\iff\overline\alpha e-t^*\in\Gamma^\times\iff\overline\alpha\in\sigma(t^*)$$by the last property.
## Special types of elements
- **Normal**: $t$ is normal if $t^*t=tt^*$.
- **Self-adjoint**: $t$ is self-adjoint if $t^*=t$.
	- **Spectral radius**: $r(t)=\|t\|$ for $t$ self-adjoint, since $\|t^2\|=\|t^*t\|=\|t\|^2$ and inductively we can show that $\|t^{2^n}\|=\|t\|^{2^n}$, for which the [[Spectrum]] radius formula can be applied.
	- **Spectrum**: $\sigma(t)\subset\mathbb R$ for $t$ self-adjoint.
	  **Proof**: consider $f(t)=e^{it}$ defined by [[Holomorphic Functional Calculus]]. We have $$(f(t))^*=(\exp(it))^*=\left(\sum_{n\in\mathbb N}\frac{(it)^n}{n!}\right)^*=\sum_{n\in\mathbb N}\left(\frac{(-it)^n}{n!}\right)^*=\exp(-it)=(f(t))^{-1}$$Hence by the spectral mapping theorem and the result for unitary element we have $$f\circ\sigma(t)=\sigma\circ f(t)\subset\set{|z|=1}$$which implies $\sigma(t)\subset\mathbb R$.
- **Unitary**: $t$ is unitary if $t\in\Gamma^\times,t^{-1}=t^*$, which is equivalent to $t^*t=tt^*=e$.
	- **Norm of unitary element**: $1=\|e\|=\|t^*t\|=\|t\|^2$ implies $\|t\|=1$.
	- **Spectrum**: $\sigma(t)\subset\set{|z|=1}$ for $t$ unitary. 
	  **Proof**: for $\alpha\in\sigma(t)$, by spectral mapping ([[Holomorphic Functional Calculus]]) we have $$\sigma(t^*)=\sigma(t^{-1})=\sigma(t)^{-1}\quad\Longrightarrow\quad\begin{cases}|1/\alpha|\le\|t^*\|=1\\|\alpha|\le\|t\|=1\end{cases}$$which implies $|\alpha|=1$.
## $C^*$-subalgebra
A subalgebra $\Pi\subset\Gamma$ with $t^*\in\Pi,\forall t\in\Pi$ is referred to as a **$C^*$-subalgebra**.
- **Independence of spectrum**: given closed $\Pi\subset\Gamma$ with $\set{e,t}\subset\Pi$, we have $\sigma(t,\Pi)=\sigma(t,\Gamma)$.