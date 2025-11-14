A **group action** of [[Group]] $G$ on a set $X$ is a function $G \times X \to X$ s.t. $$g(hx) = (gh)x,\quad\forall g,h\in G,x\in X\quad\text{and}\quad ex=x\quad\forall x\in X$$A **permutation representation** of $G$ is a homomorphism $$\rho:G\to S_X$$by properly labeling the elements in $X$.
- **Orbit**: The orbit of $x \in X$ under the action of $G$ is defined as the set $$O_x=\mathrm{Orb}(x) = \set{gx\in X:g \in G}$$The orbit partition $X/G$, which is obviously an equivalence relation, clarifies the structure of the action.
    - **Transitivity**: we say that action of $G$ is transitive if there is only one orbit. 
- **Stabilizer**: The stabilizer of $x \in X$ is defined as the set $$G_x=\stab(x) =\set{g \in G:gx = x}\le G$$Here the fact that $\stab(x)\le G$ follows from the subgroup criterion. [[Group]]
	- **Free action**: we say that action of $G$ is **free** if $\stab(x)=\varnothing,\forall x\in X$.
	- **Orbit-stabilizer theorem**: Let $G$ acts on $X$, then we have the bijection $$G/\stab(x)\cong\orb(x),\quad g\cdot\stab(x)\mapsto gx$$hence we establish the orbit-stabilizer theorem $$|\orb(x)|=|G:\stab(x)|$$which can be seen as a generalized Lagrange's theorem ([[Group]]). 
- **Fixed point**: given any $g\in G$ we denote the elements fixed under $g$ as $$X^g=\set{x\in X:gx=x}$$which is obviously a subset of $X$.
- **Cayley's theorem**: any group $G$ is isomorphic to some $H\le S_G$ by considering the group action $G\act G$ by left multiplication. 
	- Let $H\le G$ and let $G$ act on $A=\set{gH|g\in G}$. Let $\pi_H$ be the associated permutation representation induced by this action, then
		- $G$ acts transitively on $A$.
		- the stabilizer in $G$ of the point $1H\in A$ is the subgroup $H$.
		- the kernel of the action is the core of $H$: $$Core_G(H)=\bigcap_{g\in G}gHg^{-1}$$which is the largest normal subgroup of $G$ contained in $H$.
- **Burnside's lemma**: given $G\act X$ where $X$ is a set ([[Set Theory]]), there is a bijection $$G\times X/G\longleftrightarrow\coprod_{g\in G}X^g$$**Proof**: consider the set of fixed point pairs $$S=\set{(g,x)\in G\times X:gx=x}$$obviously we have two canonical partitions $$\coprod_{x\in X}G_x\cong S\cong\coprod_{g\in G}X^g$$meanwhile, notice that $$\coprod_{x\in X}G_x\cong\coprod_{O\in X/G}\coprod_{x\in O}G_x$$hence now the problem reduces to proving that there exists a bijection $$\coprod_{x\in O}G_x\cong G$$which is obvious by the orbit-stabilizer theorem above.
	- **Finite case**: for $G$ finite the above bijection degenerates to an identity $$|X/G|=\frac{1}{|G|}\sum_{g\in G}|X^g|$$and the proof is even more intuitive: $$\sum_{g\in G}|X^g|=|S|=\sum_{x\in X}|G_x|=\sum_{x\in X}\frac{|G|}{|O_x|}=|G|\sum_{x\in X}\frac{1}{|O_x|}=|G|\cdot|X/G|$$where the fraction is derived directly from the orbit-stabilizer theorem.
## Action by conjugation
The action of $G$ on itself by conjugation is defined as $g \cdot x = gxg^{-1}$ for $g, x \in G$. 
- **Conjugacy Classes**: The conjugacy class of an element $x \in G$ is the set $$\cl(x)=\{gxg^{-1} \mid g \in G\}$$Notice that conjugacy is an equivalence relation. Elements in the same conjugacy class are structurally similar.
	- The number of conjugates of a subset $S$ in a group $G$ is the index of the normalizer of $S$, $|G:N_G(S)|$. 
    - **Order invariance**: $a^k\sim b^k,\forall a,b\in\cl(x),k\in\mathbb N$, hence elements is the same conjugacy class has the sane order.
- **Class equation**: the orbit-stabilizer theorem in this case becomes $$|\cl(g)|=|G:C_G(g)|$$by separating the conjugacy class of distinct elements we get the **class equation**$$|G| = |Z(G)| + \sum_i|G:C_G(x_i)|$$
- **Conjugacy in $S_n$**: Two elements in the symmetric group $S_n$ are conjugate if and only if they have the same cycle type.
	- For $\sigma\in S_n$, if it is product of disjoint cycles of lengths $n_1,\cdots,n_r$, then the integers $n_1,\cdots,n_r$ are called the **cycle type** of $\sigma$.
    - This result is obtained by the observation that $\tau\sigma\tau_{-1}$ has the same cycle type with $\sigma$.
- **Right Group Actions**: Similarly to left group actions, a right group action is a function $X \times G \to X$ satisfying $(xg)h = x(gh)$ and $xe = x$. Right actions are less common but equally important.
- **==Group action is a great way to define a homomorphism==**.