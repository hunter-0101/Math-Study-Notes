For $V$ a topological [[Vector Space]] over [[Field]] $F$, its **topological dual space** is defined as $$V^*=\mathcal C(V,F)=\set{\ell\in\mathcal L(V,F):\ell\text{ continuous}}$$This is obviously a subspace of its [[Algebraic Dual Space]] $V^\#$, and any $\ell\in V^*$ is called a **continuous linear functional**. Note that by discussion in [[Banach Space]] a functional is bounded iff it's continuous, that is, $$V^*=\mathcal C(V,F)=\mathcal B(V,F)$$It's for this reason that we'll conventionally use $\mathcal B(V,F)$ as alternative notation for $V^*$. Note that in this note we'll assume further that $V$ is a [[Normed Vector Space]] over $\mathbb R$ or $\mathbb C$. 
- **[[Banach Space]] structure**: for [[Normed Vector Space]] $V$, $V^*$ is Banach with its operator norm. 
  **Proof**: obviously $V^*$ is a normed vector space with operator norm defined as $$\|T\|=\sup_{v\in V,\|v\|=1}\|Tv\|_F$$For completeness, pick a Cauchy sequence $\set{T_n}\subset V^*$, then for any fixed $v\in V$ we have $$|T_m(v)-T_n(v)|\le\|T_m-T_n\|\cdot\|v\|$$hence $\set{T_n(v)}$ is Cauchy, and by completeness of $F$ we can define $$T(v)=\lim_{n\to\infty}T_n(v),\quad\forall v\in V$$We can easily verify that $T\in V^*$, and the convergence $T_n\to T$ is also valid.  
- **Preservation of separability**: for [[Normed Vector Space]] $V$, if $V^*$ is separable, then so is $V$.
  **Proof**: by separability of $V^*$ we can pick a countable dense subset $\set{\ell_n}\subset V^*$. By setting $$S_1^*=\set{\ell\in V^*:\left\|\ell\right\|=1},\quad\hat\ell_n=\frac{\ell_n}{\|\ell_n\|}$$then we can easily verify that $\set{\hat\ell_n}$ is a countable dense subset of $S_1^*$. Since $\|\hat\ell_n\|=1$, there exists a corresponding $v_n\in V$ s.t. $$\|v_n\|=1,\quad \hat\ell_n(v_n)>\frac{1}{2}$$Now consider $W=\overline{\span(v_n:n\in\mathbb N)}$, which is separable with $\span_\mathbb Q(v_n:n\in\mathbb N)$ being dense in $W$. If $W\neq V$, there exists $v_0\in V\backslash W$, and WLOG assuming $\|v_0\|=1$ by corollary of norm-preserving extension below there exists $\ell_0\in V^*$ s.t. $$\|\ell_0\|=1\quad\text{and}\quad\ell_0(v)=0,\quad\forall v\in V\quad\Longrightarrow\quad\ell_0\in S_1^*$$therefore for any $n\in\mathbb N$ we have $$\|\ell_0-\hat\ell_n\|=\sup_{v\in V,\|v\|\le1}|\ell_0(v)-\hat\ell_n(v)|\ge|\ell_0(v_n)-\hat\ell_n(v_n)|=|\hat\ell_n(v_n)|\ge\frac{1}{2}$$which contradicts the density of $\set{\hat\ell_n}$ on $S_1^*$. 
	- **Invalid converse**: the converse is not true in general, i.e., separability of $V$ does not imply separability of $V^*$, e.g., $L^1$ is separable, but $L^\infty$ is not. [[Lp Space]]
- **Riesz representation theorem**: for $\ell\in\mathcal H^*$ where $\mathcal H$ is a [[Hilbert Space]] there exists a unique $v\in\mathcal H$ s.t. $\ell(u)=\langle u,v\rangle,\forall u$, and moreover $\|\ell\|=\|v\|$.
  **Proof**: consider $S=\ker\ell$, which is closed by continuity. Assume $S\neq\mathcal H$ (otherwise $v=0$) and pick $h\in S^\perp,\|h\|=1$, then it can be verified that $v=\overline{\ell(h)}h$ satisfies the requirements. Norm and uniqueness are obvious.
	- **Intuition**: for $\mathcal H$ separable we can directly take an orthonormal basis $\set{e_n}$ and define $v=\sum\overline{\ell(e_n)}e_n$. The proof above just generalize this idea to general Hilbert space.
