A **differential ring** is a commutative [[Ring]] $R$ equipped with a **derivation** $\partial:R\to R$ satisfying:
1. **Linearity over $\mathbb Z$**: $\partial(a+b)=\partial(a)+\partial(b),\forall a,b\in R$.
2. **Leibniz rule**: $\partial(ab)=\partial(a)b+a\partial(b),\forall a,b\in R$.
A **differential field** is a [[Field]] equipped with a derivation. A differential ring $S\supset R$ is a **differential extension** of $R$ if $\partial_S|_R=\partial_R$. Usually a derivation would be denoted $\partial a=a'$.
- **Ring of differential polynomial**: given $y_i$, define the ring of differential polynomials as $$R\dbrace{y_1,\cdots,y_n}=R[y_1,y_1',y_1'',\cdots,y_2,y_2',y_2'',\cdots,y_n,y_n',y_n'',\cdots]$$Further given a differential ring $S$ over $R$, take $u_1,\cdots,u_n\in S$ and let $\phi:y_i^{(i)}\to u_i^{(j)}$ be an $R$-linear **differential homomorphism** from $R\dbrace{y_1,\cdots,y_n}$ to $S$, i.e., $$\phi(v')=(\phi(v))',\quad\forall v\in R\dbrace{y_1,\cdots,y_n}$$which formalizes the notion of evaluation of differential polynomial at $u_i$.
	- **Order**: we say $P\in R\dbrace{y}$ has order $n$ if $n$ is the smallest integer s.t. $P\in R[y,y',\cdots,y^{(n)}]$.
- **Constant**: $c\in R$ is called a constant if $c'=0$.
	- **Ring structure**: obviously the collection constants forms a ring in a differential ring, and a field in a differential field.
- **Arithmetics of derivations**: several familiar rules can be derived easily from definitions:
	- **Identity**: by $\partial(1)=2\partial(1)$ we have $\partial(1)=0$.
	- **Inverse**: since $\partial(1)=\partial(a)a^{-1}+a\partial(a^{-1})$ we deduce that $\partial(a^{-1})=-\partial(a)a^{-2}$.
	- **Quotient**: from above we know that $\partial(a/b)=\frac{\partial(a)b-a\partial(b)}{b^2}$.