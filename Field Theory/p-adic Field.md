Given $p\in\mathbb P$ a prime ([[Division]]), the **$p$-adic field** $\mathbb Q_p$ is constructed progressively as:
- **$p$-adic integer**: the [[Ring]] of $p$-adic integers is defined as the collection of formal power series ([[Polynomial Ring]]) evaluated at $X=p$ as $$\mathbb Z_p=\Set{\sum_{i=0}^\infty a_ip^i:a_i\in\set{0,1,\cdots,p-1},\forall i}$$Note that it's different from the one in [[Modular Arithmetic]], which has the same symbol by chance.  
	- **$p$-adic unit**: the [[Group]] of units in $\mathbb Z_p$ are exactly those with non-zero first coefficient: $$\mathbb Z_p^\times=\set{x\in\mathbb Z_p:x=a_0+a_1p+\cdots,a_0\neq0}=\set{x\in\mathbb Z_p:\nu_p(x)=0}$$here the first equivalence is trivial via [[Modular Arithmetic]], and the second equality is discussed below in $p$-adic valuation.
- **$p$-adic number**: the **$p$-adic field** is defined as $$\mathbb Q_p=\Frac\mathbb Z_p=\Set{\sum_{i=k}^\infty a_ip^i:k\in\mathbb Z,a_i\in\set{0,1,\cdots,p-1},\forall i}$$which consists of all formal Laurent series. 
Note that $\mathbb Q_p$ can also be defined in many other equivalent ways, such as via equivalence classes, but they're less essential and motivational compared to the above one. The following is an illustration of $\mathbb Q_p$ via the **Bethe [[Lattice]]**:
![[Pasted image 20251218094551.png]]It is an infinite Bethe lattice of coordination $p+1$. Note that It's a fractal without intrinsic size. 
- **$p$-adic valuation**: we define a function $$\nu_p(x)=\min\set{k\in\mathbb Z:a_k\neq0},\quad\forall x\in\mathbb Q_p\backslash\set{0}$$and $\nu_p(0)=\infty$. We can verify directly that it's indeed a valuation ([[Field]]) on $\mathbb Q_p$. 
- **$p$-adic absolute value**: the absolute value induced by the valuation is defined as $$|x|_p=p^{-\nu_p(x)}$$It can be verified easily that it's an absolute value ([[Field]]), and is actually even stronger, that it satisfies the **strong triangle inequality** $$|x+y|_p\le\max(|x|_p,|y|_p)$$with equality if $|x|_p\neq|y|_p$. Therefore it's non-Archimedean.
	- **$p$-adic metric**: based on the absolute value above we define a metric on $\mathbb Q_p$ via $$d(x,y)=|x-y|_p,\quad\forall x,y\in\mathbb Q_p$$It can be verified that $(\mathbb Q_p,|\cdot|_p)$ is a complete [[Metric Space]], hence is a completion of $\mathbb Q$ that is different from [[Real Number System]] $\mathbb R$. By the strong triangle inequality above we know that it's an ultrametric. 
- **Distinction from $\mathbb R$**: while both $\mathbb Q_p$ and $\mathbb R$ ([[Real Number System]]) serves as completions ([[Metric Space]]) of $\mathbb Q$, they arise from fundamentally different metrics:
	- $\mathbb R$ is a completion of $\mathbb Q$ w.r.t the standard [[Euclidean Space]] norm, i.e., the standard Archimedean absolute value $|\cdot|_\infty$.
	- $\mathbb Q_p$ is a completion of $\mathbb Q$ w.r.t the $p$-adic absolute value $|\cdot|_p$.
  It's also quite important to distinguish their difference from a **purely algebraic perspective**, although they contains some "**shared values**" in the sense of equality in $\mathbb R$. 
## Properties
### Topological Properties
The $p$-adic absolute value defines a topology that is quite different from the Euclidean topology on $\mathbb R$.
- **Completeness:** $\mathbb Q_p$ is a **complete** field with respect to the metric $d_p(x, y) = |x-y|_p$.
- **Total Disconnectedness:** $\mathbb Q_p$ is a **totally disconnected** space. The only connected subsets are single points.
- **Compactness of $\mathbb Z_p$:** The ring of $p$-adic integers $\mathbb Z_p$ is a **compact** and **open/closed** subset of $\mathbb Q_p$. The open balls $B_r(0)=\{x \in \mathbb Q_p \mid |x|_p < r\}$ are also closed, and the closed balls $D_r(0)=\{x \in \mathbb Q_p \mid |x|_p \le r\}$ are also open.
- **$p$-adic balls**: in $p$-adic metric, any point inside a ball is its center. If two balls intersect, one must be contained in the other. Specifically, the open balls are the cosets of the ideal $(p^k)$: $$p^k \mathbb Z_p + x = \{y \in \mathbb Q_p \mid |y-x|_p \le p^{-k}\}$$
### Modular Properties (Hensel's Lemma)
Hensel's Lemma provides a crucial tool for lifting roots from the residue field $\mathbb Z/p\mathbb Z$ to $\mathbb Z_p$. It's a key reason why $\mathbb Q_p$ is often easier to work with than $\mathbb R$ in terms of solving polynomial equations.
- **Hensel's Lemma (Simple Case):** Let $f(X) \in \mathbb Z_p[X]$ be a polynomial. If there exists an element $a_0 \in \mathbb Z_p$ such that:
    1. $f(a_0) \equiv 0 \pmod{p}$
    2. $f'(a_0) \not\equiv 0 \pmod{p}$
  Then there exists a unique root $\alpha \in \mathbb Z_p$ of $f(X)$ such that $\alpha \equiv a_0 \pmod{p}$.
This means if a polynomial has a simple root modulo $p$, it has a unique $p$-adic root that can be found iteratively.
### Extra discussion
- **Square root in $\mathbb Q_p$**: The problem of determining whether an element $a \in \mathbb Q_p$ is a square ($x^2=a$) is an important application of $p$-adic analysis.
	- **Criterion for $a \in \mathbb Q_p^\times$ to be a square**: let $a = p^k u$, where $u \in \mathbb Z_p^\times$ and $k \in \mathbb Z$. Then $a$ is a square in $\mathbb Q_p$ if and only if:
	    1. $k$ is even (i.e., $\nu_p(a)$ is even), **AND**
	    2. $u \equiv y^2 \pmod{4p}$ for some $y \in \mathbb Z$, for $p=2$, OR
	    3. $u$ is a quadratic residue modulo $p$, for $p \neq 2$.
- **Geometric series**: by completeness of $\mathbb Q_p$ we know (by [[Banach Space]]) that $$|r|_p<1\imply\sum_{n\in\mathbb N}r^n\text{ converges}$$and due to the difference in behavior between $|\cdot|_p$ and $|\cdot|_\infty$, some geometric series that diverges in $(\mathbb R,|\cdot|_\infty)$ would converge in $(\mathbb Q_p,|\cdot|_p)$. For instance, in $\mathbb Q_3$ we have that $$\sum_{n\in\mathbb N}3^n=\frac{1}{1-3}=-\frac{1}{2}$$This provides an interesting illustrative example of how the measure of magnitude differs between these two metrics. 