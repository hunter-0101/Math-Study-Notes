Refer to [[Set Theory]] for basic information on set theory.
Assuming **axiom of choice** ([[Set Theory]]), the cardinality of a set $X$, denoted $|X|$, is the least ordinal number $\alpha$ such that there is a bijection between $X$ and $\alpha$. The transfinite sequence of cardinal numbers:$$0,1,2,\cdots,n,\cdots;\aleph_0,\aleph_1,\cdots,\aleph_\alpha,\cdots$$which starts with natural numbers and followed by the aleph numbers. The aleph numbers are indexed by ordinal numbers.
- $|X|=|Y|$ iff there exists a bijection between them. ($\ge,\le$ respectively for surjection and injection)
	- **Schröder-Bernstein theorem**: if $|X|\le |Y|,|Y|\le |X|$, then $|X|=|Y|$. 
	  **Proof**: for any $x\in X$ or $y\in Y$ define a sequence of the form $$\cdots\to f^{-1}\circ g^{-1}(x)\to g^{-1}(x)\to x\to f(x)\to g\circ f(x)\to\cdots$$that is, alternatively apply $f,g$ in both sides. This forms a partition of elements in $X\cup Y$, if we assume WLOG that $X\cap Y=\varnothing$. Now obvious there are three possible cases: the sequence may terminate to the left at $x\in X,y\in Y$, or not terminate. For each of the three cases we can define a bijection between $X$ and $Y$ alternatively. 
- **Cantor's theorem**: $f:A\to\mathcal P(A)$ is not surjective, thus $|A|<|\mathcal P(A)|$. As a consequence there is no largest cardinality.
  **Proof**: consider $B=\set{x\in A:x\notin f(x)}\in\mathcal P$. If $f$ is surjective, then there exists $\xi\in A$ such that $f(\xi)=B$. Since $x\in B\iff x\notin f(x)$, we have $\xi\in B\iff\xi\notin f(\xi)$, which yields a contradiction of the form $\varphi\iff\lnot\varphi$, because $f(\xi)=B$.
	- **[[Diagonal Argument]]**: the construction of $B$ can be seen as a diagonal argument. If we consider the table of column coordinate $x_n$ and row coordinate $f(x_n)$, each cell labeled $T$ or $F$ for $x_i\in f(x_j)$ or $x_i\notin f(x_j)$, then $B$ consists of those $n$ whose diagonal entry is $F$. That is, it inverts all entires through the diagonal, thus is not contained in $f(x_n)$.
## Countability
- **Finiteness**: a set $X$ is finite if $|X|=n$ for some $n\in\mathbb N$, i.e., $|X|<\aleph_0$.
- **Countability**
	- If $|X|\le|\mathbb{N}|$, then $X$ is **countable**. $|\mathbb{Z}|=|\mathbb{Q}|=|\mathbb{N}|:=\aleph_0$.
	- If $|X|\ge |\mathbb{R}|$, then $X$ is **uncountable**. Here $|\mathbb{R}|=c$ is the **cardinality of the continuum**. We have $|\mathcal{P}(\mathbb{N}))|=2^{\aleph_0}=\mathfrak c$.
	- **Continuum hypothesis**: the hypothesis says that $\aleph_1=2^{\aleph_0}$. This is independent of ZFC, i.e., neither itself nor its negation can be proved provided that ZCF is consistent.
- **[[Set Theory]] operations**
	- **Union**: given $A_n$ countable for all $n\in\mathbb N$, then $\bigcup_{n\in\mathbb N}A_n$ is also countable. This is obvious by the re-indexing $a_{ij}$ and use a zig-zag path.
	- **Power**: $\mathbb N^\mathbb N=\mathfrak c$.
- **Examples of (un)countability**
	- Let $E\subset \mathbb R^d$ s.t. $d(x,y)\in\mathbb Q,\forall x,y\in E$, then $E$ is at most countable. 
	  **Proof**: for $d=1$ we have either $E=\varnothing$ or $E\subset\mathbb Q+x$, thus is at most countable. For $d\ge2$ we proof the statement by induction. Pick any $x\in E$, then $E\subset\bigcup_{q\in\mathbb Q}\partial B(x,q)$. Since any $\partial B(x,q)$ is $d-1$ dimensional, $E\cap\partial B(x,q)$ is at most countable by induction hypothesis, and as countable union of countable sets is countable, the induction can be proceeded.
    - Set of positive Lebesgue measure is uncountable. [[Measure]]