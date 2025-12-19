**Discussion**: field is where our previous knowledges in [[Real Number System]] start to play against us - we're used to the notations like $\sqrt 2,\pi,e$ and are extremely familiar with additional structures on $\mathbb R$ like its topological and metric properties, but keep in mind - they're all built using **analytic tools**. In the perspective algebra, the only thing that stays consistent is the isomorphic copy of $\mathbb Q$ contained in every field $F$ with $\char F=0$, and other algebraic properties deduced in general fields from purely **algebraic tools**. We must forget about everything else - order, norm, metric, distance, absolute value, etc.. 

---
A **field** is a tuple $(F,+,\cdot)$ s.t. 
- **Division ring (skew field) structure**: $(F,+,\cdot)$ is a division [[Ring]].
- **Commutativity**: $(F\backslash\set{0},\cdot)$ is an abelian [[Group]].
To put more succinctly, a field is a **commutative division ring**. It generalizes the [[Real Number System]], and serves as powerful tool for dealing with general algebraic structures. Below we list some basic facts about fields. 
- **Characteristic**: the characteristic of field $F$ is defined as its ring characteristic $$\char F=|1|_+$$Similarly, when such integer does not exist we say $\char F=0$.
	- **Field of characteristic $0$**: it's obvious that any field $F$ with $\char F=0$ contains a subfield that is isomorphic to $\mathbb Q$. 
- **Algebraical closedness**: $F$ is algebraically closed if every non-constant polynomial in $F[X]$ the [[Polynomial Ring]] has a root in $F$, i.e., the fundamental theorem of algebra holds. 
	- **Algebraic closure**: the algebraic closure of $F$ is defined as 
	- **Algebraically closed field is infinite**: $F$ algebraically closed must satisfy $|F|=\infty$, since under finiteness assumption we can construct polynomial violating closedness by $$F=\set{a_1,\cdots,a_n}\imply P(x)=1+\prod_{i=1}^n(x-a_i)\neq0,\quad\forall x\in F$$This follows from the fact that $1=0\iff F=\set{0}$. However it can be countably infinite, for instance, the algebraic closure $\overline{\mathbb Q}$.
- **Valuation**: given a field $F$ and an abelian totally ordered ([[Order]]) [[Group]] $(\Gamma,+,\ge)$ extended to $\Gamma\cup\set{\infty}$ with $\infty\ge a,a+\infty=\infty+a=\infty+\infty=\infty,\forall a\in F$, a **valuation** of $F$ is a map $$\nu:F\to \Gamma\cup\set{\infty}\quad\st\quad\begin{cases}\nu(a)=\infty\iff a=0\\\nu(ab)=\nu(a)+\nu(b)\\\nu(a+b)\ge\min(\nu(a),\nu(b)),\text{with equality if }\nu(a)\neq\nu(b)\end{cases}$$A valuation is called **trivial** if $\nu(a)=0,\forall a\in F^\times$, and **discrete** if $\Gamma=\mathbb Z$. 
- **CRT formula**: in a field the CRT in [[Ideal]] has an explicit formula $$f\equiv r_k\pmod{I_k}\quad\iff\quad f\equiv\sum_{k=1}^nr_kJ_k(J_k^{-1}\bmod I_k)\quad\text{where}\quad J_k=\prod_{s\neq k}I_s$$which generalizes the one in [[Congruence System]]. 
- **Absolute value**: over any field $F$ (or [[Integral Domain]]) an absolute value is a real-valued function satisfying:
	1. **Positive definiteness**: $|x|\ge0,\forall x\in F$ and $|x|=0\iff x=0$.
	2. **Multiplicity**: $|xy|=|x|\cdot|y|,\forall x,y\in F$.
	3. **Triangle inequality**: $|x+y|\le|x|+|y|,\forall x,y\in F$.
  The **trivial absolute value** is the one with $|x|=1,\forall x\neq0$.
