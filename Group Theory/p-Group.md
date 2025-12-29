A $p$-group is a finite [[Group]] $P$ with $$|P|=p^n,\quad n\in\mathbb N$$
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
## Basic properties
- **Center**: the center of a $p$-group $P$ is non-trivial. 
  **Proof**: consider the class equation $$p^n=|P|=|Z(P)|+\sum_{i}|G:C_G(g_i)|$$When $P$ is abelian we have $Z(P)=P$, otherwise $$C_G(g_i)<G\imply p\mid|G:C_G(g_i)|\imply p\mid |Z(P)|$$Since $e\in Z(P)$ we have $|Z(P)|\ge p$, hence the center is always nontrivial. 
### Elementary abelian p-group
An elementary abelian p-group $P$ is an abelian group in which all non-identity element has the same prime order $p$ (it's easy to see that the shared order can only be prime).
- As any subgroup of abelian group is normal, we can deduce that for a elementary abelian p-group $P$, we have $$P\cong\prod_{i=1}^n C_p$$
- $P$ can actually be viewed as a vector space over the field $\mathbb{Z}_p$.
- $\Phi(P)=\{1\}$.
	- **Proof**: as $P\cong\prod C_p$, let $M_1=1\times C_p\times\cdots\times C_p, \cdots,M_n=C_p\times\cdots\times C_p\times 1$, then$$1=\bigcap_{i=1}^nM_n\ge\Phi(P)$$
Note that Elementary group need not to be abelian. See [[Group Gallery#Elementary group]].