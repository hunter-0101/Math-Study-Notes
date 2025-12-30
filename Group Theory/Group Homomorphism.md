Given two [[Group]] $G,H$, a **group homomorphism** is a function $$\phi: G \to H$$satisfying the property of **preservation of group operation**, i.e., $$\phi(ab)=\phi(a)\phi(b),\quad\forall a,b\in G\imply\phi(e_G)=e_H,\quad\phi\left(a^{-1}\right)=\phi(a)^{-1}$$Two groups with a homomorphism between them is denoted $G\simeq H$. The collection of all homomorphisms from $G$ to $H$ is denoted $\hom(G,H)$. 
- **Intuition**: a homomorphism, by preservation of group operation, translates the algebraic structure from one group to another. One key characteristic is that, the structural information is either **totally preserved** (an isomorphism) or **compressed**, but never enriched. More rigorously speaking, a group homomorphism is a **forgetful functor** ([[Category]]) at the element level. 
- **Kernel**: the kernel of a homomorphism is defined as $$\ker\phi =\set{g \in G: \phi(g) = e_H}$$which is similar to the definition in [[Vector Space]]. 
- **Isomorphism**: an isomorphism is a homomorphism $\phi:G\to H$ that is invertible, i.e., there exists another homomorphism $\psi:H\to G$ s.t. $$\psi\circ\phi=\id_G,\quad \phi\circ\psi=\id_H$$This is equivalent to $\phi$ being bijective, denoted $G\cong H$.
- **Other morphisms**
	- **Monomorphism**: injective homomorphism.
	- **Epimorphism**: surjective homomorphism.
	- **Endomorphism**: a homomorphism from $G$ to itself, i.e., $H=G$. 
	- **Automorphism**: an isomorphic endomorphism. 
- **Fundamental theorem of homomorphism**: given $\phi:G\to H,N\triangleleft G$ with $N\subset\ker\phi$, there exists a unique $\overline\phi:G/N\to H$ s.t. $\phi=\overline\phi\circ\pi$, i.e., the following diagram commutes: 
  <p align="center"><img align="center" src="https://i.upmath.me/svg/%0A%5Cbegin%7Btikzcd%7D%0AG%20%5Carrow%5Br%2C%20%22%5Cphi%22%5D%20%5Carrow%5Bd%2C%20%22%5Cpi%22'%5D%20%26%20H%20%5C%5C%0AG%2FN%20%5Carrow%5Bru%2C%20%22%5Coverline%5Cphi%22'%5D%20%20%20%20%20%20%26%20%20%0A%5Cend%7Btikzcd%7D%0A" /></p>
  and $\im\overline\phi=\im\phi,\ker\overline\phi=\pi(\ker\phi),\ker\phi=\pi^{-1}(\ker\overline\phi)$ where $\pi$ is the **canonical projection**.
	- **Corollary**: $\overline\phi$ is injective iff $N=\ker\phi$; if $\phi$ is surjective then $H\cong G/\ker\phi$. 
## Isomorphism theorems
There are four isomorphism theorems:
1. **First isomorphism theorem**: for the quotient group ([[Normal Subgroup]]) we have $$\phi: G \to H\imply\ker\phi\triangleleft G,\quad G/\ker\phi\cong\im\phi$$**Proof**: $\ker\phi\triangleleft G$ follows directly from the equivalent characterization of [[Normal Subgroup]]; the isomorphism can be taken to be the canonical projection. 
2. **Second isomorphism theorem**: we have the implication $$H \leq G,N \triangleleft G\imply H/(H \cap N) \cong HN/N$$**Proof**: by normality of $N$ we know that $HN=NH$, hence $HN$ is indeed a group, and we can verify by the conjugation characterization ([[Normal Subgroup]]) that $$(H\cap N)\triangleleft H,\quad N\triangleleft HN$$Pick $\pi:G\to G/N$ the canonical projection, and notice that $$\ker\pi|_H=H\cap N,\im\pi|_H=HN/N$$Therefore the theorem follows from the first isomorphism theorem.
3. **Third isomorphism theorem**: we have the implication $$N\triangleleft G,N \triangleleft M\triangleleft G\imply\frac{G/N}{M/N}\cong\frac{G}{M}$$**Proof**: consider the map $$\phi:G/N\to G/M,\quad gN\mapsto gM$$This map is well-defined because $$gN=hN\qiffq g^{-1}h\in N\subset M\imply gM=hM$$and is obviously a homomorphism. Notice that $$gN\in\ker\phi\qiffq g\in M\qiffq gN\in M/N$$Therefore $\ker\phi=M/N$, while $\im\phi=G/M$, hence the theorem follows directly from the first isomorphism theorem. 
	 - **Intuition**: the theorem is essentially saying that no new information can be gained from taking quotients within a quotient group.
