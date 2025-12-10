Let $X$ and $Y$ be [[Vector Space]] over [[Field]] $F$. A **dual pair** (or pairing) is a bilinear map $\langle \cdot, \cdot \rangle: X \times Y \to F$ that separates points:
1. $\forall x \in X, x \neq 0, \exists y \in Y \text{ s.t. } \langle x, y \rangle \neq 0$.
2. $\forall y \in Y, y \neq 0, \exists x \in X \text{ s.t. } \langle x, y \rangle \neq 0$.

The **weak topology $\sigma(X, Y)$** on $X$ induced by $Y$ is the coarsest (smallest) topology on $X$ such that for every fixed $y \in Y$, the linear map $x \mapsto \langle x, y \rangle$ is continuous.
- **Basis of Neighborhoods**: A local basis at $0$ is given by sets of the form: $$U(y_1, \dots, y_n; \epsilon) = \{x \in X : |\langle x, y_i \rangle| < \epsilon, \forall i=1,\dots,n\}$$
- **Hausdorff Property**: Because the pairing separates points, this topology is Hausdorff.
## Connections to Specific Spaces
- **Weak Topology on Normed Spaces**: If $X$ is a normed vector space, the standard "weak topology" refers to $\sigma(X, X^*)$ induced by the natural pairing $\langle x, \phi \rangle = \phi(x)$. (See [[Normed Vector Space]]).
- **Weak* Topology**: If we reverse the roles, looking at the space $Y$ with the topology induced by $X$, we obtain the **Weak* topology** $\sigma(Y, X)$.
    - **Context**: This is most relevant when $Y$ is the dual of some space $Z$ (i.e., $Y=Z^*$), and we consider the topology induced by the pre-dual $Z \subset Z^{**}$.
    - **Key Distinction**: The Weak* topology $\sigma(Z^*, Z)$ is coarser than the Weak topology $\sigma(Z^*, Z^{**})$ because $Z$ is only a subspace of $Z^{**}$ (unless $Z$ is reflexive).