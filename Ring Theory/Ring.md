A **ring** is a tuple $(R,+,\cdot)$ of a [[Set]] $R$ and two binary operations $+,\cdot:R\times R\to R$ satisfying:
1. **Group structure**: $(R,+)$ is an abelian group, and $(R,\cdot)$ is a monoid ([[Group]])
2. **Compatibility (distributivity)**: $+$ is distributive w.r.t $\cdot$.
By definitions additive and multiplicative identities $0,1$ are unique. Some authors do not require **existence of multiplicative identity** in the definition of ring, which we'll refer to as a **rng** in this vault. We say that $R$ is **commutative** if $\cdot$ is commutative, which is assumed in most cases.
- **Discussion**: ring is an algebraic structure proposed to generalize previous concepts like 1). Dedekind domain that arises in number theory. 2). [[Polynomial Ring]] and ring of invariants that occur in algebraic geometry and invariant theory. They later proved useful in other branches of math such as geometry and analysis. 
	- **Comparison with [[Group]]**: effectively speaking, a ring possess a second operation compared to group, but the crucial distinction lies in their **structural rigidity**. Two operations, together with the interactions between them, brings more rigidity to the algebraic structure, making the overall theory much richer. 
	- **Kinetic group vs. stationary ring**: we may have the feeling that ring theory is more "ring-central", while group theory is more "action-central". This is due to the fact that a ring $R$ is often viewed as a **universe of scalers**, and we care more about its internal structure; for groups, in contrast, is almost **doing something**: even it cannot act on a set, it can always act on itself. 
- **"Ring action"**: parallel to [[Group Action]], the concept of "ring action" is actually formalized by [[Module]] theory. More can be found in that note. 
## Basic concepts
- **Unit**: $a\in R$ is a unit if it's multiplicatively invertible. The set of units in $R$ is denoted $R^\times$. 
	- **Division ring**: $R$ is said to be a division ring (skew field) if $R^\times=R\backslash\set{0}$. It's obvious that a (commutative) division ring is necessarily an [[Integral Domain]]. 
	- If $u\in R^\times$ and $s$ is nilpotent in a commutative ring $R$, then $u+s\in R^\times$. We only need to expand the geometric series $(1+(u^{-1}s))^{-1}$.
	- **A non-unit is always contained in some maximal (left/right) ideal**: for $a$ not irreversible, consider the (left/right) ideal $(a)$. Now let the ideal extend, and by Zorn's lemma we're always able to find a biggest ideal among the extension chain, which is the maximal (left/right) ideal containing $a$.
- **Characteristic**: define $\char(R)=|1|_+$ where $|\cdot|_+$ indicates the order in $(R,+)$ ([[Group]]). We define $\char(R)=0$ if such positive integer does not exist.
	- **Alternative definition**: $\char(R)$ is the unique $k\in\mathbb N$ s.t. for homomorphism $\chi:\mathbb Z\to R$ we have $\ker\chi=k\mathbb Z$. Note that the homomorphism is unique because it's totally determined by the image of $1_{\mathbb Z}$, which must be mapped to $1_R$. We define the $P_R=\operatorname{im}\chi$ the **prime subring**. Thus $$P_R\cong\mathbb Z/\ker\chi\Rightarrow \char(R)=k\text{ iff }P_R\cong \mathbb Z_k$$
	- We could also define the characteristic to be the exponent of the additive group.
	- If there exists homomorphism $f:A\to B$, then $char(B)\mid char(A)$. As a corollary, for any $T\le R$ we have $\char(T)=\char(R)$.
- **Nilradical**: the nilradical of a **commutative ring** $R$ consists of all nilpotent elements:$$r(R)=\set{f\in R:f^m=0\text{ for some }m\in \mathbb Z_{>0}}$$
	- **For commutative $R$, $r(R)$ equals the intersection of all prime ideals**: obviously $r(R)$ is contained in any prime ideal (because prime ideal contains $0$). Conversely if $f\notin r(R)$, then using Zorn's lemma we can find a prime ideal that does not contain $f$.
	- Since every maximal ideal is prime, we have that $J(R)\subset r(R)$.
