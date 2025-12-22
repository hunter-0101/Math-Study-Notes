Given [[Field]] $K$, an **$K$-affine space** is a tuple $(\mathbb{A},\vect{\mathbb A},+)$ consisting of:
1. **Affine structure of points**: $\mathbb A$ a non-empty set consisting of the **points** of the affine space.
2. **Associated vector space**: $\vect{\mathbb A}$ an $K$-[[Vector Space]] of $\mathbb A$ consisting of **translation vectors**.
3. **Vector space action**: the action of $\vect{\mathbb A}$ on $\mathbb A$ by the operation $$+:\mathbb A\times\vect{\mathbb A}\to\mathbb A$$which sends $p\in\mathbb A$ to $p+v\in\mathbb A$ given any $p\in\vect{\mathbb A}$.
	1. **Right identity**: $p+0=p,\forall p\in\mathbb A$.
	2. **Associativity**: $(p+v)+w=p+(v+w),\forall p\in\mathbb A,v,w\in\vect{\mathbb A}$.
	3. **Free action**: the [[Group Action]] is free, i.e., the map $$\vect{\mathbb A}\to\mathbb A,\quad v\mapsto p+v$$is bijective for any $p\in\mathbb A$.
From the axioms above we can also deduce the bijective translation, i.e., the map $$\mathbb A\to\mathbb A,\quad p\mapsto p+v$$is bijective for any $v\in\vect{\mathbb A}$, and for any $p,q\in\mathbb A$ there exists a unique $v\in\vect{\mathbb A}$ s.t. $b=a+v$. This relation is denoted $v=b-a$. 
- **Intuition**: an affined space is like a vector space without the origin, or more concretely, an [[Euclidean Space]] with an axis frame. We only care about the relative positions between points, and ignores and absolute positions w.r.t a specific basis frame. To put vividly, an affine space is a vector space that "forgets" its origin. 
- **Dimension**: we define $\dim\mathbb A=\dim\vect{\mathbb A}$ as the dimensional of the associated [[Vector Space]]. 
- **Affine coordinate**: an **affine frame** is a coordinate frame consisting of an **origin** $o\in\mathbb A$ and a **linear basis** ([[Vector Space]]) $(v_i:1\le i\le n)\subset\vect{\mathbb A}$ s.t. every $p\in\mathbb A$ can be represented as $$p=o+\sum_{i=1}^n\lambda_iv_i\where\lambda_i\in K,\forall 1\le i\le n$$Here $(\lambda_i:1\le i\le n)$ is called the **affine coordinate**. 
## Related concepts
- **Affine Transformations**: A map $f: \mathbb{A} \to \mathbb{B}$ is affine if there exists a linear map $T: V \to W$ such that $f(P + v) = f(P) + T(v)$. Intuition: Affine maps preserve collinearity and ratios of distances on parallel lines.
## Zariski topology
The **Zariski topology** on $\mathbb{A}_k^n$ is the topology where the closed sets are exactly the algebraic sets $V(S)$ ([[Affine Variety]]).
- **Intuition**: This topology is much "coarser" than the standard Euclidean topology. In the Zariski topology, open sets are "huge" (dense), and the topology is generally not Hausdorff ($T_2$).
- **Base**: a standard base is given by **principal open sets** $$D(f) = \set{p \in \mathbb{A}_k^n : f(p) \neq 0}$$Any open set is a union of these.
- **Noetherian property**: every descending chain of closed subsets in $\mathbb A_k^n$ stabilizes. This follows directly from the Hilbert basis theorem ([[Polynomial Ring]]) and the fact that 
- **Compactness**: Every Zariski-open set is quasi-compact (though not in the sense of being "small" or "bounded," but in the sense that every open cover has a finite subcover).
- **Density of Open Sets**: In an irreducible variety, any non-empty open set is dense. This is why "generic" properties in AG often mean "true on a Zariski-open set."
- **Comparison to DG**: While a smooth manifold is locally homeomorphic to $\mathbb{R}^n$, an affine variety is locally "isomorphic" (as a ringed space) to the spectrum of a localized ring. 