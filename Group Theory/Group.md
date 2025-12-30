**Group as ontology of action**: a group is more than a set of algebraically related elements - it's a collection of symmetries of some set $X$ in a [[Category]] that is acted upon via [[Group Action]], which formed a [[Symmetric Group]]. 

---
A **group** is a tuple $(G,\cdot)$ where $\cdot:G\times G\to G$ (abbreviate $a\cdot b$ as $ab$) satisfies
1. **Associativity**: $(ab)c=a(bc)$ 
2. **Existence of (unique) identity**: $\exists e\in G$ s.t. $ea=ae=a,\forall a\in G$.
3. **Existence of (unique) inverse**: $\exists a^{-1}\in G$ s.t. $aa^{-1}=a^{-1}a=e$.
	- The operation always satisfies $(ab)^{-1}=b^{-1}a^{-1}$. 
$G$ is said to be **abelian** (**commutative**) if the operation is commutative, i.e. $ab=ba,\forall a,b\in G$. When existence of inverse is not guaranteed we can it a **monoid**.
- **Equivalent characterization**: conditions 2, 3 can be replaced by existence of left (right) identity and inverse.
  **Proof**: assume that right inverse and identity exists. For $a\in G$ we pick $ab=bc=e$, then $$eae=ae\quad\Longrightarrow\quad(ab)a(bc)=ea\quad\Longrightarrow\quad ec=ea$$Similarly from $ae=a$ we deduce $ec=a$, which implies $ea=a$. This further implies $a=c$.
	- **Discussion**: the fact that single-sided condition is sufficient for structure of group appears more clear under the Yoneda lemma above.
