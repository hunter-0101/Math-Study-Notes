**Remark**: notion of division, as well as GCD and LCM, can be generalized to any [[Ring]].

---
Given $a,b\in\mathbb Z$, by the method of repetitive subtraction there exists a unique pair $(q,r)$ s.t. $$a=qb+r,\quad q,r\in\mathbb Z,0\le r<b$$which is theoretically supported by the Archimedean property of [[Real Number System]], and can be generalized to any [[Euclidean Domain]]. When $r=0$ we say that $b$ **divides** $a$, denoted $b\mid a$.
- **Prime number**: $p\in\mathbb Z_+$ is said to be **prime** if $$\min\set{d\in\mathbb Z_+:d\mid p}=p$$the set of primes is denoted $\mathbb P$.
- **Fundamental theorem of arithmetic**: any $n\in\mathbb Z_{>1}$ can be factorized **uniquely** into $$n=\prod_{k=1}^{\omega(n)}p_k^{\nu_{p_k}(n)}\quad\text{where}\quad p_k\in\mathbb P,p_1<\cdots < p_{\omega(n)}$$here $\omega(n)$ is the **prime omega function**, and $\nu_p(n)$ is the $p$-adic valuation function. We also define a capital prisme omega function $$\Omega(n)=\sum_{k=1}^{\omega(n)}\nu_{p_k}(n)$$Proof of this theorem relies on a simple and direct induction on $n$.
	- **Generalization**: any integral domain in which the **unique factorization theorem** holds is referred to as a **UFD**. [[Integral Domain]]
- **Arithmetic property**: several basic properties of division are provided below.
	- **Division by prime**: for $a,b\in\mathbb Z,p\in\mathbb P$, we have $$p\mid ab\quad\Longrightarrow\quad p\mid a\quad\text{or}\quad p\mid b$$this is because a prime is non-decomposable.
	- **Coprime division**: given $(m,n)=1$, then we have $$m\mid a,n\mid a\quad\Longrightarrow\quad mn\mid a$$this can be verified directly from definition.
## GCD & LCM
The **greatest common divisor (GCD)** of $a_i\in\mathbb Z,1\le i\le n$ is defined as $$d=\gcd(a_1,\cdots,a_n)=(a_1,\cdots,a_n)\quad\iff\quad d=\max\set{d\in\mathbb Z_+:d\mid a_i,\forall 1\le i\le n}$$and similarly, the **least common multiple (LCM)** of $a,b\in\mathbb Z$ is defined as $$m=\lcm(a_1,\cdots,a_n)=[a_1,\cdots,a_n]\quad\iff\quad m=\min\set{m\in\mathbb Z_+:a_i\mid m,\forall 1\le i\le n}$$Note that it's possible to defined GCD and LCM in a lattice-theoretic manner using partial [[Order]] on $\mathbb Z$ defined by division. 
- **Relation between GCD and LCM**: by factorization we can easily show that $$(a,b)\cdot[a,b]=|ab|$$which is useful for calculating $[a,b]$, since most of the time $(a,b)$ can be easily obtained via Euclidean algorithm ([[Euclidean Domain]]).
- **Arithmetic property**
	- **Composite GCD/LCM**: we can verify directly from definition that $$(a_1,\cdots,a_n)=(a_1,(a_2,\cdots))\quad\text{and}\quad[a_1,\cdots,a_n]=[a_1,[a_2,\cdots]]$$here $a_i$ are allowed to be rearranged in any order. This is useful when dealing with GCD/LCM of multiple numbers. 
	- **Uniform multiples/divisions**: given $m\in\mathbb Z$ we have $$\gcd(ma,mb)=m\gcd(a,b),\quad\lcm(ma,mb)=m\lcm(a,b)$$This also applies to divisions when $m\mid\gcd(a,b)$. 
- **Coprime numbers**: $a,b\in\mathbb Z$ are said to be coprime if $(a,b)=1$.
- **Bézout's identity**: for any $a,b\in\mathbb Z$ there exists $p,q,\in\mathbb Z$ s.t. $$ap+bq=(a,b)$$this follows from the Euclidean algorithm, and can be generalized to any [[Euclidean Domain]], such as the one discussed in [[Polynomial]]. 