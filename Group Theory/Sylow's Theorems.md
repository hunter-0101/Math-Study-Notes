- **Cauchy's Theorem**: If a prime $p$ divides the order of a finite group $G$, then $G$ contains an element of order $p$.
	The sketch of proof is shown below:
	1. Denote $S=\{(x_1,\cdots,x_p)|x_i\in G,x_1\cdots x_p=1\}$, then $|S|=|G|^{p-1}$.
	2. Define a equivalence relation $\sim$ that $a\sim b$ if $a$ is a cyclic permutation of $b$.
    3. Show that every equivalence class is of order $1$ or $p$, thus $|G|^{p-1}=k+pd$.
    4. Show that $p|k$ thus there is at least one element $x$ such that $x^p=1$.
## Sylow's theorems
- **Sylow's first theorem**: for $p^k\big||G|$ where $p$ is a prime, there must be a subgroup $H\le G,|H|=p^k$.
  **Proof**:
  1. let $X=\{H\subset G:|H|=p^k\}$, then $|X|=C_n^{p^k}$. Define the action of $G$ on $X$ by $g(A)=gA,g\in G$. Now we have $|X|=\sum|O_A|$.
  2. Denote $v_p(|X|)=l$. As $p^{l-k+1}\nmid|X|$, there exists an $O_A$ that $p^{l-k+1}\nmid|O_A|$. Let $H_A$ be the stabilizer of $A$, then from $|O_A|=|G/H_A|$ we know that $p^k\big||H_A|$. [[Group Actions]]
  3. As $|H_A|\le|A|=p^k$, we know that $|H_A|=p^k$.
- **Sylow's second theorem**: if $v_p(|G|)=l$, $P$ is a Sylow p-subgroup, then any subgroup $|H|=p^k$ is contained in a conjugacy of $P$.
  **Proof**:
  1. assume $|H|=p^l$ as a Sylow p-subgroup, and $|K|=p^d$ is another p-subgroup for which we wanna prove the conjugacy. Consider $K$ acting on the cosets $G/H$ as $k(aH)\mapsto kaH$.
  2. we still have $|G/H|=\sum|O_i|$, then $|O_i|$ divides $|K|=p^d$, but $(|G/H|,p)=(m,p)=1$, thus there must be some $i$ such that $|O_i|=1$.
  3. $|O|=1$ means there is a coset $aH$ that is fixed by all $k\in K$, then $$kaH=aH\Rightarrow a^{-1}kaH=H\Rightarrow a^{-1}ka\in H\Rightarrow a^{-1}Ka\le H$$
    - A $p$-group is a group of order $p^\alpha$ for some $\alpha\ge1$. A subgroup that is also a $p$-group is a $p$-subgroup.
    - If a group is of order $p^\alpha m$ where $p\nmid m$, the subgroup of order $p^\alpha$ is called a **Sylow $p$-subgroup**. The set of Sylow $p$-subgroups is denoted $\text{Syl}_p(G)$, and the number of such groups is denoted $n_p(G)$.
    - From the theorem we know that any two Sylow p-subgroups are conjugate.
- **Sylow's third theorem**: if $|G|=p^lm$ where $(p,m)=1$, then $n_p(G)|m$, and $n_p(G)\equiv 1\pmod{p}$. As a drawback we sometimes use $n_p(G)=|G:N_G(P)|$.
  **Proof**:
  1. consider $G$ acting on $\mathrm{Syl_p}(G)$, according to Sylow II there is only one orbit. Pick $H\in\mathrm{Syl}_p(G)$, then $$p^lm=|G|=|\mathrm{Stab}(\mathrm{Syl}_p(G))|\cdot|O(H)|=|\mathrm{Stab}(\mathrm{Syl}_p(G))|\cdot|\mathrm{Syl}_p(G)|$$
  2. as $H\le\mathrm{Stab}(H)$, we know that $|\mathrm{Stab}(H)|$ is divisible by $|H|=p^l$, thus $|\mathrm{Syl}_p(G)|$ divides $m$.
  3. now consider the action of $H$ on $\mathrm{Syl}_p(G)$ by conjugation. There is only one orbit of size $1$ because there is only one fixed point, and the rest are powers of $p$. Thus $$n_p(G)=|\mathrm{Syl}_p(G)|\equiv1+p+\cdots\equiv1\pmod p$$
    - **Applications of Sylow's Theorem**: The number of Sylow $p$-subgroups is denoted $n_p$, and $n_p$ divides $|G|$ and satisfies $n_p \equiv 1\pmod p$. These constraints are crucial in classifying finite groups and in proving group structure results.
## Application of Sylow's theorems
- Sylow I states the existence of subgroup of a specific order.
- Sylow II states that the subgroups within the same $\mathrm{Sym}_p(G)$ conjugates. 
	- When there is only one such subgroup, we immediately know that it is **normal**.
	- As long as a subgroup is of the same order with a Sylow subgroup we know that it is also a Sylow subgroup, thus can be represented with a conjugacy.
> [!info] Usage of conjugacy of Sylow subgroups
> $G$ is finite, $N\triangleleft G$, P is a Sylow subgroup of $N$, and $T=N_G(P)$. Show that $G=NT$.
> **Proof**: First it's easy to verify that $NT$ form a group.
> To proof $G=NT$ we only have to show $g=nt,\forall g\in G$, which can be done by showing $n^{-1}g\in T$ or $gt^{-1}\in N$ (because both $N,T$ are "normal"). Consider the **conjugacy relation of Sylow subgroups**, we know that $gP=(nPn^{-1})g\Rightarrow(n^{-1}g)P=P(n^{-1}g)$, thus $n^{-1}g\in T$. The proof is complete for the random choice of $g$.
- Sylow III put the constraint on the number of Sylow p-subgroup, which can be used to bound the number of Sylow p-subgroups.
- Each abelian group is isomorphic to product of groups of prime power order.
## Other facts related to Sylow p-group
- If $P\le H\le G$ where $P$ is a Sylow subgroup of $G$, then $P$ is also a Sylow subgroup of $H$.
- For Sylow $P\le G$, we have $P\le N_G(P)=N_G(N_G(P))$.
	- **Proof**: obviously $N_G(P)\le N_G(N_G(P))$. On the other hand, for any $x\in N_G(N_G(P))$, we have $xPx^{-1}\le xN_G(P)x^{-1}=N_G(P)$. Since all Sylow p-subgroup are conjugate, and both $P,xPx^{-1}$ are Sylow subgroups of $N_G(P)$, there exists $y\in N_G(P)$ such that $xPx^{-1}=yPy^{-1}=P$, which shows that $x\in N_G(P)$. Thus $N_G(P)=N_G(N_G(P))$.
	- This also applies to any subgroup of $N_G(P)$.