- **Subring**: a subring of the ring $R$ is a additive subgroup of $R$ that is closed under multiplication. The [[Lattice]] of subrings of $R$ will be denoted $\sub R$. 
	- **Center**: $Z(R)=\{r\in R:ar=ra,\forall a\in R\}$.
		- $Z(M_n(R))\cong Z(R)$, as the center consists of all $rI$.
## Divisor & division relation
Division relation on $R$ is defined by $$a\mid b\qiffq ax=b\text{ for some }x\in R$$We say that $a$ is a **left divisor** of $b$, and $b$ is a **right multiple** of $a$. Similarly we can define right divisor and left multiple. A divisor that is both a left & right divisor is called a **two-sided divisor**. 
- **Associates**: the equivalence [[Relation]] of being associates is defined by $$a\sim b\qiffq a\mid b,b\mid a\qiffq b=ua\text{ for some }u\in R^\times$$It can be easily verify that this equivalence relation interacts greatly with division relation, and when talking about division relation between two elements we're actually talking about that between two equivalence classes. For convenience, in such cases we'll be using $\sim,=$ interchangeably. 
	- **Unit relation**: under the equivalence relation induced by associates, we have $$u\sim 1,\quad\forall u\in R^\times$$Therefore invertible elements are always neglected in division-related discussion. 
- **GCD & LCM**: $d=\gcd(a,b)$ if it's a common divisor of $a,b$, and any common divisor of $a,b$ divides $d$. We can define $m=\lcm(a,b)$ in a similar manner. More about this can be found in [[GCD Domain]].
	- **Uniqueness issue**: GCD (LCM) is obviously unique up to associates by definition. 
	- **Coprime elements**: $a,b$ are said to be coprime if their generated [[Ideal]]s are coprime. By definition this is equivalent to $\gcd(a,b)\sim1$. 
- **Zero divisor**: $a$ is a zero divisor if there exists $b\neq0$ s.t. $ab=ba=0$. We can it left/right zero divisor when only one of them equals $0$.
## Ring homomorphisms
A **ring homomorphism** is a structure preserving function $\phi:(R,+_R,\cdot_R)\to (S,+_S,\cdot_S)$ s.t. 
1. $\phi:(R,+_R)\to(S,+_S)$ is a [[Group Homomorphism]].
2. $\phi:(R,\cdot_R)\to(S,\cdot_S)$ is a monoid homomorphism.
For rng we do not require the correspondence of identity. Special kinds of homomorphisms like monomorphism, epimorphism, endomorphism, and automorphism are defined similarly as in [[Group Homomorphism]].
- **Kernel & image**: $\ker\phi$ is a two-sided [[Ideal]] of $R$, and $\im\phi$ is a subring of $S$.
	- $\phi:(R^*,\cdot_R)\to(S^*,\cdot_S)$ is a group homomorphism.
- **Preimage/image of subring**: for $\phi:R_1\to R_2$ and $S_1\le R_1,S_2\le R_2$, we have $$\phi^{-1}\circ\phi(S_1)=S_1+\ker\phi,\quad\phi\circ\phi^{-1}(S_2)=S_2$$Intuitively, to map the image back it's necessary to add back the "vanishing element", while to map a preimage into the image nothing need to change.
All theorems can find their corresponding analogies in [[Group Homomorphism]]
- **Fundamental theorem of homomorphism**: let $\phi:R\to S$ a ring homomorphism, $I$ an ideal of $R$, and $\pi:R\to R/I$ the canonical projection. Suppose that $I\subset\ker\phi$, then there is a unique induced homomorphism $\overline\phi:R/I\to S$ s.t. the following diagram commutes:
  <p align="center"><img align="center" src="https://i.upmath.me/svg/%0A%5Cbegin%7Btikzcd%7D%0AR%20%5Carrow%5Br%2C%20%22%5Cphi%22%5D%20%5Carrow%5Bd%2C%20%22%5Cpi%22'%5D%20%26%20S%20%5C%5C%0AR%2FI%20%5Carrow%5Bru%2C%20%22%5Coverline%5Cphi%22'%5D%20%20%20%20%20%20%26%20%20%0A%5Cend%7Btikzcd%7D%0A"  /></p>
  with $\im\overline\phi=\im\phi,\ker\overline\phi=\ker\phi/I$. In particular, when $I=\ker\phi$, we have $R/\ker \phi\cong\im\phi$.
