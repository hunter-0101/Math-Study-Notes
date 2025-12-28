**Intuition**: a group $G$ in the usual concrete form is actually a **shadow** of a more abstract and structural notion of symmetry, a specific representation **evaluated** on a specific object of the actual **generator of symmetries**. 
- **[[Distribution]] analogy**: in distribution theory a distribution is defined not via point value, but how it acts on test functions via integration. Similarly, a group does not inherently carries structures until it acts on some object. To put simply, we state that $$\text{A group can be understood in terms of its actions on all possible sets.}$$This idea is formalized by [[Yoneda Lemma]]: consider the single object [[Category]] $*_G$ given a group $G$, then a functor $F:*_G\to\textbf{Set}$ realizes (left) [[Group Action]] of $G$ on $X=F(*_G)$. Since $h_*=\hom(*,-)\cong G$, while Yoneda lemma states that $$\nat(h_*,F)\cong F(*)=X$$Hence $F$ is a group action on $X$, and a natural transformation $\mu:h_*\to F$ is determined by $\mu(\id_*)\in X$. This means that the space of natural transformations from the regular actions (self-action) to an arbitrary group action corresponds exactly to the underlying set $X$ that the group acts on.
	- **General definition of group**: a group can be defined as a single object category where all morphisms are isomorphisms, with closure of group operation deriving from the composition axiom of category. In general a category where all morphisms are isomorphisms is referred to as a **groupoid**. 
- **[[Matrix]] analogy**: in matrix theory we treat a matrix as the representation of a linear transform given a specific basis ([[Vector Space]]). Similarly, a group can be viewed as a specific representation of symmetry evaluated a specific object, as discussed above, validated by the Yoneda lemma. 
	- **Information collapse under evaluation**: when $F$ is not faithful the image $X=F(*_G)$ might be strictly "smaller" then the structure of $\ob(*_G)$, causing information collapse, e.g., when $G=\set{e,a},F:*_G\to X=\set{x}$ the new group evaluated on $X$ turn out to be $\set{e}$, and we cannot distinguish between the two morphisms $e,a$. Formally, this is due to the fact that $G\to S_X$ is not injective ([[Group Action]]). The cases where information collapse does not happen is referred to as **faithful representation**.
The above discussion also provides some insights about standings of functional and matrices: 
- **Functionals** are maps from a function space to $\mathbb R$.
- **Matrices** are linear maps between vector spaces $A:V\to W$.
Both are **representations**: they make abstract transformations concrete by pinning them to a specific coordinate system (test function or basis).

---
A **group** is an ordered pair $(G,\cdot)$ where $\cdot:G\times G\to G$ (abbreviate $a\cdot b$ as $ab$) satisfies
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
- **Rank**: denoted $\rank G$, is the smallest cardinality of the generating set of $G$:$$\rank G=\min\{|X|:X\subset G,\langle X\rangle=G\}$$This is similar to the notion of dimension for [[Vector Space]]. Notice that for $H\le G$ we might have $\rank H>\rank G$ (e.g., $\mathbb Z$ and $\braket{3,5}$ under natural addition), hence we also define $$\operatorname{sr}G=\max_{H\le G}\rank H$$as the **subgroup rank** of $G$.
	- **Free rank**: for non-free abelian group $G$ we define its free rank as the rank of its free abelian subgroup whose quotient group is a **torsion group** (a group in which every element has finite order).
	- **Rank of abelian group**: given $G$ abelian, we can also define $\rank G$ as the [[Cardinality]] of its maximal $\mathbb Z$-linearly independent subset.
		- **Well-defined and equivalence**: for two maximal $\mathbb Z$-linearly independent subset  $\set{g_i}_{i=1}^n,\set{h_j}_{j=1}^m$ with $m>n$, by adding each $h_j$ into $\set{g_i}$ we can find $$h_j=\sum_{i}a_{ij}g_i\quad\Longrightarrow\quad\begin{pmatrix}h_1\\\vdots\\ h_m\end{pmatrix}=[a_{ij}]_{m\times n}\begin{pmatrix}g_1\\\vdots\\ g_n\end{pmatrix}$$hence by [[Matrix]] we must have $\set{h_j}_{j=1}^m$ linearly dependent, which is a contradiction. For equivalence with the definition of rank of a general group just notice that a subset is maximally $\mathbb Z$-linearly independent iff it's a minimal generator.
