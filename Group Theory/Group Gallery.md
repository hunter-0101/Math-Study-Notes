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
	  3. When $|a|=2,\forall a\in A$, we have $|g|=2,\forall g\in G$; if $\exists a\in A,|a|>2$, then it can bee shown that $G$ is non-abelian (otherwise every element in $A$ has order $2$), and the coset of $A$ is unique (otherwise any two representatives commutes, making $G$ abelian). Above combined, such $G$ can be expressed as $$\mathrm{Dih}(A)=A\rtimes_\phi C_2$$ with $\phi(0)$ the identity and $\phi(1)$ inversion. This is a complete description of all generalized dihedral groups. [[Product of Groups]]
## Cyclic group
Denote $C_n=\langle a|a^n\rangle$ the cyclic group of order $n$. In general we have $$C_n\simeq\begin{cases}\mathbb Z,&n=\infty\\\mathbb Z/n\mathbb Z,&n<\infty\end{cases}$$this group is sometimes denoted $\mathbb Z_n$, and is quite useful in many different fields as prototype for algebraic structure formed by a nilpotent element.
- If $(m,n)=1$ then $C_m\times C_n\cong C_{mn}$. See proof in [[Product of Groups]].
	- As a corollary, $C_m\times C_n\cong C_{(m,n)}\times C_{[m,n]}$. 
- **Primary cyclic group**: when $n=p^k,p\in\mathbb P$ we call $C_n$ a primary cyclic group.
- $\aut(C_n)\cong Z_n^*=\{[k]_n|[k]_n\text{ invertible in }Z_n\}$. Thus $|\aut(C_n)|=\varphi(n)$ where $\varphi$ is the Euler function. [[Group Homomorphism]]
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