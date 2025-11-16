There are several **separation axioms** used in [[Point Set Topology]] for distinguishing to what extend two points in a topological space $X$ can be separated. The following separation axioms are listed in strengthening order. Note that for $T_3,T_4$ we require all one-point sets to be closed.
- **$T_1$ axiom**: given distinct $x_1,x_2\in X$ there exists open set s.t. $x_1\in U,x_2\notin U$ and vise versa.
	- **Equivalent characterization**: every finite point set is closed.
	- **Example**: co-finite topology of $\mathbb R$ is $T_1$, but not Hausdorff, since any pair of open sets will eventually overlap near infinity.
	- For $X$ satisfying $T_1$ axiom and $A\subset X$, the point $x\in X$ is a limit point of $A$ iff every neighborhood of $x$ contains infinitely many points of $A$.
- **Hausdorff ($T_2$)**: $X$ is Hausdorff for every pair of distinct points $x_1,x_2\in X$, these exists their neighborhoods $U_1,U_2$ respectively, that are disjoint. 
	- **Example**: consider the $K$-topology: let $K=\set{\frac{1}{n}:n\ge1}$, and define a topology on $\mathbb R$ by taking as a base all open sets in the usual topology, as well as all sets of the form $(a,b)\backslash K$. It's Hausdorff because it's finer, but not regular since $K$ is closed, and $T_2$ is not satisfied for $0,K$.
- **Regularity ($T_3$)**: $X$ is regular if for every pair $(x,B)$ of disjoint point and closed set, there exists disjoint open sets containing $x,B$ respectively.
- **Normality ($T_4$)**: $X$ is normal if for every pair $(B_1,B_2)$ of disjoint closed sets, there exist disjoint open sets containing $B_1,B_2$ respectively.
	- **Counterexamples**: consider the Sorgenfrey plane $\mathbb R_l^2$ where $\mathbb R_l$ denotes the lower limit topology, which is not normal. To see this, denote $D=\set{(x,-x)},A=D\cap\mathbb Q,B=D\backslash A$, and notice that there is no pair of disjoint open sets $(U,V)$ s.t. $A\subset U,B\subset V$. Note that both $A,B$ are closed in $\mathbb R_l^2$ because $D$ is closed in $\mathbb R_l^2$ and any singleton is open in $L$.
The notation $T$ comes from "Trennungsaxiom" in German, meaning "separation axiom".
- Hausdorff and regular axioms are preserved under taking subspace and product space, but normality is not. 
## Normal space
- Second-countable regular space is normal.
- Metrizable space is normal.
- Compact Hausdorff space is normal.
- Well-ordered set is normal in order topology.
- **Urysohn lemma**: for normal $X$ and disjoint closed subsets $A,B$, let $[a,b]\subset\mathbb R$, then there exists continuous $f:X\to[a,b]$ s.t. $f(A)=a,f(B)=b$.
  **Proof**: WLOG take $[a,b]=[0,1]$. Proceed as follows:
  1. Denote $P=\set{p_n}$ the set of rationals within $[0,1]$, and define a set of open sets $\set{U_p}_{p\in P}$ as follows: let $A\subset U_0,U_1=X-B,$ with $\overline{U_0}\subset U_1$, and recursively define other open sets s.t. $p<q\Rightarrow\overline{U_p}\subset U_q$ (this can be down by normality). 
  2. Let $U_p=\varnothing,p<0$, and $U_p=X,p>1$, which extends the definition without violating the inclusion relation. 
  3. Define $\mathbb Q(x)=\set{p:x\in U_p}$, and let $f(x)=\inf\mathbb Q(x)$. 
  Now It can be verified that $f$ has the desired property.
	- For any two subsets of topological space $X$ that can be endowed a continuous function as above, we say they **can be separated by a continuous function**.
	- **Completely regular ($T_{3.5}$)**: if any pair of point and disjoint closed set can be separated via continuous function, then the space is said to have **complete regularity**.
- **Tietze extension theorem**: for normal $X$ and closed subspace $A\subset X$, any continuous map $f:A\to[a,b]$ can be extended to a continuous $f:X\to[a,b]$; any continuous map $f:A\to\mathbb R$ can be extended to a continuous $f:X\to\mathbb R$.
  **Proof**: the main idea is to construct a sequence of continuous $s_n$ on $X$ that converges uniformly with $s_n|_A\to f$.
  1. **Approximation with bound decay**: given $f:A\to[-r,r]$, we can construct a $g:X\to\mathbb R$ in the following way: notice that $f^{-1}([-r,-r/3]),f^{-1}([r/3,r])$ are disjoint and closed in $A$, hence closed in $X$. By Urysohn lemma we can find some $g:X\to[-r/3,r/3]$ such that $|f(x)-g(x)|\le r/3$ for all $x\in X$.
  2. **Finite image case**: WLOG let $[a,b]=[-1,1]$. Using step 1 we construct $g_1$, and repeat the process on $f-\sum g_n=f-s_n$ we get $g=\sum_{n=1}^\infty g_n(x)=f$, where convergence and continuity is guaranteed by M-test. $\im g=[-1,1]$ is also automatically satisfied.
  3. **Infinite image case**: by homeomorphism we can replace $\mathbb R$ with $(0,1)$. 2 shows that we can extend $f$ to some $g:X\to[-1,1]$. To get an open image define $D=g^{1}(\set{1})\cup g^{-1}(\set{1})$, then $D$ is closed. Since $g(A)=f(A)\subset(0,1)$, $A$ is disjoint from $D$, hence by Urysohn lemma there exists continuous $\phi:X\to[0,1]$ s.t. $\phi(D)=0,\phi(A)=1$. Let $h(x)=\phi(x)g(x)$, then it can be verified that $h$ qualified as an extension of $f$ to $X$ satisfying the requirements.
	- **Counterexample**: some examples that all conditions are necessary includes:
		- **Normality**: required by Urysohn lemma.
		- **Closed-ness of subspace**: take $X=C$ the unit circle and let $A=X\backslash\set{P=(0,1)}$ with $f$ being any continuous function such that $f(P^+)\neq f(P^-)$.
## Examples
- **Co-finite topology**: consider a infinite set $X$, and let $\mathcal{T}=\{S\subset X:|S^C|<\infty\}$. Then $\mathcal{T}$ is a topology called co-finite topology, and it's easy to verify that $\mathcal{T}$ is non-Hausdorff.
- **Co-countable topology**: consider an uncountable set $X$, and let $\mathcal{T}=\{S\subset X:S^C\text{ is countable}\}$. All non-empty open sets intersect, thus it's non-Hausdorff.
- **Line with doubled origin**: consider $X=(R\backslash\{0\})\cup\{0_1,0_2\}$ where $0_1,0_2\notin R$ are two distinct symbols. Let $\mathcal{T}=\{(-\epsilon,0)\cup\{0_k\}\cup(0,\epsilon):\epsilon>0,k=1,2\}$. Then every neighborhood of $0_1$ intersects every neighborhood of $0_2$, thus it's non-Hausdorff.