## Topological consequences of HBT
While the extension mechanism in [[Algebraic Dual Space]] is purely algebraic, the consequences for normed spaces are profound.
- **Norm-preserving extension**: given $\ell_0\in V_0^*$ for some $V_0\subset V$ we can extend it to $\ell\in V^*$ with $$\|\ell\|_{V^*}=\|\ell_0\|_{V_0^*}$$**Proof**: by HBT ([[Algebraic Dual Space]]) applied to $$p(v)=\|f_0\|_{V_0}\|v\|$$which is a seminorm that dominates $|\ell_0|$, we can get an extension $\ell$ of $\ell_0$ with $\|\ell\|=\|\ell_0\|$.
	- **Supporting functional**: given some $v_0\in V$ if we further pick $$\ell_0(\lambda v_0)=\lambda\|v_0\|,\quad\forall\lambda\in F$$then its norm-preserving extension obtained from above satisfies $$\ell(v_0)=\ell_0(v_0)=\|v_0\|\quad\text{and}\quad\|\ell\|_V=\|\ell_0\|_{\span(v_0)}=1$$This functional is called a supporting functional due to its geometric interpretation discussed in [[Hyperplane]].
- **Separating property**: the norm topology on a Banach space is completely "seen" by its dual. Formally, for $v,w\in V$ we have $$v=w\quad\iff\quad\ell(v)=\ell(w),\forall\ell\in V^*$$We say that $V^*$ separates the points in $V$.
    - **Corollary**: if $\ell(v) = 0$ for all $\ell \in V^*$, then $v=0$. 
## Double dual
The **double dual (bidual)** $V^{**}$ is the continuous dual of $V^*$.
- **Canonical embedding**: we define the **canonical evaluation map** as $$J: V \to V^{**},\quad J(v)(\ell) = \ell(v), \quad \forall v \in V, \forall \ell \in V^*$$Essentially, instead of viewing $\ell$ as a function acting on fixed $v$, we view $v$ as a function acting on varying $\ell$.
	- **Isometry property**: for any [[Normed Vector Space]] $V$, $J$ is a linear isometry, hence $V$ is isometrically isomorphic to a subspace of $V^{**}$.
	  **Proof**: by definition of the operator norm ([[Normed Vector Space]]) in $V^{**}$ we have $$\|J(v)\| = \sup_{\ell \in V^*, \|\ell\|=1} |J(v)(\ell)| = \sup_{\ell \in V^*, \|\ell\|=1} |\ell(v)|$$From corollary of norm-preservation extension we know that for any $v$, there exists some $\ell$ with $\|\ell\|=1$ such that $\ell(v) = \|v\|$. Therefore we have $\|J(v)\| = \|v\|$.
    * **Completeness**: since $V^{**}$ is a dual space, it is always a [[Banach Space]], as shown above. Consequently, the closure $\overline{J(V)}$ is a completion of $V$. 
## Reflexive Space
A [[Banach Space]] $V$ is called **reflexive** if the canonical embedding $J$ is surjective, $$J(V) = V^{**}$$Note that it's possible for $V$ to be isometrically isomorphic to $V^{**}$ via some other map without being reflexive, though such examples are pathological - see James' space below. 
- **Basic properties & examples**
	* **Finite dimensional spaces**: any finite-dimensional [[Normed Vector Space]] is reflexive.
	  **Proof**: by the result on dual system ([[Algebraic Dual Space]]) (or the [[Matrix]] representation of linear operator on [[Vector Space]], or even simply invoke RRT) we have that $$\dim V = \dim V^* = \dim V^{**}$$Since $J$ is injective (isometry), dimension equality implies surjectivity.
	* **[[Lp Space]]**
	    * For $1 < p < \infty$ and $(\Omega,\Sigma,\mu)$ a $\sigma$-finite [[Measure]] space, $L^p(\Omega)$ is reflexive, which follows from the Riesz Representation Theorem for $L^p$, stating that $$(L^p)^* \cong L^q,\quad\forall\frac{1}{p}+\frac{1}{q}=1, 1<p,q<\infty$$This is detailed in [[Lp Space]]
	    * $L^1$ and $L^\infty$ (and $\ell^1, \ell^\infty$) are **not** reflexive, since $L^\infty,\ell^\infty$ are not separable.
