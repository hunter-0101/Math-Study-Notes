**Motivation**: [[Jordan Normal Form]] provides a universal mechanism for spectral decomposition of a finite dimensional [[Matrix]]. When we move from finite-dimensional space to general vector space like [[Topological Vector Space]] or [[Banach Space]], similar result can also be established for compact operators. Compactness is necessary so that the overall dynamic of the operator is not too pathological. 

**Remark**: this note is incomplete. 

---
**Riesz-Schauder theorem**: take $T \in \mathcal{K}(V)$ where $V$ is a infinite dimensional [[Banach Space]], then $$\dim \ker(\lambda I-T) =\codim \im(\lambda I-T) < \infty,\quad\forall\lambda\in\mathbb C\backslash\set{0}$$with both of them being a closed subspace of $V$. Moreover, the [[Spectrum]] $\sigma(T)$ is at most countable ([[Cardinality]]), has no limit point ([[Metric Space]]) except possibly $0$, and any element $\lambda \in \sigma(T) \backslash\set{0}$ is an eigenvalue of finite algebraic multiplicity. 
**Proof**: the proof proceeds following several progressive steps. 
1. **Finite dimensionality**: if $\ker(\lambda I-T)$ were infinite-dimensional, the unit ball in $\ker(\lambda I-T)$ would be compact, contradicting the corollary of Riesz’s lemma ([[Normed Vector Space]]). 
2. **Closedness of image**: pick a sequence $v_n\in V$ s.t. $$(\lambda I-T)v_n=\lambda v_n-Tv_n\to u,\quad n\to\infty$$If $\set{v_{n_k}}_{k\in\mathbb N}\subset\set{v_n}_{n\in\mathbb N}$ is a bounded subset, then by compactness we have $$Tv_{n_k}\to u'\imply \lambda v_{n_k}\to u+u'$$Hence we can conclude closedness of $\im(\lambda I-T)$ by applying the continuous $\lambda I-T$ on both sides. If otherwise $\set{v_n}_{n\in\mathbb N}$ does not admit a bounded subset, then we can pick an unbounded subset $\|v_{n_k}\|\to\infty,k\to\infty$. After normalization $\hat v_{n_k}=\frac{v_{n_k}}{\|v_{n_k}\|}$ we have $$\lambda\hat v_{n_k}-T\hat v_{n_k}\to\frac{u}{\|v_{n_k}\|}\to0$$Now $\set{\hat v_{n_k}}_{k\in\mathbb N}$ is bounded, hence we can repeat the above argument to pick a limit point $$v=\lim_{l\to\infty}T\hat v_{n_{k_l}}=\lim_{l\to\infty}\lambda\hat v_{n_{k_l}}\imply v\in\ker(\lambda I-T)$$By restricting to $T|_{V/\ker(\lambda I-T)}$ the above construction contradicts injectivity of the restricted operator, hence completing the proof. 
	- Closedness of kernel is trivial by continuity, which is equivalent to boundedness ([[Normed Vector Space]]), which is implied by compactness.
- The Ascent and Descent: Similar to the JNF proof, we define the sequences of kernels and ranges:
    
    $$\mathcal{N}_n = \ker(\lambda I-T)^n, \quad \mathcal{R}_n = \mathcal{R}(\lambda I-T)^n$$
    
    - **Ascent**: $\mathcal{N}_1 \subset \mathcal{N}_2 \subset \dots$. Compactness implies there exists a finite index $p$ (the **ascent**) such that $\mathcal{N}_p = \mathcal{N}_{p+1}$.
        
    - **Descent**: $\mathcal{R}_1 \supset \mathcal{R}_2 \supset \dots$. Similarly, there exists an index $q$ (the **descent**) such that $\mathcal{R}_q = \mathcal{R}_{q+1}$.
        
- Stability: One proves $p = q$. For this index $p$, we obtain the invariant subspace decomposition:
    
    $$X = \ker(\lambda I-T)^p \oplus \mathcal{R}(\lambda I-T)^p$$
    
    where $\ker(\lambda I-T)^p$ is finite-dimensional. This matches the decomposition $F^n = \ker(\lambda_i I - A)^{m_i} \oplus \im(\lambda_i I - A)^{m_i}$ used to derive the JNF.
## Corollaries & actionable tools

### 1. The Fredholm Alternative

For $K \in \mathcal{K}(X)$ and $\lambda \neq 0$, the equation $(\lambda I - K)x = f$ satisfies:

- Either it has a unique solution for every $f \in X$ (if $\ker(\lambda I - K) = \{0\}$).
    
- Or the homogeneous equation $(\lambda I - K)x = 0$ has $n > 0$ linearly independent solutions. In this case, the inhomogeneous equation has a solution iff $f \in \ker(\lambda I^* - K^*)^\perp$.
    

### 2. Dimension and Index Relations

- Index Zero: For $T = \lambda I - K$, the Fredholm index is always zero:
    
    $$\text{ind}(\lambda I-T) = \dim \ker(\lambda I-T) - \text{codim} \mathcal{R}(\lambda I-T) = 0$$
    
- **Duality**: $\dim \ker(\lambda I - K) = \dim \ker(\lambda I^* - K^*)$.
    

### 3. Practical Tool: The Approximation Lemma

If $K$ is a limit of finite-rank operators $K_n$ (e.g., in Hilbert spaces or Banach spaces with the approximation property), then the spectral analysis of $K$ reduces to the JNF of $K_n$ for large $n$. This allows solving infinite-dimensional problems by truncating to $n \times n$ matrices.

---

## Illustrative Examples
### Example 1: Fredholm Integral Equations
Consider the operator $K: C[0,1] \to C[0,1]$ defined by $(Kf)(x) = \int_0^1 \mathcal{k}(x,y)f(y)dy$.
- **Insight**: If $\mathcal{k}(x,y)$ is continuous, $K$ is compact. Riesz-Schauder tells us that the equation $f(x) - \mu \int_0^1 \mathcal{k}(x,y)f(y)dy = g(x)$ behaves like a matrix equation $Ax=b$.
- **Application**: If the only solution for $g=0$ is $f=0$, we are guaranteed a unique solution for any $g$. This converts a difficult existence problem in functional analysis into a search for eigenvalues.
### Example 2: Diagonal Operators in $\ell^p$
Consider $K: \ell^2 \to \ell^2$ defined by $K(e_n) = \frac{1}{n}e_n$, where $\{e_n\}$ is the standard basis.
- **Insight**: $K$ is compact because its eigenvalues $\lambda_n = 1/n$ converge to 0.
- **Contrast with JNF**: For any $\lambda \neq 0$ (e.g., $\lambda=1$), $\ker(I - K) = \{0\}$ and the operator is invertible. However, at $\lambda = 0$, the "JNF-like" structure fails because $0$ is the cluster point. The kernel is $\{0\}$ but the range is dense and not closed, demonstrating why the Riesz-Schauder theorem explicitly excludes $\lambda = 0$.