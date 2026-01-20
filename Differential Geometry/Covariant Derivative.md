Consider a smooth [[Vector Bundle]] $(M,E,\pi,\mathbb R^k)$ on [[Smooth Manifold]] $M$. A **covariant derivative** on $E$ is an $\mathbb{R}$-linear map $$\nabla: \Gamma(E) \to \Gamma(T^*M \otimes E) \cong \Omega^1(M, E)$$that satisfies the **Leibniz rule (product rule)**: $$\nabla(fs) = df \otimes s + f \nabla s,\quad\forall f\in C^\infty(M),s\in\Gamma(E)$$Here $T^*M$ is the cotangent bundle ([[Differential Form]]), and $\Omega^1(M,E)$ is the module of all $1$-forms taking values from $E$. 
- **Motivation**: in a trivial bundle $M \times \mathbb{R}^r$, one can differentiate components component-wise. In a general bundle, the fibers $E_p,E_q$ at distinct points $p\neq q$ are distinct vector spaces with no canonical identification. $\nabla$ provides a rule for "**connecting**" these fibers, effectively defining how a section "changes" as we move along the base manifold. A concrete example is provided in [[Tangent Bundle]]. 
- **Directional Differentiation**: For a vector field $X \in \mathfrak{X}(M)$, we define the covariant derivative of $s$ in the direction $X$ as the contraction $\nabla_X s := i_X(\nabla s)$. This yields a map $\nabla_X: \Gamma(E) \to \Gamma(E)$ which is $C^\infty(M)$-linear in $X$ and $\mathbb{R}$-linear in $s$.
- **Fundamental lemma of covariant derivative**: the value $(\nabla_X s)(p)$ depends only on the value of $X$ at $p$ and the values of $s$ along any curve $\gamma(t)$ such that $\gamma(0)=p$ and $\dot{\gamma}(0)=X_p$. Specifically, it does not depend on the derivative of $X$.
## Property
To perform practical computations, we express $\nabla$ in terms of a local smooth frame $S = (e_1, \dots, e_r)$ over an open set $U \subset M$.
#### The Connection Matrix
Since $\nabla e_j \in \Omega^1(U, E)$, it can be expanded in terms of the frame $S$: $$\nabla e_j = \sum_{i=1}^r \omega_j^i \otimes e_i$$The matrix of 1-forms $\omega = (\omega_j^i) \in \Omega^1(U, \mathfrak{gl}(r, \mathbb{R}))$ is called the connection form (or connection matrix) relative to the frame $S$.
#### Action on General Sections
For any section $s = \sum \sigma^i e_i \in \Gamma(U, E)$, the covariant derivative is computed as: $$\nabla s = \sum_{i=1}^r (d\sigma^i + \sum_{j=1}^r \sigma^j \omega_j^i) \otimes e_i$$In matrix notation, viewing $\sigma$ as a column vector of functions: $\nabla \sigma = d\sigma + \omega \sigma$.
#### Gauge Transformation (Change of Frame)
If $\tilde{S} = S \cdot g$ is another frame, where $g: U \to GL(r, \mathbb{R})$ is a smooth map, the connection matrix transforms according to the following identity: $$\tilde{\omega} = g^{-1} dg + g^{-1} \omega g$$
- The term $g^{-1} \omega g$ represents the "adjoint" transformation (similar to linear maps).
- The term $g^{-1} dg$ represents the "inhomogeneous" part arising from the Leibniz rule, reflecting the fact that the connection is not a tensor but a differential operator.
## Example: induced Connection on a Submanifold
Consider a smooth submanifold $M \subset \mathbb{R}^n$. The tangent bundle $TM$ is a sub-bundle of the trivial bundle $T\mathbb{R}^n|_M \cong M \times \mathbb{R}^n$. This context provides a concrete visualization of how a connection is "forced" by geometry.
#### Setup
1. **Ambient Connection**: $\mathbb{R}^n$ has a canonical flat connection $D$. For a vector field $Y = (Y^1, \dots, Y^n)$ on $\mathbb{R}^n$, $(D_X Y)^i = X(Y^i)$.
2. **Orthogonal Projection**: At each $p \in M$, there is an orthogonal projection $P_p: T_p\mathbb{R}^n \to T_p M$ (assuming the standard Euclidean metric).
#### The Tangent Connection (Levi-Civita)
We define the covariant derivative $\nabla$ on $TM$ by differentiating in the ambient space and projecting back to the tangent space: $$\nabla_X Y := P(D_X Y), \quad X, Y \in \mathfrak{X}(M)$$
#### Concrete Case: The 2-Sphere $S^2 \subset \mathbb{R}^3$
Let $S^2 = \{ p \in \mathbb{R}^3 : \|p\|^2 = 1 \}$. The projection $P$ is given by $P_p(v) = v - \langle v, p \rangle p$.
- **Example Computation**: Let $Y(p)$ be a tangent vector field. To find $\nabla_X Y$, we compute the standard directional derivative of the components of $Y$ in $\mathbb{R}^3$ and then subtract the component normal to the sphere.
- **Insight**: If we take a "straight" vector field in $\mathbb{R}^3$ and restrict it to $S^2$, its $D$-derivative is zero. However, its $\nabla$-derivative is non-zero because the projection $P$ changes as we move along the sphere. This demonstrates that the connection encodes the "bending" of the manifold within the ambient space.
> Theoretical Tool: The Second Fundamental Form
> 
> The "error" between the ambient derivative and the intrinsic connection is captured by the second fundamental form $B(X, Y) = D_X Y - \nabla_X Y$. This tool is essential for relating the intrinsic geometry of a bundle/manifold to its extrinsic embedding.