* **Hereditary Properties**:
    * **Closed Subspaces**: closed subspace of a reflexive space is reflexive.
    * **Banach Space $V$**: $V$ is reflexive iff $V^*$ is reflexive.
* **James's theorem**: a [[Banach Space]] $V$ is reflexive iff all $\ell\in V^*$ there exists an element $v\in V$ of norm $\|v\|\le1$ s.t. $\ell(v)=\|\ell\|$.
## Weak\* Convergence
**Weak* convergence** for $\{\ell_n\} \subset V^*$ is defined as $$\ell_n\wsto\ell\quad\iff\quad\ell_n(v) \to \ell(v), \quad \forall v \in V$$This is the counterpart of weak convergence ([[Normed Vector Space]]) on dual space, and is the realization of [[Weak Topology]] on the topological dual space. 
* **Comparison of Topologies**
    * **Norm (Strong)**: convergence on the unit sphere uniformly. It's the strongest of all.
    * **Weak ($\sigma(V^*, V^{**})$)**: convergence against all functionals in the bidual.
    * **Weak* ($\sigma(V^*, V)$)**: convergence against all vectors in the pre-dual $V$.
    * Since $V \subset V^{**}$ (via canonical embedding), the weak* topology is **coarser** (has fewer open sets) than the Weak topology. They coincide iff $V$ is reflexive.
* **Banach-Alaoglu theorem**: The closed unit ball $B_{V^*} = \{\ell \in V^* : \|\ell\| \le 1\}$ is **compact** in the weak* topology.
    * **Significance**: this is the most important compactness result in functional analysis. Unlike $B_V$, which is only weakly compact if $V$ is reflexive, $B_{V^*}$ is *always* weak* compact.
    * *Proof Idea*: Tychonoff's theorem applied to a product of compact intervals in $F$.
* **Metrizability**: If $V$ is separable, then the weak* topology on the bounded subset $B_{V^*}$ is metrizable.
    * **Corollary**: if $V$ is separable, every bounded sequence in $V^*$ has a weak* convergent subsequence. (This creates a "Bolzano-Weierstrass" property for duals of separable spaces).
* **Lower Semi-Continuity**: The norm $\|\cdot\|_{V^*}$ is weak* lower semi-continuous: $$\ell_n \xrightarrow{w^*} \ell \implies \|\ell\| \le \liminf_{n\to\infty} \|\ell_n\|$$Note thatThis also holds for weak convergence in $V$.
---
## Other info
### Goldstine’s Theorem
While $J(V)$ might not equal $V^{**}$ (non-reflexive), it is distinctively "large" inside it.
* **Theorem**: The image of the closed unit ball $B_V$ under $J$ is **weak-*** dense in the closed unit ball $B_{V^{**}}$.
* *Interpretation*: Every functional in $V^{**}$ can be approximated by elements of $V$ if we use the weak-* topology (pointwise convergence on $V^*$).
### Kakutani’s Theorem (Geometric Interpretation)
This is arguably the most important characterization of reflexivity for optimization and PDEs.
* **Theorem**: A Banach space is reflexive if and only if its closed unit ball is **compact in the weak topology**.
* *Utility*: This generalizes the Heine-Borel theorem (closed + bounded = compact) to infinite dimensions, provided we switch to the weak topology. This allows for extracting convergent subsequences in minimization problems (e.g., Calculus of Variations).
### James' Space (The Cautionary Tale)
R.C. James constructed a Banach space $B$ with a basis such that:
$$B \text{ is isometrically isomorphic to } B^{**}$$
**BUT** the canonical map $J: B \to B^{**}$ is **not** surjective (the image has codimension 1).
* *Lesson*: Reflexivity is not just about the *space* being isomorphic to its double dual; it requires the *canonical evaluation map* to be the isomorphism.