## Dual group for abelian group
A **character** of abelian $G$ is a [[Group Homomorphism]] $\chi:G\to S^1=\set{z\in\mathbb C:|z|=1}$. Collection of characters of $G$ form the **dual group** $G^\vee$ under addition defined by $(\chi+\chi')(g)=\chi(g)\chi'(g)$.
- **Duality relation**: for $G$ finitely-generated abelian, we have $G\cong G^\vee$.
  **Proof**: the result is obvious for cyclic groups, while for any two groups $H,K$ notice $$\chi\in(H\times K)^\vee\quad\Longrightarrow\quad\chi(h,k)=\chi(h,e_K)\chi(e_H,k)=\phi_H(h)\psi_K(k)$$hence we have the isomorphism $$(H\times K)^\vee\cong H^\vee\times K^\vee,\quad\phi\times\psi\leftrightarrow(\phi,\psi)$$By primary decomposition of finitely generated abelian group ([[Product of Groups]]) we establish the result for arbitrary finitely generated abelian group. 
- **Orthogonality relations**: let $G$ be a finite abelian group, the for any $\chi,\psi\in G^\vee$ we have $$\sum_{a\in G}\chi(a)\psi(a^{-1})=\begin{cases}|G|,&\text{if } \chi=\psi\\0,&\text{otherwise}\end{cases}$$this theorem directly yields $\sum_{a\in G}\chi(a)=|G|$ if $\chi$ is trivial, and $0$ otherwise.
  **Proof**: the first case is obvious. For $\chi\neq\psi$, there exists $b\in G,\chi(b)\neq\psi(b)$. Now as when $a$ run through $G$, $ab$ also run through $G$, thus we have $$\sum_{a\in G}\chi(a)\psi(a^{-1})=\sum_{a\in G}\chi(ab)\psi((ab)^{-1})=\chi(b)\psi(b)^{-1}\sum_{a\in G}\chi(a)\psi(a^{-1})$$now that $\chi(b)\psi(b)^{-1}\neq1$, we have that the sum equals $0$.
	- If we apply this theorem to $G^\vee$ we get $$\sum_{\chi\in G^\vee}\chi(a) =\begin{cases}|G|&\text{if } a=e\\0&\text{otherwise}\end{cases}$$
## Subgroups
A **subgroup** $H\le G$ is a subset $H\subset G$ s.t. $(H,\cdot)$ forms a group. We have the **subgroup criterion** $$H\le G\quad\iff\quad ab^{-1}\in H,\quad\forall a,b\in H$$which is derived directly from definition.
- **Coset**: by invertibility we can verify that $$aH=bH\quad\iff\quad aH\cap bH\neq\varnothing\quad\iff\quad a\in bH\quad\iff\quad b^{-1}a\in H$$Hence we can define **left cosets** via quotient w.r.t the equivalence relation ([[Set Theory]]) $$G/H=G/\sim\where a\sim b\iff aH=bH$$Any $b\in aH$ is called a **representative** of $aH$. Similarly we can define the **right cosets**, denoted as  $H\backslash G$. 
	- **Discussion on equipartition**: invertibility assumption (therefore, the cancelation law) ensures that the cosets are copies of "rigid translations" without any "overlap", and this symmetry is one key source of special structural properties related to groups. 
- **Index**: by uniform partition above we have $|H|\mid|G|$, hence we can define the index of $H$ as $$|G:H|=|G/H|$$which is the number of cosets of $H$ in $G$. 
	- **Tower law**: for $K\le H\le G$ we have $$|G:K|=|G:H|\cdot|H:K|$$Here $|\cdot|$ is the [[Cardinality]], interpreted as a bijection between LHS and RHS.
	  **Proof**: denote the canonical projections into equivalence class ([[Set Theory]]) as  $$\iota:G\to K,\quad\iota_1:G\to H,\quad\iota_2:H\to K$$then we can easily verify that $\iota=\iota_2\circ\iota_1$, which implies, for any fixed $k\in K$, that $$\iota^{-1}(k)=\bigsqcup_{h\in\iota_2^{-1}(k)}\iota_1^{-1}(h)$$meanwhile, the canonical bijection between cosets yields the isomorphism $$G/K\cong\iota^{-1}(k),\quad G/H\cong\iota_1^{-1}(h),\quad H/K\cong\iota_2^{-1}(k)$$the results above, combined together, completes the proof. 
	- **Lagrange's theorem**: by taking $K=\set{1}$ we can deduce from the tower law that $$|G| = |G:H|\cdot |H|$$which is usually called the Lagrange's theorem. 
	- **Orbit-stabilizer theorem**: Let $G$ acts on $X$, then $|\orb(x)|=|G:\stab(x)|,\forall x\in X$.
		- As a corollary, $|\cl(x)|=|G:C(x)|$. This is shown with acting by conjugacy.
- **Centralizer**: $C_G(g)$ consists of elements that commutes with $g$, i.e., $$C_G(g) =\set{x \in G: xg = gx}$$The **center** of $G$ is defined as $Z(G) =\bigcap_{g\in G}C_G(g)=\set{x\in G:xg=gx,\forall g\in G}$.
- **Normalizer**: $N_G(H) =\{g \in G \mid gHg^{-1} = H\}$ is the set of elements that "normalize" $H$. We have $H\le N_G(H)\le G$ by definition of subgroup.
- **Stabilizer**: $\text{Stab}(x) =\set{g \in G:gx = x}\le G$. 
- **Subgroup Generated by Subset of a Group**: given $S \subseteq G$, define $\langle S \rangle\le G$ as $$\braket{S}=\bigcap_{S\subset H\le G}H$$i.e.,the smallest subgroup that contains $S$.
- **Maximal subgroup**: $M\subsetneq G$ is maximal if there exists no proper subgroup $H$ such that $M\subsetneq H\subsetneq G$.
	- For $G$ abelian, $H\le G$ is maximal iff $|G:H|=p$ where $p$ is a prime.
	- $N\triangleleft G$ is maximal iff $G/N$ is simple.
	- **Frattini subgroup**: $\Phi(G)$ is the **intersection of all maximal subgroups** of finite $G$.
		- Since conjugates of maximal subgroup are maximal, $\Phi(G)\triangleleft G$.
		- As automorphism preserves maximal subgroup, we actually have $\Phi(G)\operatorname{char}G$.
		- **Frattini subgroup contains all non-generators**, i.e., elements that can be always be removed from a generating set (the equivalence between this definition and the above one can be verified by considering whether $X$ and $X\cup\{g\}$ generates $G$). Formally, we have $$\langle a_1,\cdots,a_n\rangle=G\quad\text{iff}\quad\langle a_1\Phi(G),\cdots,a_n\Phi(G)\rangle=G/\Phi(G)$$
		- See properties of Frattini subgroup of p-group in [[Group Gallery]].
- **Avoidance lemma**: given $H,K< G$ we have $G\neq H\cup K$.
  **Proof**: WLOG assume that $H\triangle K\neq\varnothing$, take $a\in H-K,b\in K- H$, then if $G=H\cup K$ we must have $ab\in H$ or $ab\in K$, where either case would lead to a contradiction.
## Normal subgroup & quotient group
A subgroup $H\le G$ is normal if $$H\triangleleft G\qiffq N_G(H)=G$$There are several equivalent characterizations for this that are useful:
1. **Invariance under conjugation**: $g^{-1}hg\in H,\forall g,\in G,h\in H$. [[Group Action]]
2. **Coset definition**: $gH=Hg,\forall g\in G$, i.e., the left and right coset coincide.
3. **Kernel characterization**: there exist a homomorphism $\phi$ s.t. $\ker\phi=H$. 
4. **Subgroup of normal subgroup**: there exist a $K$ such that $H\le K\triangleleft G$.
Intuitively, the property of being normal implies that **group operations are compatible with taking quotient**, therefore the collection $G/H$ itself forms another group. 
- **Quotient group**: given $N\triangleleft G$ the collection of cosets $G/N$ with operations $$(aN)(bN)=(ab)N,\quad(aN)^{-1}=a^{-1}N$$is called the quotient group of $G$ w.r.t $H$. 
## Lattice of subgroups
The lattice of subgroups of a group $G$ is the lattice whose elements are the subgroups of $G$. with the partial ordering being set inclusion.
![[Pasted image 20241212165429.png]]
- By the lattice theorem, there is a Galois connection between the lattice of subgroups of a group $G$ and that of its quotients $G/N$ for some $N\triangleleft G$. [[Group Homomorphism]]
- **Normal subgroup lattice**: normal subgroups forms a modular lattice. [[Lattice]]
- **Subgroup lattice and structure of group**: a specific group has a unique subgroup lattice, as the inclusion relation between all subgroups are fixed. However, given a subgroup lattice it's hard to establish the structure of the group itself.
	- **Non-isomorphic groups may share the same lattice structure**: consider $C_p,C_q$ where $p,q$ are primes, then they share the same lattice structure. Even stronger conditions, say, the same order of the group, lattice of normal subgroups, automorphism group, combined together, would not guarantee that two groups are isomorphic.
## Group extension
For two groups $Q,N$, a group $G$ is the extension of $Q$ by $N$ if there is an exact sequence of homomorphisms $$1\to N\xto{\iota}G\xto{\pi} Q\to1$$with $i$ injective and $\pi$ surjective, and $\ker\pi=\operatorname{Im}i$. Thus we have that $G/i(N)\cong Q$.
- **Central extension**: an extension is central if $i(N)\subset Z(G)$. Say, the extension $$1\to N\to N\rtimes_\theta Q\to Q\to 1$$defined by semi-direct product is central iff $\theta$ is trivial and $N$ is abelian.
- **Isomorphic extension**: two extensions are isomorphic if there exists a commutative diagram
  <p align="center"><img align="center" src="https://i.upmath.me/svg/%0A%5Cbegin%7Btikzcd%7D%0A1%20%5Carrow%5Br%5D%20%26%20N%20%5Carrow%5Br%5D%20%5Carrow%5Bd%2C%20Rightarrow%2C%20no%20head%5D%20%26%20G%20%5Carrow%5Br%5D%20%5Carrow%5Bd%2C%20%22%5Capprox%22%5D%20%26%20Q%20%5Carrow%5Br%5D%20%5Carrow%5Bd%2C%20Rightarrow%2C%20no%20head%5D%20%26%201%20%5C%5C%0A1%20%5Carrow%5Br%5D%20%26%20N%20%5Carrow%5Br%5D%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%26%20G'%20%5Carrow%5Br%5D%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%26%20Q%20%5Carrow%5Br%5D%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%26%201%0A%5Cend%7Btikzcd%7D%0A" /></p>
  An extension is said to be **split** if it's isomorphic to the extension defined by a semi-direct product. 