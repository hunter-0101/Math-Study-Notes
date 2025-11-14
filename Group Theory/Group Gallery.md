- **Group of $G$-valued functions on $X$**: denote $G^X$ the group formed by maps $f:X\to G$ with multiplication defined as $(f_1f_2)(x)=f_1(x)f_2(x)$. This is obviously a group. We also denote $G^{(X)}$ the group of $G$-valued functions s.t. $f(x)=e$ for almost all $x\in X$.
- **Matrix group**: see [[Matrix Group]].
## Euclidean group
The Euclidean group $E_n$ is the group of isometries (transformations that preserve the Euclidean distance) of a Euclidean space $E^n$.
- **Orthogonal group**: $O_n$ consists of orthogonal transformations preserving a fixed point. $O_n$ is parameterized by a $n\times n$ matrix with $n(n-1)/2$ degree of freedom.
- **Translation group**: $T_n\cong R_n$ with $n$ degree of freedom. We can write $$E_n\cong T_n\rtimes_\tau O_n$$where $\tau$ is any automorphism of $T_n$ associated with $O_n$. Thus $E_n$ has $n(n+1)/2$ degree of freedom.
- $SO_n$ is those whose determinant is $1$, i..e., $SO_n=O_n\cap SL_n$. We have $SO_n=E_n^+/T_n$.
## Affine group of $Z_n$
Fix $n\in N$, for any $a\in Z_n,u\in Z_n^*$, we define the bijective function $$f_{a,u}:Z_n\to Z_n,\quad r\mapsto ur+a$$and define the affine group as $$\mathrm{Aff}_n=\Set{f_{a,u}|a\in Z_n,u\in Z_n^*}\le S_{Z_n}$$then it can be seen that we have the semi-direct product $$\mathrm{Aff}_n\cong Z_n\rtimes_\mu Z_n^*$$where $\mu:Z_n^*\to \aut(Z_n)$ is the isomorphism given by $u\mapsto f_{0,u}$.
## Dihedral group
Denoted $D_{2n}$, dihedral group contains all symmetries of a regular $n$-gon. We have $$D_{2n}=\{1,r,\cdots,r^{n-1},s,sr,\cdots,sr^{n-1}\}=\langle r,s|r^n=s^2=1,srs^{-1}=r^{-1}\rangle=\langle r,s|r^n,s^2,(rs)^2\rangle$$
- **Generalized dihedral group**: let $G$ be a group and $A\lneq G$. If all the elements in $G\backslash A$ have order $2$, then either all elements in $G$ have order $2$, or $\exists a\in A,|a|>2$, in this case we must have $G$ non-abelian and $|G:A|=2$. Such $G$ is called the **generalized dihedral group** with distinguished subgroup $A$.
	- **Proof**
	  1. $\forall g\in G\ A,a\in A$, we have $gag^{-1}=a^{-1}$.
	  2. $A$ is an abelian normal subgroup of $G$.
	  3. When $|a|=2,\forall a\in A$, we have $|g|=2,\forall g\in G$; if $\exists a\in A,|a|>2$, then it can bee shown that $G$ is non-abelian (otherwise every element in $A$ has order $2$), and the coset of $A$ is unique (otherwise any two representatives commutes, making $G$ abelian). Above combined, such $G$ can be expressed as $$\mathrm{Dih}(A)=A\rtimes_\phi C_2$$ with $\phi(0)$ the identity and $\phi(1)$ inversion. This is a complete description of all generalized dihedral groups. [[Product Group]]
## Cyclic group
Denote $C_n=\langle a|a^n\rangle$ the cyclic group of order $n$. In general we have $$C_n\simeq\begin{cases}\mathbb Z,&n=\infty\\\mathbb Z/n\mathbb Z,&n<\infty\end{cases}$$
- If $(m,n)=1$ then $C_m\times C_n\cong C_{mn}$. See proof in [[Product Group]].
	- As a corollary, $C_m\times C_n\cong C_{(m,n)}\times C_{[m,n]}$. 
- **Primary cyclic group**: when $n=p^k,p\in\mathbb P$ we call $C_n$ a primary cyclic group.
- $\aut(C_n)\cong Z_n^*=\{[k]_n|[k]_n\text{ invertible in }Z_n\}$. Thus $|\aut(C_n)|=\varphi(n)$ where $\varphi$ is the Euler function. [[Group Homomorphism]]
## Symmetric group
For nonempty set $\Omega$, let $S_\Omega$ (or $\Sigma(\Omega)$) be the set of all bijections from $\Omega$ to itself. Define function composition $\circ$, then $(S_\Omega,\circ)$ is the symmetric group on set $\Omega$.
- **Support**: for $\sigma\in S_n$, define $\supp(\sigma)=\{j:\sigma(j)\neq j\}$. When $supp(\sigma)\cap supp(\tau)=\varnothing$ we say that they're **disjoint**.
	- For disjoint $\sigma,\tau$, we have $\sigma\tau=\tau\sigma, supp(\sigma\tau)=supp(\sigma)\cup supp(\tau)$ (the converse also holds), and since $\sigma^i,\tau^j$ are always disjoint we have $$|\sigma\tau|=[|\sigma|,|\tau|]$$
