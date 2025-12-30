For a sub[[Group]] $H\le G$ the property of being **normal** is defined as $$H\triangleleft G\qiffq N_G(H)=G$$There are several equivalent characterizations for this that are useful:
1. **Invariance under conjugation ([[Group Action]])**: $g^{-1}hg\in H,\forall g,\in G,h\in H$. 
2. **Coset definition**: $gH=Hg,\forall g\in G$, i.e., the left and right coset coincide.
3. **Kernel characterization**: $H=\ker\phi$ for some [[Group Homomorphism]] $\phi$. 
**Proof of equivalence**: $(1\Leftrightarrow 2)$ is trivial; for $(1\Rightarrow3)$ we can simply take $\phi=\pi:G\to G/H$ the canonical projection (below); for $(3\Rightarrow1)$ notice that for any $g\in G$ we have $$h\in\ker\phi\imply\phi(ghg^{-1})=\phi(g)e_{\im\phi}\phi(g)^{-1}=e_{\im\phi}\imply ghg^{-1}\in\ker\phi$$which completes the proof. 
- **Intuition**: two sets of equivalent characterizations provides different intuitions:
	- **Invariance under action of conjugation**: a normal subgroup is a fixed point in the collection of subgroups of $G$ under the [[Group Action]] of conjugation, i.e., is a subgroup that is "**perspective-independent**", i.e., "invariant under change of basepoint". 
	- **Kernel of homomorphism**: since elements within $H$ are "invariant under change of basis", if we tears the structure of "all symmetries of change of basis" out it's natural that it will be projected to the identity element in the "quotient", i.e., serves as the kernel of this canonical projection. 
  Algebraically, the property of being normal implies that **group operations are compatible with taking quotient**. If a subgroup were perspective-dependent, the "operation" in the quotient group would change depending on who is looking at it. 
- **Dependency on the underlying group**: the property of being normal is dependent on the underlying group itself, so an extension of underlying group, or a restriction of subgroup could affect the property of being normal. The matrix group below provides a geometric example for this. 
	- **Intuition**: if the structure of the group is "enriched" (i.e., extended) it might be fine enough to "see" the distinctions between elements within a previously normal subgroup, hence it's no longer normal; if we're restricted to only a subgroup of a normal subgroup, it could also be "seen" since it could be translated somewhere else in the normal subgroup. 
- **Simple group**: $G$ is simple if it only has trivial normal subgroups. 
- **Subnormal series**: a subnormal series of $G$ is a series of the form $$G=G_0\triangleright G_1\triangleright\cdots\triangleright G_l\triangleright\set{e}$$Within such subnormal series, the quotients $G_{i-1}/G_i$ are called **factor group**. 
## Quotient group & group extension
The action of **taking quotient** and **extension** are the group-theoretic [[Division]] and multiplication. They're inverse to each other with functions similar to their arithmetic counterparts. 
- **Quotient group**: given $N\triangleleft G$ the **quotient group of $G$ w.r.t $N$** is the collection of cosets ([[Group]]) $G/N$ equipped with multiplication and inverse operations defined by $$(aN)(bN)=(ab)N,\quad(aN)^{-1}=a^{-1}N$$Note that normality of subgroup is crucial, as discussed below. 
	- **Intuition**: now that a normal subgroup would "remain unchanged" when "viewed from any perspective", i.e., invariant under any "change of basis" ([[Group Action]]), we can naturally tears this sub-structure out and only focus on other elements that "could change". This helps to simplify our work when investigating the structure of the group. 
	- **Example**: from [[Matrix Group]] we know that $\sl(n,F)\triangleleft\gl(n,F)$, and $$\gl(n,F)/\sl(n,F)\cong F$$Geometrically, $\sl(n,F)$ remains unchanged under any invertible linear transformation because any $A\in\sl(n,F)$ always preserves the volume form, and by taking the quotient we're focusing on the constant multiplier by which the volume form is scaled. 