- **Order**: the order of an element $g\in G$ is defined as $$|g|=\underset{n\in\mathbb N}{\arg\min}\ x^n=1$$When such $n$ does not exists, we define $|x|=\infty$. By Euclidean algorithm ([[Euclidean Domain]]) applied on the exponent we have that $$\set{n\in\mathbb N:g^n=1}=\set{k|g|:k\in\mathbb N}$$this is useful in many discussion on order of an element. 
	- **Order in finite group**: by uniqueness of inverse we know that $$G=gG\quad\Longrightarrow\quad\prod_{g'\in G}g'=\prod_{g'\in G}gg'=g^{|G|}\prod_{g'\in G}$$by the cancelation law we have $g^{|G|}=1$, therefore we must have $|g|\mid|G|$ ([[Division]]). This can also be derived from Lagrange's theorem, noticing $\braket{g}\le G$.
	- **Group with elements having prescribed order**: for any $m,n,r>1$, we can construct a group with element $a,b$ such that $|a|=m,|b|=n,|ab|=r$. Example can be constructed within $\sl_2(F_q)$ for some prime power $q$. 
- **Rank**: denoted $\rank G$, is the smallest cardinality of the generating set of $G$:$$\rank G=\min\{|X|:X\subset G,\langle X\rangle=G\}$$This is similar to the notion of dimension for [[Vector Space]]. Notice that for $H\le G$ we might have $\rank H>\rank G$ (e.g., $\mathbb Z$ and $\braket{4,6}$ under natural addition), hence we also define $$\operatorname{sr}G=\max_{H\le G}\rank H$$as the **subgroup rank** of $G$. 
	- **Free rank**: for non-free abelian group $G$ we define its free rank as the rank of its free abelian subgroup whose quotient group is a **torsion group** (a group in which every element has finite order).
	- **Rank of abelian group**: given $G$ abelian, we can also define $\rank G$ as the [[Cardinality]] of its maximal $\mathbb Z$-linearly independent subset.
		- **Well-defined and equivalence**: for two maximal $\mathbb Z$-linearly independent subset  $\set{g_i}_{i=1}^n,\set{h_j}_{j=1}^m$ with $m>n$, by adding each $h_j$ into $\set{g_i}$ we can find $$h_j=\sum_{i}a_{ij}g_i\quad\Longrightarrow\quad\begin{pmatrix}h_1\\\vdots\\ h_m\end{pmatrix}=[a_{ij}]_{m\times n}\begin{pmatrix}g_1\\\vdots\\ g_n\end{pmatrix}$$hence by [[Matrix]] we must have $\set{h_j}_{j=1}^m$ linearly dependent, which is a contradiction. For equivalence with the definition of rank of a general group just notice that a subset is maximally $\mathbb Z$-linearly independent iff it's a minimal generator.
## Subgroups
A **subgroup** $H\le G$ is a subset $H\subset G$ s.t. $(H,\cdot)$ forms a group. We have the **subgroup criterion** $$H\le G\quad\iff\quad ab^{-1}\in H,\quad\forall a,b\in H$$which is derived directly from definition. We'll conventionally use the notations $$\sub G=\set{H:H\le G},\quad\sub_KG=\set{H:K\le H\le G}$$Note that other notations like $\mathcal S(G)$ are also used instead. 
- **Coset**: by invertibility we can verify that $$aH=bH\quad\iff\quad aH\cap bH\neq\varnothing\quad\iff\quad a\in bH\quad\iff\quad b^{-1}a\in H$$Hence we can define **left cosets** via quotient w.r.t the equivalence relation ([[Set]]) $$G/H=G/\sim\where a\sim b\iff aH=bH$$Any $b\in aH$ is called a **representative** of $aH$. Similarly we can define the **right cosets**, denoted as  $H\backslash G$. 
	- **Discussion on equipartition**: invertibility assumption (therefore, the cancelation law) ensures that the cosets are copies of "rigid translations" without any "overlap", and this symmetry is one key source of special structural properties related to groups. 
	- **Discussion on left/right cosets**: it worth noting that multiplication in the left/right results in different left/right cosets that cannot be corresponded in general. For instance, in the [[Symmetric Group]] $S_3$ set $$H=\set{e,(12)}\imply\begin{cases}\text{Left cosets}\begin{cases}(13)H=\set{(13),(123)}\\(23)H=\set{(23),(132)}\end{cases}\\\text{Right cosets}\begin{cases}H(13)=\set{(13),(132)}\\H(23)=\set{(23),(123)}\end{cases}\end{cases}$$Therefore the best we can say in general is that the partition is uniform, but exactly how each class looks like is quite complicated. 
- **Index**: by uniform partition above we have $|H|\mid|G|$, hence we can define the index of $H$ as $$|G:H|=|G/H|$$which is the number of cosets of $H$ in $G$. 
	- **Tower law**: for $K\le H\le G$ we have $$|G:K|=|G:H|\cdot|H:K|$$Here $|\cdot|$ is the [[Cardinality]], interpreted as a bijection between LHS and RHS.
	  **Proof**: denote the canonical projections into equivalence class ([[Set]]) as  $$\iota:G\to K,\quad\iota_1:G\to H,\quad\iota_2:H\to K$$then we can easily verify that $\iota=\iota_2\circ\iota_1$, which implies, for any fixed $k\in K$, that $$\iota^{-1}(k)=\bigsqcup_{h\in\iota_2^{-1}(k)}\iota_1^{-1}(h)$$meanwhile, the canonical bijection between cosets yields the isomorphism $$G/K\cong\iota^{-1}(k),\quad G/H\cong\iota_1^{-1}(h),\quad H/K\cong\iota_2^{-1}(k)$$the results above, combined together, completes the proof. 
	- **Lagrange's theorem**: by taking $K=\set{1}$ we can deduce from the tower law that $$|G| = |G:H|\cdot |H|$$which is usually called the Lagrange's theorem. 
	- **Orbit-stabilizer theorem**: Let $G$ acts on $X$, then $|\orb(x)|=|G:\stab(x)|,\forall x\in X$.
		- As a corollary, $|\cl(x)|=|G:C(x)|$. This is shown with acting by conjugacy.
- **Centralizer**: $C_G(g)$ consists of elements that commutes with $g$, i.e., $$C_G(g) =\set{x \in G: xg = gx}$$The **center** of $G$ is defined as $$Z(G) =\bigcap_{g\in G}C_G(g)=\set{x\in G:xg=gx,\forall g\in G}$$
- **Normalizer**: $N_G(H) =\{g \in G \mid gHg^{-1} = H\}$ is the set of elements that "normalize" $H$. We have $H\le N_G(H)\le G$ by definition of subgroup.
- **Stabilizer**: $G_x=\stab x=\set{g \in G:gx = x}\le G$. 
- **Subgroup generated by a subset**: for any $S \subseteq G$ we define $$\braket{S}=\bigcap_{S\subset H\le G}H\le G$$It's the smallest subgroup in $G$ containing $S$. More can be found in [[Group Representation]]. 
- **Maximal subgroup**: $M\subsetneq G$ is maximal if $M< H\le G\implies H=G$. 
	- For $G$ abelian, $H\le G$ is maximal iff $|G:H|=p$ where $p$ is a prime.
	- $N\triangleleft G$ is maximal iff $G/N$ is simple.
	- **Frattini subgroup**: $\Phi(G)$ is the **intersection of all maximal subgroups** of finite $G$.
		- Since conjugates of maximal subgroup are maximal, $\Phi(G)\triangleleft G$.
		- As automorphism preserves maximal subgroup, we actually have $\Phi(G)\operatorname{char}G$.
		- **Frattini subgroup contains all non-generators**, i.e., elements that can be always be removed from a generating set (the equivalence between this definition and the above one can be verified by considering whether $X$ and $X\cup\{g\}$ generates $G$). Formally, we have $$\langle a_1,\cdots,a_n\rangle=G\quad\text{iff}\quad\langle a_1\Phi(G),\cdots,a_n\Phi(G)\rangle=G/\Phi(G)$$
		- See properties of Frattini subgroup of p-group in [[Group Gallery]].
- **Avoidance lemma**: given $H,K< G$ we have $G\neq H\cup K$.
  **Proof**: WLOG assume that $H\triangle K\neq\varnothing$, take $a\in H-K,b\in K- H$, then if $G=H\cup K$ we must have $ab\in H$ or $ab\in K$, where either case would lead to a contradiction.
### Lattice of subgroups
The lattice of subgroups of a group $G$ is the lattice whose elements are the subgroups of $G$. with the partial ordering being set inclusion.
![[Pasted image 20241212165429.png]]
- By the lattice theorem, there is a Galois connection between the lattice of subgroups of a group $G$ and that of its quotients $G/N$ for some $N\triangleleft G$. [[Group Homomorphism]]
- **Normal subgroup lattice**: normal subgroups forms a modular [[Lattice]]. 
- **Subgroup lattice and structure of group**: a specific group has a unique subgroup lattice, as the inclusion relation between all subgroups are fixed. However, given a subgroup lattice it's hard to establish the structure of the group itself.
	- **Non-isomorphic groups may share the same lattice structure**: consider $C_p,C_q$ where $p,q$ are primes, then they share the same lattice structure. Even stronger conditions, say, the same order of the group, lattice of normal subgroups, automorphism group, combined together, would not guarantee that two groups are isomorphic.
## Other info
### Topological group
A **topological group** is a triple $(G,\cdot,\mathcal T_G)$ consisting of:
1. **Group structure**: $(G,\cdot)$ is a group. 
2. **[[Topological Space]]**: $(G,\mathcal T_G)$ is a topological space, called the **group topology**. 
	1. **Compatibility condition**: the group operation $\cdot$ and inverse $g\mapsto g^{-1}$ are [[Continuous Function]] under the corresponding topology ($\mathcal T_G\times\mathcal T_G$ and $\mathcal T_G$, resp.). 
- **Locally compact topological group**: 