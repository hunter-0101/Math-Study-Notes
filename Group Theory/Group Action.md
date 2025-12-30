A **group action** of [[Group]] $G$ on a set ([[Set]]) $X$ is a function $$G\act X: G \times X \to X$$satisfying the follow properties:
1. **Compatibility**: $g(hx) = (gh)x,\forall g,h\in G,x\in X$. 
2. **Identity action**: $ex=x,\forall x\in X$ where $e$ is the identity element in $G$. 
Group action provides a simple, controllable way to investigate the object under action, as well as the structure of the group itself. 
- **Discussion**: group action is one of the main source of inspiration for the definition of [[Group]], since the action of permuting elements in a set forms a well-behaved algebraic structure ([[Symmetric Group]]) that can be studied systematically. The algebraic structure (dynamic) of a group can only be **revealed by acting it upon some object**. This also resonates (and actually motivated) the [[Category]] definition of group. 
- **Permutation representation**: the action $G\act X$ defines a [[Group Homomorphism]] $$\rho:G\to S_X$$The cyclic notation ([[Symmetric Group]]) of these permutations are called the **permutation representation** of the group $G$ over $X$. 
- **Faithfulness**: the action $G\act X$ is faithful if $$g_1\neq g_2\imply\exists x\in X\ \st\ g_1 x\neq g_2x$$Intuitively it says that we can uniquely identify group elements by their effect on the set. 
## Basic concepts
Below we go over some basic concepts related to a group action, and also record some of their important properties. 
- **Orbit**: The orbit of $x \in X$ under the action of $G$ is defined as the set $$O_x=\orb x = \set{gx\in X:g \in G}$$The **orbit partition** is defined via the set quotient ([[Set]]) $$X/G=X/\sim\where x\sim y\qiffq y\in\orb x$$This partition clarifies the structure of the action. 
    - **Transitivity**: the action of $G$ on $X$ is transitive if $\orb x=X$, i.e., there is only one orbit. 
- **Stabilizer**: The stabilizer of $x \in X$ is defined as the set $$G_x=\stab x =\set{g \in G:gx = x}$$We can verify that $G_x\le G$ by the subgroup criterion ([[Group]]).
	- **Free action**: the action of $G$ on $X$ is **free** if $G_x=\varnothing,\forall x\in X$.
	- **Orbit-stabilizer theorem**: Let $G$ acts on $X$, then we have $$|O_x|=|G:G_x|$$**Proof**: notice that we have the bijection $$G/G_x\leftrightarrow O_x,\qtextq{given by} g\cdot G_x\mapsto gx$$The desired theorem follows naturally. 
		- **Corollary**: by Lagrange's theorem ([[Group]]) we have $$|G|=|G_x|\cdot|O_x|,\quad\forall x\in X$$This is quite useful in some cases. 
		- **Discussion**: orbit-stabilizer theorem is **local** - it focuses on the action upon only one element $x\in X$, and says nothing about relations across different orbits. and in general there could many orbits of different length. For instance, check out the class equation (below) and its applications (like in [[Sylow Theorems]]). 
- **Fixed points**: the set of fixed points of $g\in G$ is denoted as $$X^g=\set{x\in X:gx=x}$$This is mainly used in [[Galois Extension]]. 
## Important results
- **Cayley's theorem**: the action $G\act G$, by invertibility, defines an isomorphism $$\rho:G\to S_{|G|}$$In this manner $G$ is embedded into a subgroup of $S_{|G|}$. 
- **Burnside's lemma**: given $G\act X$ where $X$ is a set ([[Set]]), there is a bijection $$G\times X/G\longleftrightarrow\coprod_{g\in G}X^g$$**Proof**: consider the set of fixed point pairs $$S=\set{(g,x)\in G\times X:gx=x}$$obviously we have two canonical partitions $$\coprod_{x\in X}G_x\cong S\cong\coprod_{g\in G}X^g$$meanwhile, notice that $$\coprod_{x\in X}G_x\cong\coprod_{O\in X/G}\coprod_{x\in O}G_x$$hence now the problem reduces to proving that there exists a bijection $$\coprod_{x\in O}G_x\cong G$$which is obvious by the orbit-stabilizer theorem above.
	- **Finite case**: for $G$ finite the above bijection degenerates to an identity $$|X/G|=\frac{1}{|G|}\sum_{g\in G}|X^g|$$and the proof is even more intuitive: $$\sum_{g\in G}|X^g|=|S|=\sum_{x\in X}|G_x|=\sum_{x\in X}\frac{|G|}{|O_x|}=|G|\sum_{x\in X}\frac{1}{|O_x|}=|G|\cdot|X/G|$$where the fraction is derived directly from the orbit-stabilizer theorem.
## Action by conjugation
The action of $G$ on itself by conjugation is defined as $h\cdot g = hgh^{-1}$ for $g,h\in G$. 
- **Intuition**: action by conjugation arises naturally as the change of basepoint formula in the fundamental group ([[Homotopy]]). It generalizes the change of basis formula in [[Vector Space]], illustrating how the group is like when "**viewed from another perspective**". More concretely, it describes exactly how each $g$ should be "presented" under a **faithful** action $$G\act X:x\mapsto hx$$Therefore it's a natural **group version "change of basis" formula**. 
- **Conjugacy class**: the conjugacy class of an element $x \in G$ is the set $$\cl g\coloneqq O_g=\set{hgh^{-1}: h \in G}$$Notice that conjugacy is an equivalence relation. 
	- **Structural similarity**: elements in the same conjugacy class are **structurally similar**, and therefore cannot be distinguished by the group structure alone, i.e., looks exactly the same under some faithful action. For instance, in $S_3$ we have $$(12)\circ(123)\circ(12)=(132)=(23)\circ(123)\circ(23)$$and $(123)$ can be changed to $(132)$ by swapping the indexes $2,3$. 
	- The number of conjugates of a subset $S$ in a group $G$ is the index of the normalizer of $S$, $|G:N_G(S)|$. 
    - **Order invariance**: $a^k\sim b^k,\forall a,b\in\cl x,k\in\mathbb N$, hence elements is the same conjugacy class has the sane order.
- **Class equation**: the orbit-stabilizer theorem in this case becomes $$|\cl g|=|G:C_G(g)|$$Applying the addition principle ([[Counting]]) we get the **class equation**$$|G| = |Z(G)| + \sum_i|G:C_G(g_i)|$$where the summation runs over the set of representatives of all conjugacy classes. 
- **Conjugacy in $S_n$**: Two elements in the symmetric group $S_n$ are conjugate if and only if they have the same cycle type.
	- For $\sigma\in S_n$, if it is product of disjoint cycles of lengths $n_1,\cdots,n_r$, then the integers $n_1,\cdots,n_r$ are called the **cycle type** of $\sigma$.
    - This result is obtained by the observation that $\tau\sigma\tau_{-1}$ has the same cycle type with $\sigma$.
- **Right Group Actions**: Similarly to left group actions, a right group action is a function $X \times G \to X$ satisfying $(xg)h = x(gh)$ and $xe = x$. Right actions are less common but equally important. 