An **integral domain** is a **commutative** [[Ring]] $R$ with no nonzero zero divisor.
- **Law of cancelation**: the law of cancelation holds for integral domain, since $$ar=br\quad\iff\quad (a-b)r=0\quad\iff\quad a-b=0$$in the last equality we used the fact that $r\neq0$. 
	- **Law of cancelation for division**: by cancelation law and definition of division ([[Ring]]), $$ac\mid bc,c\neq0\imply a\mid b$$This is the key properties to deduce downstream results in [[GCD Domain]]. 
- **Field of fraction (quotient field)**: given an integral domain $R$, denote $R^*=R\backslash\{0\}$, then we define the field of fraction of $R$ as $$\Frac(R)=R\times R^*/\sim\quad\text{where}\quad(n,d)\sim(m,b)\iff nb=md$$Denote the equivalence class $(n,d)$ as $\frac{n}{d}$, then we have the operations $$\frac{n}{d}+\frac{m}{b}=\frac{nb+md}{db},\quad\frac{n}{d}\cdot\frac{m}{b}=\frac{nm}{db}$$Note that when $R$ is only commutative the $\Frac(R)$ becomes a ring of fraction.
- **Hierarchy of integral domain**: we have the hierarchical inclusion relation $$\text{Field}\subsetneq\text{Euclidean Domain}\subsetneq\text{PID}\subsetneq\text{UFD}\subsetneq\text{GCD Domain}\subsetneq\text{Integral Domain}$$The proofs are straightforward from definition. 
	- **Relation with division ring**: a commutative division ring is exactly a field by definition, but without commutativity (which is not generally assumed in the definition of a division ring) there're not a lot of things to be said. 
## Irreducible & prime element
- **Irreducibility**: for a nonzero non-unit $p\in R$, its irreducibility is defined as $$p\in\irr R\quad\iff\quad(p=xy)\implies(x\in R^\times\text{ or }y\in R^\times)$$Intuitively, an element is irreducible if it can only be factorized in a trivial manner (via unit).  
	- **Why non-unit**: reducibility is defined mainly for the discussion on unique factorization, and for units the question is meaningless - given any $a\in R,u\in\ R^\times$ we can always write $a=u^{-1}(ua)$, which introduces unnecessary complexity to the factorization. 
- **Prime**: a nonzero non-unit $p\in R$ is prime if we have the implication $$p\mid xy\imply p\mid x\qtextq{or}p\mid y$$Equivalently, $(p)$ is a prime [[Ideal]].
	- **Relation with irreducibility**: for $p$ a nonzero non-unit we have that $$p \text{ prime}\imply p\in\irr R$$**Proof**: assume otherwise that there exists a prime $p$ with factorization $$p=xy\where x,y\notin R^\times$$Applying primeness, we can assume WLOG that $$p\mid x\imply x=pt\imply x=xyt\imply x(1-yt)=0$$Since $R$ is an integral domain, we conclude that $yt=1$, i.e., $y\in R^\times$, a contradiction. 
	- **Intuition**: irreducibility and primeness could differ because:
		- **Irreducibility is an atomic property**, talking about whether an element can be broken down.
		- **Primeness is a structural property**, and governs how the element in discussion interacts with products via the ideal $(p)$. 
## Properties
- **Characterization of ideal inclusion**: for any $a, b \in R$, we have $$(a) \subseteq (b) \qiffq b \mid a$$This actually holds for any commutative [[Ring]] by definition. 
	- **Corollary**: we have the equivalence $$(a) = (b) \qiffq a = ub\text{ for some } u\in R^\times$$Strict inclusion $(a) \subsetneq (b)$ corresponds to $b$ being a proper divisor of $a$.
## Other info
- **Unique factorization domain (UFD)**: an integral domain $R$ is a UFD if any $x\notin R^\times$ can be decomposed into product of irreducible elements: $$x=p_1\cdots p_n\where p_i\in\irr R$$and the decomposition is unique up to permutation and associates.
	- **UFD is GCD domain**: we can easily verify that the product of common elements in the factorization of two elements is exactly their GCD. 
	- **Prime iff irreducible**: in UFD any irreducible is prime, therefore any element is prime iff it's irreducible. 
	  **Proof**: for any $p\in\irr R$, assume that $$p\mid xy\qtextq{while}p\not\mid x,p\not\mid y$$We must have $x,y\in\irr R$, otherwise at least one of them can be written as a multiple of $p$. By definition of UFD, we can set $$x=p_1\cdots p_m,\quad y=q_1\cdots q_n\imply p\in\set{p_1,\cdots,p_m}\cap\set{q_1,\cdots,q_n}\imply p\mid x,p\mid y$$which is a contradiction. 
 