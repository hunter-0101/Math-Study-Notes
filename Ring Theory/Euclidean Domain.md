An [[Integral Domain]] $R$ is called a **Euclidean domain** if it admits a map $\delta:R-\set{0}\to\mathbb N$ s.t. **Euclidean division** in $R$ is possible: given any $f,g\in R,g\neq0$ there exists $q,r\in R$ s.t. $$f=qg+r\quad\text{where}\quad \delta(r)<\delta(g)\text{ or }r=0$$the map $\delta$ is called the **Euclidean function** of $R$.
- **PID structure**: every Euclidean domain is a PID ([[Ideal]]).
  **Proof**: pick any $\mathfrak a\subset R$, then by definition we can pick $a\in\mathfrak a$ s.t. $\delta(a)$ is minimal across $\mathfrak a-\set{0}$. Now we can easily verify that $\mathfrak a=(a)$. 
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