- **Involution**: an involution over $F$ is a function $f:F\to F$ that is **involutary**, i.e., $$f\circ f(x)=x,\quad\forall x\in F$$Algebraically, it's a field automorphism or order $2$. An involution is usually denoted $x\mapsto\overline x$. 
	- **Fixed field of involution**: the fixed field of $F$ induced by $x\mapsto\overline x$ is , literally, defined as $F_0=\set{x\in F:x=\overline x}$ the subfield fixed under the involution. 
- **Ordered field**: an ordered field is a tuple $(F,\le)$ is totally ordered ([[Order]]). 
	- **Archimedean property**: $(F,\le)$ is Archimedean if every element lies between two elements f its field of fraction. 
## Example of fields
- **[[p-adic Field]]**: the field $\mathbb Q_p,p\in\mathbb P$ ([[Division]]) is an important class of field used fro dealing with umber theoretic problems, such as [[Diophantine Approximation]].
- **[[Modular Arithmetic]] field**: we define $\mathbb F_p=\mathbb Z/p\mathbb Z$, then $(\mathbb F_p,+,\times)$ under the usual arithmetics modulo $p$ is a field. 
- **Field of rational functions**: for the [[Polynomial Ring]] $\mathbb F_p[X]$ consider $$\mathbb F_p(X)=\Frac\mathbb F_p[X]$$as the field of fraction ([[Integral Domain]]), then we have $|\mathbb F_p(X)|=\infty$ while $\char\mathbb F_p(X)=p$.
## Algebra over a field
Given field $F$, a $F$-algebra is a [[Ring]] $A$ that is also a [[Vector Space]] over $F$, with compatibility of scalar multiplications: $(ax)\cdot(by)=(ab)(x\cdot y),\forall a,b\in F,x,y\in A$.
- **Normed algebra**: a normed algebra $V$ is a normed [[Vector Space]] that is also an algebra over $\mathbb R$ satisfying the sub-multiplicative property: $\|vw\|\le\|v\|\cdot\|w\|$ .
	- **Distributivity over convergent sequence**: given $\sum x_n=x,y\in V$ we have that $$yx-\sum_{n=1}^Nyx_n=y\sum_{n\in\mathbb N}x_n-y\sum_{n=1}^Nx_n=y\sum_{n=N+1}^\infty x_n$$by definition RHS converges to $0$, which proves the distributivity. 
- **Tensor product**: for two $F$-algebras $A,B$, the tensor product $A\otimes_F B$ is a $F$-algebra with $$(a_1\otimes b_1)(a_2\otimes b_2)=a_1a_2\otimes b_1b_2$$and other naturally induced operations.
- **Quotient algebra**: an algebra $A$ over commutative [[Ring]] $R$ is a ring itself, and given $I$ an ideal of $A$ closed under $R$-multiplication, $A/I$ inherits the structure of an algebra over $R$ and is called the quotient algebra.
- **Graded algebra**: an algebra $A$ over $K$ is **graded** if $A=\bigoplus A_k$ where $A_k$ are algebras such that $A_k\times A_l=A_{k+l}$. 
	- **Example**: a simple example is $\mathbb R[X_1,X_2]$ with $A_k$ being the set of all homogeneous polynomials of degree $k$. [[Polynomial Ring]]
- **Algebraic & transcendental element**: for a $F$-algebra $A$, an element $a\in A$ is **algebraic over $F$**, or an **algebraic element** over $F$, if $$p(a)=0\quad\text{for some}\quad p\in F[X]$$Otherwise $a$ is called a **transcendental element**. 
	- **Field of algebraic elements**: give [[Field Extension]] $L/K$, there exists an intermediate field constructed as $$M=\set{\ell\in L:\ell\text{ is algebraic over }K}$$**Proof**: obviously $K\subset M\subset L$. Notice that for any $\alpha,\beta\in M$ we have $$[K(\alpha,\beta):K]=[K(\alpha,\beta):K(\alpha)][K(\alpha):K]<\infty$$by the simple algebraic extension result below, hence $K(\alpha,\beta)/K$ is algebraic, which means $\alpha\pm\beta,\alpha\beta,\alpha\beta^{-1}\in M$, hence $M$ is a field.