- We have $S_\Delta\cong S_\Omega$ if $|\Delta|=|\Omega|$, with the isomorphism $\phi(\sigma)=\theta\circ\sigma\circ\theta^{-1}$ for some $\theta:\Delta\to\Omega$.
- **Disjoint cycle decomposition**: to effectively express $\sigma\in S_n$, a cycle is a string of integers which represents the element of $S_n$ that cyclically permutes these integers, shown as $\sigma=(a_1,\cdots,a_{m_1})\cdots(a_{m_{k-1}+1},\cdots,a_{m_k})$. Note that $1$-cycle will not be written.
- **Conjugate class**:For any $k$-cycle $\psi=(i_1,\cdots,i_k)$ and $\beta\in S_n$, we have $$\beta\psi\beta^{-1}=(\beta(i_1),\cdots,\beta(i_k))$$Thus the $\cl(\psi)=\{\phi\in S_n:\phi\text{ is k-cycle}\}$. Further, for any $\sigma\in S_n$, we have $$Cl(\sigma)=\{\tau\in S_n:\tau\text{ have same number of k-cycles as }\tau,\forall k\}$$
- **Generator**: the symmetric group can be generated with $n-1$ transpositions or one transposition together with a $n$-cycle:$$S_n=\langle(1,2,\cdots,n),(1,2)\rangle=\langle(1,2),(1,3),\cdots,(1,n)\rangle=\langle(1,2), (2,3),\cdots,(n-1,n)\rangle$$Note that for an arbitrary $\tau=(a,b)$, $S_n=\langle(1,\cdots,n),\tau\rangle$ iff $(b-a,n)=1$. This can be shown by considering in what case can all transpositions $(1,k)$ be generated by $(1,\cdots,n)^{-k}\tau(1,\cdots,n)^k$.
- **Automorphism on symmetric group**: we have $$\aut(S_n)=Inn(S_n)\cong S_n$$this can be shown by looking only at the generators $(i,i+1)$, combined with the fact that automorphism preserves order.
### Alternating group
- **Sign of a permutation**: define the sign function of a $\sigma\in S_n$ by$$sng(\sigma)=\prod_{(i,j)}\frac{\sigma(i)-\sigma(j)}{i-j}$$it can be shown that $sng(\sigma\tau)=sgn(\sigma)sgn(\tau)$. we now define the **alternating group** as $$A_n=\ker\operatorname{sgn}=\{\sigma\in S_n:\sigma\text{ is even permutation}\}$$
	- It can be easily shown (by consider the transposition generators) that $sgn$ is the only surjective homomorphism from $S_n$ to $\{1,-1\}$. This, to some extent, verifies the uniqueness of [[Determinant]] as an alternating multilinear function.
- **Extending Cayley's theorem**: for any $n$, $S_n$ is isomorphic to a subgroup of $A_{n+2}$ (the isomorphism can be constructed with a natural projection and the last to entries for adjusting the sign). Thus any group $G$ is isomorphic to a subgroup of $A_{|G|+2}$. 
- **Generator**: $A_n$ is generated by all $3$-cycles or permutations of type $(2,2)$.
	- **Proof**
	  1. $1=(123)(132)$.
	  2. For any $\tau\in A_n\subset S_n$, we can decompose it into transpositions $\tau=\prod_1^r\sigma_k$. $r$ is even since $\tau$ is even, thus we can separate them into $r/2$ pairs.
	  3. Any $\sigma_k\sigma_{k+1}$ can be written as product of two $3$-cycles. This complete the proof.
- **Simplicity of $A_n$ for $n\ge5$**: the key idea is that, it's possible to construct a $3$-cycle using elements form any conjugacy class.
	- **Proof 1: directly showing that ay $N\triangleleft G$ contains the generator of $A_n$**. 
	  1. **$A_n\triangleleft S_n$ is the only normal subgroup**: for a specific $\sigma\in N\triangleleft G$, we can pick a $\sigma(i)\neq i$ and $j\neq\sigma(i)$. Now let $\tau=(ij)$, then we have $$\sigma\tau\sigma^{-1}\tau^{-1}=(\sigma(i)\sigma(j))(ij)$$which is either a $3$-cycle or a permutation of type $(2,2)$. By the generator of $A_n$ and the property of conjugacy class, we know that $A_n\subset N$. By Lagrange's theorem $A_n$ is the only normal subgroup.
	  3. Transitivity of normality directly yields the result.
	- **Proof 2: Proof by reducing to simple case**.
	  1. **Group $A_6$ is simple**: this can be directly checked by looking at its conjugacy classes.
	  2. **$N\triangleleft G$ contains $3$-cycle**: for $\sigma(1)=i\neq1$ (we can obtain this by relabeling), let $\tau=(ijk)$, then $\tau\sigma\tau^{-1}=\tau(\sigma(1))\neq\sigma(1)$, so $\phi=\tau\sigma\tau^{-1}\sigma^{-1}\neq1$. Notice that $$\phi=(\tau\sigma\tau^{-1})\sigma^{-1}\in N,\quad\phi=\tau(\sigma\tau^{-1}\sigma^{-1})\text{ is product of two 3-cycles}$$Now let $H$ be the copy of $A_6$ within $A_n$ (may be augmented if number of elements involved is less than $6$), then $H\cap N$ is nontrivial and normal. However $H\cong A_6$ is simple, thus $H\cap N=H\Rightarrow H\subset N$, which means $N$ contains a $3$-cycle.
