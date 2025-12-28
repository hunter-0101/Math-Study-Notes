Given a topological [[Field]] $F$, an **topological vector space (TVS)** is a pair $(V, \mathcal T)$ consisting of:
1. **[[Vector Space]]**: $V$ being an $F$-vector space.
2. **[[Topological Space]]**: $\mathcal T$ being a topology on $V$ s.t. the vector space operations (**addition** & **scaler multiplication**) are continuous, which is called a **vector topology**. 
This is a central object investigated in functional analysis. Note that [[Normed Vector Space]] is a common type of TVS investigated thoroughly. 
- **Translation invariance**: $\mathcal T$ is translation-invariant. For any $a \in V$, the map $T_a(x) = x+a$ is a homeomorphism. Consequently, $\tau$ is uniquely determined by the neighborhood filter at the origin, $\mathcal{N}(0)$.
- **Hausdorff requirement**: Many authors include the Hausdorff ($T_2$) property in the definition. In a TVS, the following are equivalent ([[Separation Axioms]]):
    1. $(V, \tau)$ is Hausdorff.
    2. $(V, \tau)$ is $T_1$ (points are closed).
    3. The singleton $\{0\}$ is closed in $(V, \tau)$.
- **Non-Normable Examples**:
    - **$L^p([0, 1])$ for $0 < p < 1$**: A metric TVS that is not locally convex (the only continuous linear functional is the zero functional).
    - **$C^\infty(\Omega)$**: The space of smooth functions with the topology of uniform convergence of all derivatives on compact subsets. This is a **Fréchet space** but not normable.
- **Locally Convex Spaces (LCS)**: A TVS is locally convex if there exists a neighborhood base at $0$ consisting of convex sets. This is equivalent to saying the topology is induced by a family of seminorms $\{p_\alpha\}_{\alpha \in A}$.
## Linear operator
For TVS $V$ and $W$ over $\mathbb{K}$, a mapping $T: V \to W$ is a **continuous linear operator** if it satisfies the algebraic linearity conditions and is continuous with respect to the topologies $\tau_V$ and $\tau_W$.
- **Algebraic Inheritance**: Definitions for $\ker T$, $\im T$, and the Rank-Nullity intuition persist. However, in the infinite-dimensional TVS setting, $\im T$ is not guaranteed to be closed, which is a central problem in solvability of operator equations.
- **Continuity at Zero**: By linearity and translation invariance, $T$ is continuous on $V$ $\iff$ $T$ is continuous at $0 \in V$.
- **Boundedness (TVS sense)**: In a TVS, a set $B \subset V$ is **bounded** if for every neighborhood $U \in \mathcal{N}(0)$, there exists $s > 0$ such that $B \subset tU$ for all $t > s$.
    - $T$ is continuous $\implies$ $T$ is bounded (maps bounded sets to bounded sets).
    - The converse is true for **bornological spaces** (including all Fréchet and normed spaces) but false in general TVS.
- **Closed Kernel**: If $T: V \to \mathbb{K}$ is a linear functional ($T \neq 0$), then $T$ is continuous $\iff$ $\ker T$ is a closed hyperspace.
## Actionable Theoretical Tools
### Concrete Examples of Insights
1. **On the Importance of Local Convexity**:
    - _Context_: The Hahn-Banach Theorem (existence of enough continuous linear functionals to separate points).
    - _Insight_: This requires local convexity. In $L^p(0,1)$ for $p < 1$ (not locally convex), the dual space is $\{0\}$. Thus, geometric intuition about "hyperplanes" separating sets fails in non-LCS.
2. **On the Closedness of Subspaces**:
    - _Context_: In finite dimensions, every subspace is closed. In TVS, this is false.
    - _Example_: Let $V = \ell^2$ (Hilbert space). The subspace $c_{00}$ of sequences with finite support is dense in $\ell^2$ but not closed.
    - _Actionable Rule_: A linear operator $T$ has a continuous inverse on its range $\iff$ $T$ is **bounded below**: $\exists c > 0$ such that $\|Tv\| \ge c\|v\|$.