Given two [[Group]] $G,H$, a **group homomorphism** is a function $$\phi: G \to H$$satisfying the property of **preservation of group operation**, i.e., $$\phi(ab)=\phi(a)\phi(b),\quad\forall a,b\in G\imply\phi(e_G)=e_H,\quad\phi\left(a^{-1}\right)=\phi(a)^{-1}$$Two groups with a homomorphism between them is denoted $G\simeq H$. The collection of all homomorphisms from $G$ to $H$ is denoted $\hom(G,H)$. 
- **Kernel**: the kernel of a homomorphism is defined as $$\ker\phi =\set{g \in G: \phi(g) = e_H}$$which is similar to the definition in [[Vector Space]]. 
- **Isomorphism**: an isomorphism is a homomorphism $\phi:G\to H$ that is invertible, i.e., there exists another homomorphism $\psi:H\to G$ s.t. $$\psi\circ\phi=\id_G,\quad \phi\circ\psi=\id_H$$This is equivalent to $\phi$ being bijective, denoted $G\cong H$.
- **Other morphisms**
	- **Monomorphism**: injective homomorphism.
	- **Epimorphism**: surjective homomorphism.
	- **Endomorphism**: a homomorphism from $G$ to itself, i.e., $H=G$. 
	- **Automorphism**: an isomorphic endomorphism. 
- **Fundamental theorem of homomorphism**: given $\phi:G\to H,N\triangleleft G$ with $N\subset\ker\phi$, there exists a unique $\overline\phi:G/N\to H$ s.t. $\phi=\overline\phi\circ\pi$, i.e., the following diagram commutes: 
  <p align="center"><img align="center" src="https://i.upmath.me/svg/%0A%5Cbegin%7Btikzcd%7D%0AG%20%5Carrow%5Br%2C%20%22%5Cphi%22%5D%20%5Carrow%5Bd%2C%20%22%5Cpi%22'%5D%20%26%20H%20%5C%5C%0AG%2FN%20%5Carrow%5Bru%2C%20%22%5Coverline%5Cphi%22'%5D%20%20%20%20%20%20%26%20%20%0A%5Cend%7Btikzcd%7D%0A" /></p>
  and $\im\overline\phi=\im\phi,\ker\overline\phi=\pi(\ker\phi),\ker\phi=\pi^{-1}(\ker\overline\phi)$ where $\pi$ is the canonical projection.
	- **Corollary**: $\overline\phi$ is injective iff $N=\ker\phi$; if $\phi$ is surjective then $H\cong G/\ker\phi$. 
## Isomorphism theorems
There are four isomorphism theorems:
1. **First Theorem**: given homomorphism $\phi: G \to H$, we have $\ker(\phi)\triangleleft G,G/\ker(\phi) \cong \im(\phi)$.
2. **Diamond Theorem**: for $H \leq G,N \triangleleft G$ we have $H/(H \cap N) \cong HN/N$.
3. **Third Theorem**: If $N \triangleleft G$ and $M \triangleleft G$ with $M \subseteq N$, then $(G/M)/(N/M) \cong G/N$.
	 - No new information gained from taking quotients of a quotient group.
4. **Lattice (Correspondence) Theorem**: $N\triangleleft G$, then there is a bijection from the set of subgroups $A$ of $G$ which contain $N$ onto the set of subgroups $\overline{A}=A/N$ of $G/N$. This bijection has the following properties: for all $A,B\le G,N\le A,N\le B$,
	- $A\le B$ iff $\overline{A}\le\overline{B}$.
	- if $A\le B$ then $|B:A|=|\overline{B}:\overline{A}|$.
	- $\overline{\langle A,B\rangle}=\langle \overline{A},\overline{B}\rangle$.
	- $\overline{A\cap B}=\overline{A}\cap\overline{B}$.
	- $A\triangleleft G$ iff $\overline{A}\triangleleft\overline{G}$.
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