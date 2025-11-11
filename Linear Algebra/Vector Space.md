A set $V$ is called a **vector (linear) space** over [[Field]] $F$ if it's equipped with two binary functions (addition $+:V\times V\to V$ and scaler multiplication $\cdot:F\times V\to V$) s.t.:
1. **Group structure**: $(V,+)$ is an abelian [[Group]].
2. **Distributivity**: $(a+b)v=av+bv,a(u+v)=au+av$.
3. **Compatibility**: $a(bv)=(ab)v$.
4. **Scaler multiplication identity**: $1v=v$.
$V$ is also called a $K$-vector field. Notice that a vector space is naturally a [[Module]]
- **Direct sum decomposition**: we write:$$V=\bigoplus V_k$$if each $v\in V$ can be uniquely represented as $v=\sum v_k,v_k\in V_k$.
- **Hamel (Algebraic) basis**: a Hamel basis is a linearly independent set of [[Module]] generators. We sometimes use **Hamel-span** to emphasize that only finite combination of generators is allowed. A Hamel basis always exist for a vector space.
  **Proof**: denote $X$ the collection of linearly independent subsets of $V$. Obviously $X$ is not empty and is partially ordered ([[Order]]) by inclusion $\subset$. For any $Y\subset X$ s.t. $(Y,\subset)$ is totally ordered we pick $L_Y$ the union of all elements in $Y$, then $L_Y\in X$ is an upper bound for $Y$. Now by Zorn's lemma ([[Set Theory]]) we can pick $L_\max$ a maximal element of $X$, which is a basis for $V$ by maximality.
	- **Discussion**: the fact that $v\in V$ cannot be expressed as a $K$-linear combination of $L_\max$ is equivalent to $v$ being linearly independent of $L_\max$ replies on division ring structure of $K$, since we're using the division operation that $$rv+\sum r_iv_i=0\quad\iff\quad v=-r^{-1}\sum r_iv_i$$This is actually a characterization of division ring, as discussed in [[Module]].
	- **Dimension**: given a basis $E=\set{e_i}$ of $V$ we define $\dim_F V=|E|$ if $|E|<\infty$, and say that $V$ is infinite dimensional if such finite basis does not exists. 
	  **Well-define-ness**: when two basis contains different number of elements then the larger one must be linearly dependent, via discussion on rank of [[Matrix]].
	- If $\mathbb K\subset\mathbb C$ is a field and $E$ is an infinite dimensional Banach space over $K$, then every Hamel basis for $E$ has at least cardinality $\mathfrak c=|\mathbb C|$.
	  **Proof**: denote the basis as $\set{v_j}_{j\in\mathbb N}$, by definition of Hamel basis we have $$E=\bigcup_{n\in\mathbb N}\operatorname{span}(v_j)_{j=1}^n$$This means $E$ is a countable union of proper subspaces of finite dimension, but every finite dimensional proper subspace of a normed space is nowhere dense, thus $E$ is a first category, contradicting the Baire category theorem.
- **Isomorphism**: an isomorphism $\phi$ between two vector spaces $V,W$ is a bijective linear transform, which is define below.
## Linear transform
For vector spaces $V, W$ over [[Field]] $F$, a **linear transform** (**operator**) is a mapping $T:V \to W$ that preserves addition and scalar multiplication. In this note we assume $\dim V=n,\dim W=m$ with $m,n<\infty$. More general discussion can be found in [[Hilbert Space]] and [[Operator]].
- **[[Matrix]] of linear transform**: given basis $\set{v_j}_{1\le j\le n},\set{w_i}_{1\le i\le m}$ for $V,W$ define the matrix of $T$ under the basis as the unique $A\in F^{m\times n}$ satisfying $$T(v_1,\cdots,v_n)=(T(v_1),\cdots T(v_n))=(w_1,\cdots,w_m)A$$Intuitively it's saying that $A_{ij}$ is the $w_i$ component in $T(v_j)$. The induced coordinate transform $A:F^n\to F^m$ is given by $x\mapsto y=Ax$ since we have that $$T\left(\sum_{j=1}^mx_jv_j\right)=\sum_{j=1}^nx_jT(v_j)=\sum_{j=1}^nx_j\sum_{i=1}^mA_{ij}w_i=\sum_{i=1}^mw_i\sum_{j=1}^nx_jA_{ij}=\sum_{i=1}^ny_iw_i\quad\Longrightarrow\quad y=Ax$$The usual formulas for $T\in\mathcal L(V)$ is just a special cases.
	- **Change of basis**: given $T\in\mathcal L(V,W)$ and two pair of basis $$(v_j')=(v_j)P,\quad (w_i')=(w_i)Q$$its matrix $A,B$ under old and new basis is associated, by coordinate formula, via $$T(v_j')=T((v_j)P)=T(v_j)P=(w_i)AP=(w_i')Q^{-1}AP\quad\Longrightarrow\quad B=Q^{-1}AP$$where the extraction of $P$ follows from linearity of $T$. 
- **Jordan normal form**: for $T\in\mathcal L(V)$ we have the direct sum invariant subspace decomposition $$V=\bigoplus_iV_i$$together with a basis $e_j^i$ for each $V_i$ s.t. $$(\lambda_iI-A)e_j^i=e_{j-1}^i,\quad\forall j$$dimension of the subspaces and coefficients $\lambda_i$ are determined uniquely up to permutation.
  **Proof**: notice that the proof in [[Jordan Normal Form]] only relies on linearity and finiteness of dimensionality, its proof immediately generalize to this case.
- **Trace**: see [[Matrix]].

---
## Tensor product
Given two $K$-vector spaces $V,W$ where $K$ is a [[Field]], define their tensor product as an abelian [[Group]] together with $\otimes:V\times W\to V\otimes W$ satisfying $$\begin{align}(v_1+v_2)\otimes w&=v_1\otimes w+v_2\otimes w\\v\otimes(w_1+w_2)&=v\otimes w_1+v\otimes w_2\\s(v\otimes w)&=(sv)\otimes w=v\otimes(sw)\end{align}$$for all $v_i\in V,w_i\in W,s\in K$.
