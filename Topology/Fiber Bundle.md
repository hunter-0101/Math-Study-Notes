A **fiber bundle** is a 4-tuple $(E, B, \pi, F)$ consisting of:
1. **Base space**: a [[Topological Space]] $B$ serving as the base of the bundle.
2. **Fiber**: a topological space $F$ assigned to each of the points in $B$. 
3. **Total space**: a topological space $E$ consisting of all fibers assigned to points in $X$. 
4. **Bundle projection**: a surjective ([[Relation]]) [[Continuous Function]] $\pi:E\surto B$ with the **local triviality condition** - for any $x\in B$ there exists an open neighborhood $U\ni x$ and a homeomorphism ([[Continuous Function]]) $\varphi:\pi^{-1}(U)\to U\times F$ with the commutative diagram 
   <p align="center"><img align="center" src="https://i.upmath.me/svg/%0A%5Cbegin%7Btikzcd%7D%0A%5Cpi%5E%7B-1%7D(U)%20%5Carrow%5Bd%2C%20%22%5Cpi%22'%5D%20%5Carrow%5Br%2C%20%22%5Cvarphi%22%5D%20%26%20U%5Ctimes%20F%20%5Carrow%5Bld%2C%20%22%5Ctext%7Bproj%7D_1%22%5D%20%5C%5C%0AU%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%26%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%0A%5Cend%7Btikzcd%7D%0A"/></p>
   This condition ensures that fiber bundle is always **locally a product space**. The pair $(U,\varphi)$ is called a **local trivialization**. 
When $E=B\times F$ we call it a **trivial bundle**, and a general non-trivial fiber bundle could possess a nontrivial global "twist", e.g., the Möbius strip below. Conventionally a fiber bundle will be denoted as a short sequence $F\to E\xto{\pi}B$, the projection, $\pi:E\to B$, or simply as $E$. 
- **Discussion**: [[Set]] theoretically, in a fiber bundle the total space is simply a disjoint union: $$E=\bigsqcup_{x\in B}E_x=\bigsqcup_{x\in B}F$$The non-triviality of a bundle is a statement about the **obstruction to extending local product homeomorphisms to a global one**. 
- **Homotopy Lifting Property:** Fiber bundles are examples of **fibrations**, specifically Serre fibrations, allowing for the lifting of homotopies from the base to the total space.
- Exact sequences: Every fiber bundle induces a long exact sequence of homotopy groups: $$\dots \to \pi_n(F) \to \pi_n(E) \to \pi_n(B) \to \pi_{n-1}(F) \to \dots$$
- **Counterexamples**: we list some examples that are **not** fiber bundles.
	- **Singular fiber**: set $\pi:E\to\mathbb R$ where $E$ is the union of $x$- and $y$-axis. This is not a fiber bundle because the fiber "jumps" in dimension at the origin. This structure is usually described using **fibration** or **sheaf** with varying stalks. 
## Concept
- **Section**: a (global) section of a fiber bundle is a continuous map $$s: B \to E\quad\st\quad\pi \circ s = \text{id}_B$$A **local section** is defined on an open subset $U \subset B$ as $s: U \to \pi^{-1}(U)$ such that $\pi \circ s = \text{id}_U$.
	- **Note:** global sections may not exist (e.g., the tangent bundle of $S^2$ has no non-vanishing global section per the Hairy Ball Theorem).
- **Transition Functions and Structure Group**: let $B\subset\bigcup U_i$ be an open cover with local trivializations $\phi_i: \pi^{-1}(U_i) \to U_i \times F$. For $x \in U_i \cap U_j$, the map $\phi_i \circ \phi_j^{-1}$ on $(\{x\} \times F)$ induces a homeomorphism of the fiber: $$\psi_{ij}(x): F \to F, \quad \psi_{ij}(x)(f) = pr_2 \circ \phi_i \circ \phi_j^{-1}(x, f)$$The maps $\psi_{ij}: U_i \cap U_j \to \text{Homeo}(F)$ are called transition functions. They satisfy the cocycle condition:
  1. $\psi_{ii}(x) = \text{id}_F$  
  2. $\psi_{ij}(x)\psi_{jk}(x)\psi_{ki}(x) = \text{id}_F$
  The **structure group** $G$ is a subgroup of $\text{Homeo}(F)$ such that all transition functions take values in $G$.
- **Differentiability**: a fiber bundle is **differentiable** (or smooth) if $E, B, F$ are smooth manifolds, $\pi$ is a smooth map, and the local trivializations $\phi_i$ are diffeomorphisms. In this case, the transition functions $\psi_{ij}$ are smooth maps into a Lie group $G$.
## Examples

### Möbius strip
A non-trivial bundle over $S^1$ with fiber $F = [-1, 1]$.
- **Base Space:** $B = S^1$.
- **Transition Functions:** If we cover $S^1$ with two overlapping intervals, one transition function must involve a reflection $f \mapsto -f$.
- **Structure Group:** $G = \{1, -1\} \cong \mathbb{Z}_2$, reflecting the non-orientability.
### Vector bundle
See [[Vector Bundle]] for definition and basic discussion.
- **Example: Tangent Bundle $TS^n$:** The collection of all tangent spaces to a sphere.
- **Insight:** A vector bundle is trivial if and only if it admits $n$ linearly independent global sections.  
### Sphere bundle
Associated with a vector bundle $(E, B, \pi, \mathbb{R}^n)$ equipped with a Riemannian metric, the sphere bundle $S(E)$ consists of all unit vectors in $E$.
- **Fiber:** $S^{n-1}$.
- **Example: Unit Tangent Bundle of $S^2$:** This is homeomorphic to the real projective space $\mathbb{R}P^3$.
## Other info
#### Tool 1: The Bundle Construction Theorem
This tool allows us to build a bundle purely from transition functions.
Theorem: Given a cover $\{U_i\}$ of $B$ and a collection of maps $\psi_{ij}: U_i \cap U_j \to G$ satisfying the cocycle condition, there exists a unique (up to isomorphism) fiber bundle with these transition functions.
- **Practical Use:** To prove two bundles are isomorphic, it suffices to show their transition functions are related by $\psi'_{ij} = \lambda_i \psi_{ij} \lambda_j^{-1}$ for some $\lambda_i: U_i \to G$.
#### Tool 2: Obstruction Theory for Sections
To determine if a global section exists, one uses characteristic classes.
- **Example 1 (Stiefel-Whitney Class $w_1$):** A line bundle $L \to B$ is trivial (and thus has a non-vanishing section) if and only if $w_1(L) = 0 \in H^1(B; \mathbb{Z}_2)$. In the **Möbius strip**, $w_1 \neq 0$, confirming it is non-trivial.
- **Example 2 (Euler Class $e$):** For an oriented vector bundle $E \to B$, the existence of a non-vanishing section implies $e(E) = 0$. For $TS^2$, $e(TS^2) = \chi(S^2) = 2 \neq 0$, proving no such section exists.
#### Tool 3: Classification of Bundles over Suspensions
For a Lie group $G$, the isomorphism classes of principal $G$-bundles over a sphere $S^n$ are in one-to-one correspondence with the homotopy classes of the "clutching map": $$[S^{n-1}, G] \cong \pi_{n-1}(G)$$
- **Application:** To classify complex line bundles over $S^2$, we look at $\pi_1(U(1)) \cong \mathbb{Z}$. Each integer corresponds to a unique bundle (the Hopf bundle and its powers).