## $p$-group
A group $P$ is called a p-group if $|P|=p^n$ for some $n\in Z$.
- **Frattini subgroup**: for p-group $P$, by the property of Frattini quotient below we know that the $\Phi(P)$ contains all $\langle x^p\rangle$ and $[P,P]$, thus we have $$\Phi(P)=P^p[P,P]$$
	- **Frattini quotient**: For any p-group $P$, the Frattini quotient $P/\Phi(P)$ is en elementary abelian group. ($\Phi(P)$ refers to the Frattini subgroup [[Group#Subgroups]])
		- **Proof**: by definition $\Phi(P)=\bigcap M$ for all maximal subgroups $M\le P$. 
		  1. **We have $|P:M|=p$**: since $P$ has a non-trivial center, if $Z\subset M$ by induction on $|P|$ we can show that $|P:M|=p$; if $Z\not\subset M$ then $P=ZM$, thus $|P:M|=p$.
		  2. Since $P/M\cong C_p$ we know that $P^p\subset M$; since $[P,P]$ is the smallest subgroup by which the quotient group is abelian, thus $[P,P]\subset M$. By definition we have $P^p[P,P]\le\Phi(M)$, completing the proof.
	- **Proof of the expression of $\Phi(P)$**: from above we know that $P^p[P,P]\le\Phi(P)$. Now that $P/\Phi(P)$ is elementary abelian, we know that $P/\Phi(P)\cong\prod C_p$, thus every elements within it is non-removable from some generating set. Hence $\Phi(P)=P^p[P,P]$.
- **Lattice of p-groups**: two p-groups with isomorphic subgroup lattice is of the same order. [[Group#Lattice of subgroups]]
	- **Proof**: it suffices to show that when $|P_1|\neq|P_2|$ their lattice non-isomorphic. For a $|P|=p^n$, by Sylow's theorem there exists a subgroup $P'\le P$ with $|P'|=p^{n-1}$. Apply this repeatedly we get a chain of length $n-1$. Now it can be easily seen that the **longest length** characterize the order of the group, thus yielding the result.
- p-groups are solvable and nilpotent. This can be directly derived from the fact that the center of p-group is not trivial. [[Solvable Group]]
- **p-group of special order**
	- $|G|=p^2$ is abelian
### Elementary abelian p-group
An elementary abelian p-group $P$ is an abelian group in which all non-identity element has the same prime order $p$ (it's easy to see that the shared order can only be prime).
- As any subgroup of abelian group is normal, we can deduce that for a elementary abelian p-group $P$, we have $$P\cong\prod_{i=1}^n C_p$$
- $P$ can actually be viewed as a vector space over the field $\mathbb{Z}_p$.
- $\Phi(P)=\{1\}$.
	- **Proof**: as $P\cong\prod C_p$, let $M_1=1\times C_p\times\cdots\times C_p, \cdots,M_n=C_p\times\cdots\times C_p\times 1$, then$$1=\bigcap_{i=1}^nM_n\ge\Phi(P)$$
Note that Elementary group need not to be abelian. See [[Group Gallery#Elementary group]].
## Quaternion Group
Denoted as $Q_8$, it is a non-abelian group of order 8 related to the quaternions.
- **Elements**: $Q_8 = {\pm 1, \pm i, \pm j, \pm k}$, where $i, j, k$ are quaternion units satisfying:
	- $i^2 = j^2 = k^2 = ijk = -1$,
    - $ij = k$, $ji = -k$, $jk = i$, $kj = -i$, $ki = j$, and $ik = -j$.
## Elementary group
We use $\mathcal{E}$ to denote the class of all non-trivial elementary groups ,i.e., all elements are of the same (prime) order.
- $G\in\mathcal{E}$ is abelian iff $G$ is a vector space over $\mathbb{F}_p$.
	- Proof: any vectors space over $\mathbb{F}_p$ is obviously abelian. Conversely, if $G$ abelian, then every element corresponds to a coordinate under any proper generator, thus is a vector space over $\mathbb{F}_p$.
- **Non-abelian elementary group**: 
	- **Example**: the Heisenberg group is a non-abelian group of order $p^3$. [[Group Gallery#Matrix Groups]]