Given $\alpha\in\mathbb R$, a **good Diophantine approximation** of $\alpha$ is defined as $p/q\in\mathbb Q$ s.t. $$\abs{a-\frac{p}{q}}<\abs{a-\frac{p'}{q'}}, \quad\forall 0<q'\le q,p,p'\in\mathbb Z$$similarly, a **best Diophantine approximation** is defined to satisfy $$|q\alpha-p|<|q'\alpha-p'|,\quad\forall 0<q'\le q$$note that any best Diophantine approximation is a good one, but not vise versa.
- **Continued fraction representation**: any rational number has a finite continued fraction representation, and any irrational number has a infinite continued fraction representation. This defines a **bijective** mapping between real number and continued fractions.
	- **Quadratic irrationals** have periodic continued fraction expansion.
- **Best approximation theorem**: every best approximation of a real number is a convergent of its simple continued fraction expansion and conversely, each of the convergent $c_1,\cdots,c_n$ is a best approximation.
	- Note that the convergent is the $n$-th term of the infinite continued fraction $c=[a_0;a_1,a_2,\cdots]$. That is, $c_n=[a_0;a_1,\cdots,a_n]$.
	- A **badly approximable number** is an $x$ for which there is a positive constant $c$ such that for all rational $p/q$ we have $$\abs{x-\frac{p}{q}}>\frac{c}{q^2}$$The badly approximable numbers are precisely those with **bounded partial quotients**. That is, all $x=[a_0;a_1,\cdots]$ such that there exists an $M$, $a_k\le M,\forall k$.
## Irrationality criterion
Given $\alpha\in\mathbb R$ the following conditions are equivalent:
1. $\alpha\notin\mathbb Q$.
2. For any $\varepsilon>0$ there exists $p/q\in\mathbb Q$ s.t. $0<\abs{\alpha-\frac{p}{q}}<\frac{\varepsilon}{q}$.
3. For any $Q\in\mathbb R_{>1}$ there exists $p,q\in\mathbb Z,1\le q<Q$ s.t. $0<\abs{\alpha-\frac{p}{q}}<\frac{1}{qQ}$.
4. There exists infinitely may $p/q\in\mathbb Q$ s.t. $0<\abs{\alpha-\frac{p}{q}}<\frac{1}{q^2}$.
**Proof**: $3\Rightarrow4\Rightarrow2\Rightarrow1$ are obvious, hence it suffices to show $1\Rightarrow3$, which is also referred to as the **Dirichlet's approximation theorem**. Notice that $$\abs{\alpha-\frac{p}{a}}<\frac{1}{qQ}\quad\iff\quad\abs{q\alpha-p}<\frac{1}{Q}$$By considering optimal $p$ for each $1\le q<Q$ the result follows from the Pigeon hall principle.
- **Approximation of rational numbers**: notice that for any $\alpha\in\mathbb Q$ there exists $c=c(\alpha)$ s.t. $$\abs{\alpha-\frac{p}{q}}\ge\frac{c}{q},\quad\forall p,q\in\mathbb Z,\alpha\neq\frac{p}{q}$$We can take, e.g., $c(\alpha)=1/b$ for $\alpha=a/b,a,b\in\mathbb Z$.
- **Extension to Gaussian number**: consider $\mathbb Q(i)=\set{a+bi:a,b\in\mathbb Q}$, then the following are equivalent:
  1. $\alpha\notin\mathbb Q(i)$.
  2. For any $\varepsilon>0$ there exists $p/q\in\mathbb Q(i)$ s.t. $0<\abs{\alpha-\frac{p}{q}}<\frac{\varepsilon}{q}$.
  3. For any $N\in\mathbb Z_{\ge1}$ there exists $q\in\mathbb Z,1\le q<N^2$ and $p\in\mathbb Z(i)$ s.t. $)<\abs{\alpha-\frac{p}{q}}<\frac{\sqrt2}{qN}$.
  4. There are infinitely many $p/q\in\mathbb Q(i)$ s.t. $\abs{\alpha-\frac{p}{q}}<\frac{\sqrt2}{q^{3/2}}$.
  The proof is essentially the same.
### Lower bounds for Diophantine approximations
- **Liouville's theorem**: if $x$ is an irrational algebraic number of degree $n$ over rational numbers, then there exists a constant $c(x)>0$ such that $$\abs{x-\frac{p}{q}}>\frac{c(x)}{q^n},\quad\forall p,q\in Z$$
	- Following this result, we have the first transcendental number, the Liouville constant $$\sum_{j=1}^\infty 10^{-j!}$$
- **Thue-Siegel-Roth theorem**: for any irrational algebraic number $x$ and $\varepsilon>0$, there exists a positive real number $c(x,\varepsilon)$ such that $$\abs{x-\frac{p}{q}}>\frac{c(x,\varepsilon)}{q^{2+\varepsilon}}$$