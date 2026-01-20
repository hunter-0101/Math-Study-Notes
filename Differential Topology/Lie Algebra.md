Lie group and Lie algebra provides a model for continuous symmetry (e.g., symmetry of a circle). 
**Example**: consider $\gl(n,\mathbb R)$ as a [[Smooth Manifold]] with $\dim\gl(n,\mathbb R)=n^2$ ([[Group Gallery]]). Since matrix multiplication can be written as linear combinations of entries it's $C^\infty$, while smoothness of inverse $\imath$ can be seen via adjacent matrix ([[Matrix]]) and continuity of [[Determinant]]. This makes $\gl(n,\mathbb R)$ a Lie group. Further consider the inclusion $$\iota:\sl(n,\mathbb R)\to\gl(n,\mathbb R)$$We know that $\sl(n,\mathbb R)$ is a regular submanifold as the pre-image of $1$ under $\det$, by the regular level set theorem ([[Smooth Manifold]]). Meanwhile, the composition $$\imath\circ\iota:\sl(n,\mathbb R)\to\gl(n,\mathbb R)\to\gl(n,\mathbb R)$$is $C^\infty$, hence the induced map $\overline\iota:\sl(n,\mathbb R)\to\sl(n,\mathbb R)$ is $C^\infty$. This means $\sl(n,\infty)$ is a Lie group as well. The above arguments also applies to $\gl(n,\mathbb C),\sl(n,\mathbb C)$.

---
Given a [[Field]] $K$, a Lie algebra over $K$ is vector space $V$ over $K$ together with $[\cdot,\cdot]:V\times V\to V$, called the **bracket**, satisfying:
1. **Bilinearity**: $[aX+bY,Z]=a[X,Z]+b[Y,Z],[Z,aX+bY]=a[Z,X]+b[Z,Y]$.
2. **Anti-commutativity**: $[Y,X]=-[X,Y]$.
3. **Jacobi identity**: $\sum_{\text{cyc}}[X,[Y,Z]]=0$.
To put in another way, Lie algebra is an algebra ([[Field]]) over $K$ whose multiplication operation is alternating and satisfies the Jacobi identity.
- **Derivation**: a $K$-linear map $D:V\to V$ is a derivation of Lie algebra $V$ if $$D[X,Y]=[DX,Y]+[X,DY],\quad\forall X,Y\in V$$
## Lie group
A Lie group is a [[Smooth Manifold]] $G$ that is also a group ([[Group]]) s.t. multiplication and inverse $$\mu:G\times G\to G,\mu(a,b)=ab,\quad\quad\imath:G\to G,\imath(a)=a^{-1}$$are both $C^\infty$. We denote $l_a=\mu(a,\cdot),r_a=\mu(\cdot,a)$ the **left/right multiplications**.
- **Lie group homomorphism**: $F:G\to H$ is a Lie group homomorphism if $F\in C^\infty$ and $F$ is a group homomorphism. This is equivalent to $$F\in C^\infty,\quad F\circ l_h=l_{F(h)}\circ F,\quad\forall h\in H$$
- **Lie subgroup**: $H\le G$ is a Lie subgroup if it's an immersed submanifold ([[Smooth Manifold]]) via the inclusion map, and the group operations are $C^\infty$.
	- **Embedded Lie subgroup**: a subgroup that is a regular submanifold is a Lie subgroup, called an embedded Lie subgroup. This is natural since a regular submanifold is of course an immersed submanifold, with well-behaved group operations on it. 
	- **Closed subgroup theorem**: a closed subgroup of a Lie group is an embedded Lie subgroup.