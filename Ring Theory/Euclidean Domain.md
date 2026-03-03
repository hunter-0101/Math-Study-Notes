An [[Integral Domain]] $R$ is called a **Euclidean domain** if it admits a map $\delta:R\setminus\set{0}\to\mathbb N$, called the **Euclidean valuation (function)**, satisfying two conditions:
1. **Euclidean division**: given any $a,b\in R,b\neq0$ there exists $q,r\in R$ s.t. $$b=qa+r\quad\text{where}\quad \delta(r)<\delta(a)\text{ or }r=0$$Here $b$ is the **dividend**, while $a$ is the **divisor**. When there are multiple Euclidean valuations we specify one of them by saying "Euclidean division w.r.t. $\delta$". 
2. **Multiplicative monotonicity**: we have $$\delta(a)\le\delta(ab),\quad\forall a,b\in R\setminus\set{0}$$This condition ensures compatibility of the valuation with division. 
A Euclidean domain can be seen as a generalization to our familiar set of integers $\mathbb Z$. 
- **Alternative definition**: some books define Euclidean domain using only condition 1. This is acceptable since on any such integral domain $(R,\delta)$ we can alway set $$\overline\delta(a)=\min_{b\neq0}\delta(ab)$$which satisfies condition 2, and makes $\paren{R,\overline\delta}$ also an Euclidean domain. 
  **Proof**: to begin with, $\overline\delta$ satisfies condition 2 because $$\overline\delta(ab)=\min_{c\neq0}\delta(abc)\le\min_{d\neq 0}\delta(ad)=\overline\delta(a)$$For Euclidean division w.r.t. $\overline\delta$, for any $a,b\in R,b\neq0$ we set $\overline\delta(b)=\delta(bc)$ and consider the Euclidean division by $bc$:$$a=q_c(bc)+r\where r=0\text{ or }\delta(r)<\delta(bc)$$Set $q=cq_c$, then we have $a=qb+r$, with the Euclidean valuation of $r$ given by $$\overline\delta(r)\le\delta(r)\le\delta(bc)=\overline\delta(b)$$Therefore we indeed have a valid Euclidean division. 
	- **Discussion**: the main rationale behind this alternative definition is that, while these two definitions characterizes the same set of integral domains, condition 2 is not particularly relevant in proving the two crucial theorems about Euclidean domain: 1). Euclidean domain is PID. 2). Euclidean algorithm terminates after finitely many steps. 
	- **Reference**: more about this can be found in this [note](https://kconrad.math.uconn.edu/blurbs/ringtheory/euclideanrk.pdf)
## Properties
- **PID structure**: every Euclidean domain is a [[Principal Ideal Domain]].
  **Proof**: pick any $\mathfrak a\subset R$, then by definition we can pick $a\in\mathfrak a$ s.t. $\delta(a)$ is minimal across $\mathfrak a-\set{0}$. Now we can easily verify that $\mathfrak a=(a)$. 
	- **Intuition**: the existence of division algorithm allows us to view the ideal generation process as a "descent". For any $I\in\Id F[X]$ we can pick the non-zero element of minimal degree. 
## Euclidean algorithm
The standard Euclidean algorithm takes the following procedure:
```python
def gcd(a, b)
	while b != 0
		t := b
		b := a mod b
		a := t
	return a
```
The returned number is the GCD of inputs.
- **Extended Euclidean algorithm**: not only the remainders $r_k(0\le k\le n+1)$, but also the quotients $q_k(1\le k\le n)$ are stored in Euclidean division. It keeps two sequences $s_k,t_k$ as $$\begin{align}&s_0=1,s_1=0,& s_{k+1}=s_{k-1}-q_ks_k\\&t_0=0,t_1=1,&t_{k+1}=t_{k-1}-q_kt_k\end{align}$$The computation stops when $r_{k+1}=0$, indicating that $r_k=(a,b)$. Now by traversing back we have the **Bézout's identity** $(a,b)=s_ka+t_kb$, and further $s_{k+1}=\pm\frac{b}{(a,b)},t_{k+1}=\pm\frac{1}{(a,b)}$.
  **Proof**: notice the following relations $$A_k=\begin{pmatrix}s_{k-1}&s_k\\t_{k-1}&t_k\end{pmatrix}\qquad A_{k+1}=A_k\cdot\begin{pmatrix}0&1\\1&-q_k\end{pmatrix}$$We have that $|A_k|=(-1)^{k+1}$. Perform $A_k$ on $(a,b)^T$ would yields the GCD, proving the results.
	- Generalization of Bézout's identity can be found in [[Ideal]]. 
- **Number of steps**: denoting $T(a,b)$ the number of steps taken in the algorithm, then $T$ is invariant under multiplication of both elements.
	- Given $N\in\mathbb N$, then the smallest value for the worst case is $F_{N+2},F_{N+1}$ the Fibonacci numbers, shown by induction.
- **Least absolute remainder**: replace the requirement $0\le r_{k+1}<|r_k|$ with $|r_{k+1}|\le|r_{k-1}|/2$, i.e., choose the remainder with least absolute value, and work with $|r_{k+1}|$ in the next step. The number of steps taken by this is smaller than the standard Euclidean algorithm by exactly the numbers that negative remainders appears.