4. **Fourth isomorphism theorem**: given $N\triangleleft G$ we have the isomorphism $$\phi:\sub_NG\leftrightarrow\sub G/N,\quad A\mapsto\overline A=A/N$$which has the following properties: for any $N\le A,B\le G$, we have
	1. **Subgroup correspondence**: $A\le B\iff\overline{A}\le\overline{B}$, and further $|B:A|=\abs{\overline{B}:\overline{A}}$.
	2. **Subgroup generation**: $\overline{\braket{ A,B}}=\braket{\overline{A},\overline{B}}$. 
	3. **Intersection of subgroup**: $\overline{A\cap B}=\overline{A}\cap\overline{B}$. 
	4. **Preservation of normality**: $A\triangleleft G\iff\overline{A}\triangleleft\overline{G}$.
   **Proof**: 
## Automorphism
The set of **automorphisms** of $G$ is denoted $$\aut G=\set{(\phi:G\to G): \phi\text{ is an isomorphism}}$$It's obvious that $(\aut G,\circ)$ is a [[Group]]When isomorphism is replaced by homomorphism we get the **endomorphism group** $\operatorname{End}G$.
- **Inner automorphism**: inner automorphisms are automorphisms defined via conjugation:  $$\inn G =\set{\phi_g\in\aut(G):\phi_g(x) = gxg^{-1}}$$We have $\inn(G)\triangleleft \aut(G)$ by properties of conjugation ([[Group Action]]). The quotient group $$\out G=\aut G/\inn G$$is called the **outer automorphism group**.
	- $G/Z(G)\cong \inn(G)$ given by $g Z(G)\mapsto\phi_g$.
- **Characteristic subgroup**: $H\char G$ if $\phi(H)\le H$ for any $\phi\in \aut(G)$.
	- By the definition every characteristic subgroup is normal.
	- Given $d\in Z$, if there is a unique $H\le G$ such that $|G:H|=d$, then $H\operatorname{char} G$.
	- **Fully characteristic subgroup**: with stronger constraint, a fully characteristic subgroup requires $H$ to be invariant under all endomorphisms.
		- The commutator subgroup is always a fully characteristic subgroup.
- If $(|H|,|K|)=1$, then $\aut(H\times K)\cong \aut(H)\times \aut(K)$.
  **Proof**: consider the mapping $$f:\aut(H)\times\aut(K)\to\aut(H\times K),\quad (\phi_H,\phi_K)\mapsto (\phi:(h,k)\mapsto(\phi_H(h),\phi_K(k)))$$which is obviously a monomorphism. Conversely, for $\phi'\in\aut(H\times K)$ we denote $$\phi'(e_H,k)=(h',k')$$By **Bézout's identity** ([[Ideal]]) we have $t|H|+s|K|=1$, then by the above equality $$(h'^{s|K|},k'^{s|K|})=\phi'\left((e_H,k)^{s|K|}\right)=\phi'(e_H,e_K)=(e_H,e_K)\quad\Longrightarrow\quad h'=e_H$$By the same reasoning we can show that $\phi'(h,e_K)=(h',e_K),\forall h$, hence $$\phi'(h,k)=\phi'(h,e_K)\phi'(e_H,k)=(h',e_H)(e_H,k')=\phi'_H\times\phi'_K$$This means $f$ is a epimorphism, hence an isomorphism.
	- **Alternative proof**: $(|H|,|K|)=1$ ensures that $H\times \{e_K\}$ and $\{e_H\}\times K$ are characteristic subgroups of $H\times K$.
	- Using this and properties of cyclic group ([[Group Gallery]]) we know that $$Z_{mn}^*\cong \aut(C_{mn})\cong \aut(C_m)\times \aut(C_n)\cong Z_m^*\times Z_n^*$$which verifies the product formula for Euler's function $\varphi(mn)=\varphi(m)\varphi(n)$.
- **Complete group**: a group $G$ is complete if $g\mapsto i_g:G\to \aut(G)$ is isomorphism
	- A group is complete iff $Z(G)$ is trivial and $\aut(G)=\inn(G)$. 