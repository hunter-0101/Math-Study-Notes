A **category** $\mathcal C$ consists of aa class of **objects** $\ob(\mathcal C)$ and a class of **morphism** $\mor_\mathcal C$ satisfying:
1. **Composition axiom**: $\mor_\mathcal C(B,C)\circ\mor_\mathcal C(A,B)\subset\mor_\mathcal C(A,C),\forall A,B,C\in\ob(\mathcal C)$.
2. **Identity axiom**: for each object $A$ there exists $\mathbb 1_A\in\mor_\mathcal C(A)$ s.t. $$f\circ\id_A=f,\id_A\circ g=g,\quad\forall f\in\mor_\mathcal C(A,B),g\in\mor_\mathcal C(B,A)$$We call $\id_A$ the identity morphism. We also denote it as $\mathbb1_A$.
3. **Associativity axiom**: we have $$h\circ(g\circ f)=(h\circ g)\circ f,\quad\forall f,g,h$$whenever the compositions are defined.
We'll sometimes write $\mor_\mathcal C(A,B)$ as $\mor(A,B)$ or $\hom(A,B)$ when there is no risk of confusion.
- **Intuition**: a category is like a "python package" we can import to solve specific problems, and the categorical definition (via [[Universal Property]]) is like the API we're allowed to call to actually use these packages. For instance, Cartesian product of [[Set]] $X,Y$ is an object $P$ with $$\pi_1:P\to X,\quad\pi_2:P\to Y$$That is universal, and that's all we care - we don't care about what is actually inside $P$, we only care about how $P$ can interact with other objects.  This allows the "**Operating System**" (see [[ZFC Set Theory vs. Category Theory]] for more about the analogue) to swap out the underlying "**Hardware**" (the specific category) while keeping the "**Software**" (the theorems) exactly the same. 
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
We define **decategorification** as the process of passing from higher level of lower level by forgetting morphisms up to isomorphism, and replacing objects by invariants, like what we've done to degenerate [[Yoneda Lemma]] into Cayley's theorem ([[Group Action]]).
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