- **Group extension**: given two groups $Q,N$, a another group $G$ is the **extension of $Q$ by $N$** if there is an exact sequence ([[Module]]) of homomorphisms $$1\to N\xto{\iota}G\xto{\pi} Q\to1$$with $i$ injective and $\pi$ surjective, and $\ker\pi=\im\iota$. Thus we have that $G/\iota(N)\cong Q$.
	- **Central extension**: an extension is central if $\iota(N)\subset Z(G)$. Say, the extension $$1\to N\to N\rtimes_\theta Q\to Q\to 1$$defined by semi-direct product is central iff $\theta$ is trivial and $N$ is abelian.
	- **Isomorphic extension**: two extensions are isomorphic if there exists a commutative diagram
	  <p align="center"><img align="center" src="https://i.upmath.me/svg/%0A%5Cbegin%7Btikzcd%7D%0A1%20%5Carrow%5Br%5D%20%26%20N%20%5Carrow%5Br%5D%20%5Carrow%5Bd%2C%20Rightarrow%2C%20no%20head%5D%20%26%20G%20%5Carrow%5Br%5D%20%5Carrow%5Bd%2C%20%22%5Capprox%22%5D%20%26%20Q%20%5Carrow%5Br%5D%20%5Carrow%5Bd%2C%20Rightarrow%2C%20no%20head%5D%20%26%201%20%5C%5C%0A1%20%5Carrow%5Br%5D%20%26%20N%20%5Carrow%5Br%5D%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%26%20G'%20%5Carrow%5Br%5D%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%26%20Q%20%5Carrow%5Br%5D%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%26%201%0A%5Cend%7Btikzcd%7D%0A" /></p>
	  An extension is said to be **split** if it's isomorphic to the extension defined by a semi-direct product. 
