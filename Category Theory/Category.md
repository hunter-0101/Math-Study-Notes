**Motivation**: similarity in structures can be observed across different fields of math, such as homeomorphism in [[Point Set Topology]] and isomorphism in [[Group]]. This gives rise to a new theory of higher level of abstraction that **clarifies the structural similarities among different areas**.
**Historical note**: several historical contexts of category theory is listed below:
- **Origin**: in 1940s Samuel Eilenberg and Saunders Mac Lane were studying algebraic topology, in specifically in formalizing natural transformations and functorial relationships between homotopy theories. The paper *General Theory of Natural Equivalences* in 1945 was driven by the need to systematically organize mappings between different algebraic structures.
- **Philosophical drive**: emergence of the concept of universal property, and then shift from objects to morphisms motivates the development of category theory. In particular an organizing language for modern mathematics is desired.

**Functoriality**: this is not a rigorous mathematical concept, but is widely used to convey the idea that a "construction" between two categories are well-behaved. For example, if $C$ is such a construction from $\textbf{Grp}$ to $\textbf{Top}$, then we'll expect that given $f:A\to B$ a group homomorphism its image $C(f):C(A)\to C(B)$ would be a continuous map in a reasonable way.
Note that saying "the functoriality of $C$" does not imply that $C$ itself is a functor, since it's likely that it's only defined on a small set of objects.

---
A **category** $\mathcal C$ consists of aa class of **objects** $\ob(\mathcal C)$ and a class of **morphism** $\mor_\mathcal C$ satisfying:
1. **Composition axiom**: $\mor_\mathcal C(B,C)\circ\mor_\mathcal C(A,B)\subset\mor_\mathcal C(A,C),\forall A,B,C\in\ob(\mathcal C)$.
2. **Identity axiom**: for each object $A$ there exists $\mathbb 1_A\in\mor_\mathcal C(A)$ s.t. $$f\circ\id_A=f,\id_A\circ g=g,\quad\forall f\in\mor_\mathcal C(A,B),g\in\mor_\mathcal C(B,A)$$We call $\id_A$ the identity morphism. We also denote it as $\mathbb1_A$.
3. **Associativity axiom**: we have $$h\circ(g\circ f)=(h\circ g)\circ f,\quad\forall f,g,h$$whenever the compositions are defined.
We'll sometimes write $\mor_\mathcal C(A,B)$ as $\mor(A,B)$ or $\hom(A,B)$ when there is no risk of confusion.
- **Isomorphic objects**: $A\cong B$ if there exists $f:A\to B,g:B\to A$ s.t. $g\circ f=\id_A,f\circ g=\id_B$.
- **Subcategory**: $\mathcal S$ is called a subcategory of $\mathcal C$ if:
  1. **Object & morphism inclusion**: $\ob(\mathcal S)\subset\ob(\mathcal C),\mor_\mathcal S\subset\mor_\mathcal C$.
  2. **Identity axiom**: $\mathbb1_A\in\mor_\mathcal S,\forall A\in\ob(\mathcal S)$.
  3. **Composition axioms**: $\mor_\mathcal S(B,C)\circ\mor_\mathcal S(A,B)\subset\mor_\mathcal S(A,C),\forall A,B,C\in\ob(\mathcal S)$.
  We do not need to add associativity axiom since it's already guaranteed in inclusion relation.
	- **Fullness**: $\mathcal S\subset\mathcal C$ is full if $$\mor_\mathcal S(A,B)=\mor_\mathcal C(A,B),\quad\forall A,B\in\ob(\mathcal S)$$in such case specifying just the objects in $\mathcal S$ is sufficient to distinguish it.
- **Opposite category**: $\mathcal C^{\text{op}}$ consists of the same objects as $\mathcal C$ and reversed morphisms, i.e., $$\ob(\mathcal C^{\text{op}})=\ob(\mathcal C);\quad (f^\text{op}:f^\text{op}(b)=a\text{ if }f(a)=b)\in\mor_{\mathcal C^\text{op}}(A,B),\quad\forall f\in\mor_\mathcal C(A,B)$$Obviously we have $(\mathcal C^\text{op})^\text{op}=\mathcal C$.
- **Initial/Terminal object**: $I\in\ob(\mathcal C)$ is an initial object if for any $X\in\mathcal C$ there exists exactly one morphism $I\to X$. Its dual notion is called the terminal object $T$.
	- **Uniqueness**: initial/terminal object is unique up to isomorphism:
	  **Proof**: it suffices to show uniqueness of initial object by duality. Assume that there are two initial objects $A,B\in\ob(\mathcal C)$, then by definition there exists unique morphisms $$\begin{cases}f_{AB}:A\to B\\f_{BA}:B\to A\end{cases}\quad\Longrightarrow\quad\begin{cases}f_{BA}\circ f_{AB}:A\to A\\f_{AB}\circ f_{BA}:B\to B\end{cases}$$By uniqueness of morphism and existence of identity morphism we have $$f_{BA}\circ f_{AB}=\id_A,\quad f_{BA}\circ f_{AB}=\id_B$$hence $A\cong B$.
	- **Zero object**: an object is called zero object if it's both initial and terminal.
