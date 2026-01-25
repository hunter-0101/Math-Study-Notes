A [[Topological Space]] $(X, \mathcal T)$ is **disconnected** if there exists a **separation** of $X$: $$X=U\cup V\where U,V\in\mathcal T,U,V\neq\varnothing,U\cap V=\varnothing$$We say that $(X,\mathcal T)$ is **connected** if no such separation exists.
- **Equivalent Characterizations**
	- $X$ is connected iff the only clopen subset of $X$ are $\varnothing$ and $X$. 
	- $X$ is connected iff every [[Continuous Function]] $f: X \to \{0, 1\}$ (with the discrete topology) is constant. 
## Properties & concepts
- **Topology dependence**: connectedness is not an absolute property of a set but depends strictly on $\mathcal T$. If $\mathcal T_1 \subset \mathcal T_2$, then $(X, \mathcal T_2) \text{ connected} \implies (X, \mathcal T_1) \text{ connected}$.
- **Continuous Invariance:** If $f: X \to Y$ is continuous and $X$ is connected, then $f(X)$ is connected in the subspace topology of $Y$.
- **Connected Components:** For any $x \in X$, the connected component of $x$, denoted $C(x)$, is the union of all connected subsets containing $x$.
    - $C(x)$ is the maximal connected subset of $X$.        
    - Components form a partition of $X$.
    - Every component is closed in $X$.
- **Products:** $\prod X_\alpha$ is connected if and only if each $X_\alpha$ is connected (using the product topology).
## Path Connectedness
A **path** ([[Homotopy]]) in $X$ from $x$ to $y$ is a [[Continuous Function]] $\gamma: [0, 1] \to X$ s.t. $\gamma(0) = x,\gamma(1) = y$. A space $X$ is **path connected** if for every pair $x, y \in X$, there exists a path in $X$ from $x$ to $y$.
- **Relation to connectedness**: path connectedness is generally stronger than connectedness. 
- **Path components**: defined by the equivalence relation $x \sim y$ iff there exists a path from $x$ to $y$. Path components partition $X$, but unlike connected components, they are not necessarily closed.
- **Topologist's sine curve**: let $$S = \Set{\paren{x, \sin\frac{1}{x}} : x \in (0, 1]} \cup \Set{(0, y) : y \in [-1, 1]}$$Then $S$ is connected but not path connected. This illustrates that "closeness" in the sense of limit points does not guarantee the existence of a continuous path.