## Composition series
A **composition series** of a [[Group]] $G$ is a finite subnormal series of subgroups of the form $$G = G_0 \triangleright G_1 \triangleright \cdots \triangleright G_n =\set{e}\where G_{i-1}/G_i\text{ is simple, }\forall1\le i\le n$$That is, $G_i$ is the maximal normal subgroup of $G_{i-1}$. The quotients are **composition factors**, and $n$ is the **composition length**. Obviously a subnormal series is a composition series iff it is of maximal length, i.e., no additional subgroup can be inserted into the series. 
**Jordan-Hölder theorem**: any finite, nontrivial $G$ has a composition series, with composition factors being unique up to isomorphism and permutation. 
**Proof**: for existence, notice that when $G/N$ is not simple, we can always extent $N$ to a larger normal subgroup via the fourth isomorphism theorem ([[Group Homomorphism]]). For uniqueness,  the main idea is to use induction on the length of shortest composition series. It is sufficient to show that any decomposition seres is equivalent to the minimal seres.
 0. **Lemma**: if $A,B$ are normal subgroups of $G$ such that $G/A,G/B$ are simple, then $$G/A\cong B/(A\cap B),\quad G/B\cong A/(A\cap B)$$This can be proven in the following steps: 
	     1. $A,B$ does not contain each other, otherwise $G/A$ or $G/B$ will not be simple.
	     2. $AB/A$ is normal in $G/A$, and by simplicity we know that $AB/A=G/A$.
	     3. The fourth isomorphism theorem yields the result. [[Group Homomorphism]]
	 1. **Existence & preparation**: by the fourth isomorphism theorem a composition series terminating in $1$ is guaranteed to exist for finite group $G$. Pick below the shortest among them: $$G=G_0\triangleright G_1\triangleright\cdots\triangleright G_r=1$$For any other composition series denoted with $H_i(0\le i\le s)$, if $H_1=G_1$ then by induction the result holds. Otherwise let $K=H_1\cap G_1\triangleleft G$. By the lemma we have that $G_1/K\cong G/H_1$ and $H_1/K\cong G/G_1$ are simple.
	 2. **Construct a series $K_i$**: let $K_i=K\cap G_i$, then $K_i\triangleleft G_i,K_{i+1}\triangleleft K_i$. Consider the homomorphism $\phi:K\to G_i/G_{i+1}$ given by the quotient map, then $\ker\phi=K_i$ and the image is normal. By the isomorphism theorems $K_i/K_{i+1}\triangleleft G_i/G_{i+1}$, thus by its simplicity we have $K_i/K_{i+1}$ either trivial or simple. By removing the duplicates we have $$\begin{align}G_1\triangleright G_2\triangleright\cdots\triangleright G_r=1\\G_1\triangleright K_1\triangleright\cdots\triangleright K_r=1\end{align}$$By induction the above two series are equivalent, thus exactly one of $K_i/K_{i+1}$ is trivial.
	 3. **Relate to $H_i$**: as $K_1\triangleleft H_1$ with simple quotient, we have two composition series $$\begin{align}H_1\triangleright H_2\triangleright\cdots\triangleright H_s=1\\H_1\triangleright K_1\triangleright\cdots\triangleright K_r=1\end{align}$$Again by induction these two series are equivalent with $r-1=s-1$. Thus we only need to show that $$\begin{align}G\triangleright G_1\triangleright K_1\triangleright\cdots\triangleright K_r=1\\G\triangleright H_1\triangleright K_1\triangleright\cdots\triangleright K_r=1\end{align}$$are equivalent. By lemma above we have $G/G_1\cong H_1/K_1$ and $G/H_1\cong G_1/K_1$, thus the proof is completed.
	 - **Proof 2**: we use induction on $|G|$. Most steps are similar to that in proof 1, only that after defining $K_2$, we directly pick a composition series of it. Now by the lemma we have the vertices marked by the same symbol isomorphic, thus the result directly follows. ![[Pasted image 20241214202715.png]]
	 - **Composition series for infinite group**: for infinite groups with a composition series, the Jordan-Hölder theorem still holds, but in the proof we need to also show that the normal subgroup of a group with finite composition series also has a finite composition series (as we've done in proof 1).
- **Discussion**: infinite groups do not necessarily have a composition series, like $\mathbb Z$.
## Derived series
**Derived (Commutator) series** is the following series of commutator subgroups $$G=G^{(0)}\triangleright G^{(1)}\triangleright G^{(2)}\triangleright\cdots$$where $G^{(n+1)}=[G^{(n)},G^{(n)}]$. It may ends with invariant $G^{(t)}$ or $1$, and in later case $G$ is said to be solvable, and the least $n$ such that $G^{(n)}=1$ is the **derived (solvable) length**.
- **Commutator subgroup**: $G^{(1)}=[G,G]=\langle[a,b]=a^{-1}b^{-1}ab|a,b\in G\rangle$ is the group generated by all commutators. (Note that product of commutators is not necessarily a commutator)
	- $G/N$ is abelian iff $[G,G]\subset N$. Note that $[G,G]\triangleleft G$ since for $u=[a,b]$, we have $g^{-1}ug=u[u,g]$.
- For finite non-solvable group, the terminated subgroup $G^{(n)}$, which satisfies $[G^{(n)},G^{(n)}]=G^{(n)}$ is called **perfect group**. For infinite group, the series need not to terminate at a finite stage.
## Solvable group
A group $G$ is said to be **solvable** if one of the following equivalent conditions are satisfied:
1. $G$ can be constructed from abelian groups using extensions. [[Group]]
2. The derived series terminates in $\set{1}$. 
3. $G$ has a subnormal series whose factor groups are abelian and terminates in $\set{1}$.
	- This definition is equivalent to 2 as $G/N$ is abelian iff $[G,G]\subset N$.
4. (For finite $G$) $G$ has a composition series where the factor groups are cyclic groups of prime order.
	- The equivalence can be seen from two facts:
	  1. Finite group has finite composition length.
	  2. Every simple abelian group is cyclic of prime order.
- **Subgroup of solvable group is solvable**: for any $H\le G$, it can be shown that $H\cap G_i$ forms a composition series for $H$.
- **Extension of solvable groups is solvable**: for $N\triangleleft G$ and $\overline G=G/H$, we have that if $N,\overline G$ are solvable, then $G$ is solvable. This can be shown by directly constructing the composition series.
	- **Finite p-groups are solvable**: we use induction on order of p-group $P$. We already know that $Z(P)$ is not trivial, and by induction hypothesis $Z(P)$ and $P/Z(P)$ are solvable, thus by the above property $P$ is also solvable. [[Group Gallery#$p$-group]]
## Nilpotent group
A group $G$ is called **nilpotent** if it satisfies one of the following **equivalent** conditions:
1. $G$ has a central series of finite length.
2. $G$ has a upper/lower central series that terminates with trivial subgroup.
3. $G$ can be obtained from abelian groups by successive central extensions. Here central extension refer to those where the image of the normal subgroup $N$ is central in $G$. (Note that this poses a stronger constraint to the extension, thus **all nilpotent groups are solvable**)
4. (Finite) $G$ is equal to a direct product of its Sylow subgroups.
	- This can be shown by the fact that a). p-groups are nilpotent. b). A group is equal to the direct product of its Sylow subgroups if $n_p=1$ for all primes $p\mid |G|$. [[Sylow Theorems]]
### Central series
A **central series** is a kind of normal series of subgroups. For $G$, the central series is defined as $$G=G_0\triangleright G_1\triangleright\cdots\triangleright G_n=1$$where each quotients are central in $G/G_{i+1}$: $[G,G_i]\le G_{i+1}$.
- A group has a central series iff it's nilpotent.
- **Ascending central series**: denote $Z^2(G)=Z(G/Z(G))$ and similarly define $Z^i(G)$, then we have a series $$1\le Z(G)\le Z^2(G)\le\cdots$$where $g\in Z^i(G)$ iff $[g,x]\in Z^{i-1}(G),\forall x\in G$. The smallest $n$ such that $Z^n(G)=G$ is called the **nilpotency class** of $G$.
	- We sometimes refer to groups of class $2$ as metabelian.