## Functor
Given categories $\cal C,D$, a **functor** $F:\cal C\to D$ associate each object/morphism in $\cal C$ to one of those in $\cal D$, and there are two kinds of functors, **covariant** and **contravariant**, defined by 
1. **Object mapping**: $F(\ob(\cal C))\subset\ob(\cal D)$.
2. **Morphism mapping**: $F(\id_A)=\id_{F(A)},\forall A\in\ob(\cal C)$, and further
	1. **Covariant functor**: $F(g\circ f)=F(g)\circ F(f),\forall f,g\in\mor_\mathcal C$.
	2. **Contravariant functor**: $F(g\circ f)=F(f)\circ F(g),\forall f,g\in\mor_\mathcal C$.
A functor $F:\cal C\to C$ is called an **endofunctor**.
- **Faithfulness**: $F:\cal C\to D$ is faithful if $F:\mor_\mathcal C\to\mor_\mathcal D$ is injective.
- **Fullness**: $F:\cal C\to D$ is full if $F:\mor_\mathcal C\to\mor_\mathcal D$ is surjective.
- **Forgetful functor**: $F:\cal C\to D$ is forgetful if it "forget" or drop some of the input's structure or properties, e.g. $F:\mathcal C\to\textbf{Set}$.
- **Bifunctor**: given categories $\cal C_1,C_2,D$ a bifunctor is a functor $$F:\cal C_1\times C_2\to D$$which is similar to bi-linear maps. [[Exterior Algebra]]
### Hom functor
for object $A\in\ob(\mathcal C)$ consider the two functors $$h_A:\mathcal C\to\textbf{Set},\quad h^A:\mathcal C\to\textbf{Set}$$where $h_A$ is covariant with $$h_A:\begin{cases}\ob(\mathcal C)\to\set{\mor_\mathcal C(A,X):X\in\ob(\mathcal C)},& X\mapsto\mor_\mathcal C(A,X)\\\mor_\mathcal C(X,Y)\to\set{g:\mor_\mathcal C(A,X)\to\mor_\mathcal C(A,Y)},& f\mapsto g=(f\circ)\end{cases}$$and $h^A$ is contravariant with $$h^A:\begin{cases}\ob(\mathcal C)\to\set{\mor_\mathcal C(X,A):X\in\ob(\mathcal C)},&X\mapsto\mor_\mathcal C(X,A)\\\mor_\mathcal C(X,Y)\to\set{h:\mor_\mathcal C(Y,A)\to\mor_\mathcal C(X,A)},& f\mapsto h=(\circ f)\end{cases}$$For any two pairs $i:B\to B',k:A'\to A$ we have the following commutative diagram 
  <p align="center"><img align="center" src="https://i.upmath.me/svg/%0A%5Cbegin%7Btikzcd%7D%0A%7B%5Coperatorname%7BMor%7D_%5Cmathcal%20C(A%2CB)%7D%20%5Carrow%5Bd%2C%20%22h_A(i)%22'%5D%20%5Carrow%5Br%2C%20%22h%5EB(k)%22%5D%20%26%20%7B%5Coperatorname%7BMor%7D_%5Cmathcal%20C(A'%2CB)%7D%20%5Carrow%5Bd%2C%20%22h_%7BA'%7D(i)%22%5D%20%5C%5C%0A%7B%5Coperatorname%7BMor%7D_%5Cmathcal%20C(A%2CB')%7D%20%5Carrow%5Br%2C%20%22h%5E%7BB'%7D(k)%22'%5D%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%26%20%7B%5Coperatorname%7BMor%7D_%5Cmathcal%20C(A'%2CB')%7D%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%0A%5Cend%7Btikzcd%7D%0A"  /></p>
  Any function $j:A\to B$ will be mapped to $i\circ j\circ k$ through either of the paths $$\begin{align}&(h_{A'}(i)\circ h^B(k))(j)=h_{A'}(i)(j\circ k)=i\circ j\circ k\\&(h^{B'}(k)\circ h_A(i))(j)=h^{B'}(k)(i\circ j)=i\circ j\circ k\end{align}$$which implies that the **hom functor** defined by $$\hom(A,-)=h_A(-),\quad\hom(-,B)=h^B(-)$$is a bifunctor $\hom(-,-):\mathcal C^\text{op}\times\mathcal C\to\textbf{Set}$. We sometimes denote it as $\hom_\mathcal C(-,-)$ to emphasize the category domain. 
  - **Adjoint pair**: given functors $F:\mathcal C\to\mathcal D,G:\mathcal D\to\mathcal C$ of the same variance, $(F,G)$ is called and **adjoint pair**, with $F,G$ being the **left/right adjoint functor**, if for all $A\in\ob(\mathcal C),B\in\ob(\mathcal D)$ there exists a bijection $\varphi:\mor_\mathcal D(FA,B)\to\mor_\mathcal C(A,GB)$ s.t. in following two diagram:
    <p align="center"><img align="center" src="https://i.upmath.me/svg/%0A%5Cbegin%7Btikzcd%7D%0A%7B%5Ctext%7BMor%7D_%5Cmathcal%20D(FA%2CB)%7D%20%5Carrow%5Br%2C%20%22%7B%5Cvarphi_%7BA%2CB%7D%7D%22%5D%20%5Carrow%5Bd%2C%20%22h_%7BFA%7D(g)%22'%5D%20%26%20%7B%5Ctext%7BMor%7D_%5Cmathcal%20C(A%2CGB)%7D%20%5Carrow%5Bd%2C%20%22h_A(Gg)%22%5D%20%26%20%7B%5Ctext%7BMor%7D_%5Cmathcal%20D(FA%2CB)%7D%20%5Carrow%5Br%2C%20%22%7B%5Cvarphi_%7BA%2CB%7D%7D%22%5D%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%26%20%7B%5Ctext%7BMor%7D_%5Cmathcal%20C(A%2CGB)%7D%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%5C%5C%0A%7B%5Ctext%7BMor%7D_%5Cmathcal%20D(FA%2CB')%7D%20%5Carrow%5Br%2C%20%22%7B%5Cvarphi_%7BA%2CB'%7D%7D%22'%5D%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%26%20%7B%5Ctext%7BMor%7D_%5Cmathcal%20C(A%2CGB')%7D%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%26%20%7B%5Ctext%7BMor%7D_%5Cmathcal%20D(FA'%2CB)%7D%20%5Carrow%5Bu%2C%20%22h%5EB(Ff)%22%5D%20%5Carrow%5Br%2C%20%22%7B%5Cvarphi_%7BA'%2CB%7D%7D%22'%5D%20%26%20%7B%5Ctext%7BMor%7D_%5Cmathcal%20C(A'%2CGB)%7D%20%5Carrow%5Bu%2C%20%22h%5E%7BGB%7D(f)%22'%5D%0A%5Cend%7Btikzcd%7D%0A" /></p>
    The first diagram commutes for fixed $A\in\ob(\mathcal C)$ and $g\in\mor_\mathcal D(B.B')$, while the second diagram commutes for fixed $B\in\ob(\mathcal D)$ and $f\in\mor_\mathcal C(A,A')$.
  - **Representable functor**: functor $F:\mathcal C\to\textbf{Set}$ is **representable** if there exists $X\in\ob(\mathcal C)$ s.t. $$F\cong\begin{cases} h_X,&\text{if }F\text{ is covariant}\\h^X,&\text{if }F\text{ is contravariant}\end{cases}$$We say that $F$ is represented by $X$.
  
## Natural transformation
Given functors $F,G:\cal C\to D$ of the same variance a **natural transformation** $\varphi:F\to G$ is a collection of morphisms $\set{(\varphi_A:FA\to GA):A\in \mathcal C}$ s.t. given any $f\in\mor_\mathcal C(A,B)$ the left (right) of the following diagrams commutes, given that $F,G$ are covariant (contravariant): 
<p align="center"><img align="center" src="https://i.upmath.me/svg/%0A%5Cbegin%7Btikzcd%7D%0AFA%20%5Carrow%5Br%2C%20%22%5Cvarphi_A%22%5D%20%5Carrow%5Bd%2C%20%22Ff%22'%5D%20%26%20GA%20%5Carrow%5Bd%2C%20%22Gf%22%5D%20%26%20FA%20%5Carrow%5Br%2C%20%22%5Cvarphi_A%22%5D%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%26%20GA%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%5C%5C%0AFB%20%5Carrow%5Br%2C%20%22%5Cvarphi_B%22'%5D%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%26%20GB%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%26%20FB%20%5Carrow%5Br%2C%20%22%5Cvarphi_B%22'%5D%20%5Carrow%5Bu%2C%20%22Ff%22%5D%20%26%20GB%20%5Carrow%5Bu%2C%20%22Gf%22'%5D%0A%5Cend%7Btikzcd%7D%0A"  /></p>
The set of natural transformations between $F,G$ is denoted $\nat(F,G)$.
- **Natural equivalence**: $F,G$ are naturally equivalent (**isomorphic**), denoted $F\cong G$, if $\varphi_A$ is an isomorphism for all $A\in\mathcal C$, with $\varphi_A$ called a **natural isomorphism (equivalence)**.
- **Functor category**: given categories $\cal C,D$, a functor category $[\mathcal C,\mathcal D]$ is a category whose objects are functors $F:\cal C\to D$ and morphisms are natural transformations between functors.
	- **Presheaf**: given category $\mathcal C$ define the presheaf on $\mathcal C$ as the functor category $[\mathcal C^{\text{op}},\textbf{Set}]$.
- **Example**: consider $*_G$ given group $G$. For functors $A,B\in[*_G,\textbf{Set}]$ with $A(*)=X,B(*)=Y$ a natural transformation $\varphi:X\to Y$ should satisfy the condition $$\varphi(g(x))=g(\varphi(x)),\quad\forall x\in X,g\in G$$A simple example is $G=C_4$ the cyclic group ([[Group Gallery]]) with $$\begin{cases}X=\set{0,1,2,3}\\ A(g)=(x\mapsto x+g\bmod4)\end{cases}\quad\text{and}\quad\begin{cases}Y=\set{0,1}\\ B(g)=(x\mapsto x+g\bmod2)\end{cases}$$In such case a natural transformation could be $\varphi(1)=\varphi(3)=1,\varphi(0)=\varphi(2)=0$.
## Examples
- **Category of sets**: $\textbf{Set}$ takes all sets as objects, and all functions between them as morphisms. $\textbf{FinSet}$ is a subcategory of $\textbf{Set}$ whose objects are finite sets.
- **Category of [[Group]]**: $\textbf{Grp}$ takes all groups as objects and [[Group Homomorphism]] as morphisms. 
	- Similarly we can define $\textbf{Ring}$ for [[Ring]], $\textbf{Field}$ for [[Field]], and ${}_{R}\textbf{Mod},\textbf{Mod}_R$ for left and right $R$-[[Module]].
- **Single object category**: see [[Group]].

## Categorification
We define the "**category number**" as a measure of level of abstraction.
0. **Category number 0**: numbers, elements, scalers, vectors, etc..
1. **Category number 1**: structures built from 0-things, like sets, groups, rings, vector spaces, modules, monoids, etc..
2. **Category number 2**: usual categories themselves, like $\textbf{Set}, \textbf{Vect}_k,\textbf{Grp}$. In general a category $\mathcal C$ takes 1-tings as objects, and functions (relations) between them as morphisms.
3. **Category number 3**: usual 2-categories, whose morphisms between objects themselves are categories. Morphisms between morphisms are called 2-morphisms.
We define **decategorification** as the process of passing from higher level of lower level by forgetting morphisms up to isomorphism, and replacing objects by invariants, like what we've done to degenerate [[Yoneda Lemma]] into Cayley's theorem ([[Group Actions]]).
In contrast, **categorification** is the inverse operation of decategorification. Given object $A$ from a lower-level category, we find some higher-level category $\mathcal C$ s.t. $$\operatorname{Decat}(\mathcal C)\cong A$$
- **Example**: several small examples are provided below. 
	- $\mathbb N\leftrightarrow\textbf{FinSet}$: decategorification proceeds by cardinality, with $(+,\cdot,0,1)\leftrightarrow(\sqcup,\times,\varnothing,\set{e})$.
	- **$\mathbb Z\leftrightarrow$ category of $\mathbb Z$-graded vector spaces**: Taking graded dimension or the Grothendieck group can recover integer combinations (virtual objects). (There are multiple ways to realize this; the key idea is that complexes/graded objects allow “negative” contributions in Euler characteristics.)
	- **Euler characteristic $\leftrightarrow$ homology groups**: the Euler characteristic is a decategorified invariant. The homology/cohomology groups categorify the Euler characteristic: the categories of chain complexes/perverse sheaves produce the alternating sum on decategorification.
	- **Jones polynomial $\leftrightarrow$ Khovanov homology**
	- **A ring $\leftrightarrow$ a monoidal category**.
- **Discussion**
	- **Non-uniqueness of categorification**: there can be many inequivalent categories that decategorify to the same algebraic object.
	- **Choice of decategorification functor**: the choice of this functor matters. cardinality, $K_0$, graded Euler characteristic, trace of Frobenius, etc., gives different decategorifications.


- Key example: Fourier series and transform on group and arbitrary category, which degenerates to the ordinary [[Fourier Series]] and [[FT on L2]] results taking $G=\mathbb R$.