- **First isomorphism theorem**: let $I$ be an ideal of $S$ and $R\le S$ a subgroup, then $R+I$ is a subring of $S$ and $I\cap R$ is an ideal of $R$, and we have $R/(I\cap R)\cong(R+I)/I$.
- **Second isomorphism theorem**: let $I,J$ be ideals of $R$ with $I\subset J$, then there is a canonical isomorphism $(R/I)/(J/I)\cong R/J$.
- **Correspondence theorem**: given $I\in\Id R$, we have the lattice isomorphism $$\sub_IR\cong \sub R/I ,\quad S\mapsto \overline S=S/I$$This follows from the correspondence theorem of [[Group Homomorphism]], noticing that $$s_1s_2\in S,\forall s_1,s_2\in S\qiffq(s_1+I)(s_2+I)=s_1s_2+I\in S/I,\forall s_1,s_2\in S$$which is just the definition of quotient ring ([[Ideal]]). 
### Automorphism
We define $\aut(R)$ to contain all ring automorphisms of $R$. Sometimes $\aut(R,+)$ or $\aut(R,\cdot)$ is used to restrict the discussion to group/monoid.
- Consider only the inner automorphisms, we have $$\psi:R^*\to \aut(R),\quad\psi(u)=\gamma_u$$where $\gamma_u$ is the conjugation by $u$. Clearly, $\ker\psi=Z(R)\cap R^*$.
- **Skolem-Noether theorem**: for simple unitary rings $A,B$ and $K=Z(B)$, $K$ is a field due to simplicity. If the dimension of $B$ over $K$ is finite, and $A$ is also a $K$-algebra, then given $K$-algebra homomorphisms $f,g:A\to B$, there exists a unit $b\in B$ such that $$g(a)=b\cdot f(a)\cdot b^{-1}$$In particular, every automorphism of a central simple $K$-algebra is an inner automorphism.
- Given $\phi\in\aut(R,+)$, if for any $a,b\in R$ at least one of the following holds: $$\phi(ab)=\phi(a)\phi(b)\quad\text{or}\quad\phi(ab)=\phi(b)\phi(a)$$then $\phi$ is either an automorphism or an anti-automorphism for $(R,\cdot)$.
  **Proof**: for any $a\in R$ denote $$l(a)=\set{r\in R:\phi(ar)=\phi(a)\phi(r)},\quad r(a)=\set{r\in R:\phi(ar)=\phi(r)\phi(a)}$$then since $\phi\in\aut(R,+)$ we know that $l(a),r(a)\le(R,+)$, hence by the avoidance lemma ([[Group]]) and the assumption we have either $l(a)=R$ or $r(a)=R$. Now we set $$l(R)=\set{r\in R:l(r)=R},\quad r(R)=\set{r\in R:r(r)=R}$$then the above argument can be repeated, showing that either $l(R)=R$ or $r(R)=R$, i.e., $\phi$ is an automorphism or an anti-homomorphism. 
## Examples of rings
- **[[Polynomial Ring]]**: a common example of PID is the polynomial ring in one indeterminant $F[X]$ over some [[Field]] $F$. When generalizing to several indeterminants $$F[X_1,\cdots,X_n]\where X_iX_j=X_jX_i,\forall i\neq j$$Then we're getting a noetherian ring that is a UFD but not a PID. 