For a function $f:X\to Y$ (in the sense of [[Set Theory]]) from [[Topological Space]] $(X,\mathcal T_X)$ to $(Y,\mathcal T_Y)$, we say that it's continuous if $$f^{-1}(A)\in\mathcal T_X,\quad\forall A\in\mathcal T_Y$$The set of continuous functions from $X$ to $Y$ is denoted $C(X,Y)$, and if $Y$ is well-understood we usually abbreviate it as $C(X)$. Note that making either  $\mathcal T_X$ coarser (deleting nearness relation in domain) or $\mathcal T_Y$ finer (adding nearness relation in image) may destroy continuity.
- **Intuition**: in [[Function on Euclidean Space]] we've defined the notion of continuity via preservation of limit, and since limit itself formalizes the concept of arbitrary closeness ([[Series]]), it makes sense (via intuition of [[Topological Space]]) that we're generalizing this concept via preservation of openness. 
- **Equivalent definition**: there are several equivalent definitions available, which are useful in different cases: 
	- **Preimage of closed sets**: $f\in C(X,Y)$ iff $f^{-1}(A)$ is closed given $A\subset Y$ closed. This follows directly from the original definition by taking a complement. 
	- **Image of closure**: we have the equivalence $$f\in C(X,Y)\quad\iff\quad \left(A\subset X\Longrightarrow f(\overline{A})\subset\overline{f(A)}\right)$$
	- **Pointwise continuity**: $f\in C(X,Y)$ if it's continuous at every $x\in X$, defined as $$\forall f(x)\in U\in\mathcal T_Y\quad \exists x\in V\in\mathcal T_X\quad\st\quad f(U)\subset V$$The equivalence is trivial. 
- **Initial & final topology**: when a family of functions is given, we can induce a topology that makes the continuous. 
	- **Initial topology**: for set $X$ and a family of topological spaces $(Y_\alpha,\mathcal T_\alpha)_{\alpha\in I}$ with functions $$f_\alpha:X\to Y_\alpha,\quad\forall \alpha\in I$$the **initial topology** on $X$ induced by $f_\alpha$ is the **coarsest** topology $\mathcal T_X$ making all of $f_\alpha$ continuous. 
	- **Final topology**: for set $Y$ and a family of topological spaces $(X_\alpha,\mathcal T_\alpha)_{\alpha\in I}$ with functions $$f_\alpha:X_\alpha\to Y,\quad\forall\alpha\in I$$the **final topology** on $Y$ induced by $f_\alpha$ is the **finest** topology $\mathcal T_Y$ making all of $f_\alpha$ continuous. 
## Structure of $C(X,Y)$
The set of continuous functions $C(X,Y)$ between $(X,\mathcal T_X),(Y,\mathcal T_Y)$ bears some special structures that makes it useful in many cases.
- **Pasting lemma**: Let $X=A\cup B$ be the union of two closed sets (or open sets) $A$ and $B$. If $f:A\to Y$ and $g:B\to Y$ are continuous, and if $f|_{A\cap B} = g|_{A\cap B}$, then the function $h:X\to Y$ defined by $h(x) = f(x)$ for $x\in A$ and $h(x)=g(x)$ for $x\in B$ is continuous.
- **Vector-valued function**: $f:A\to X\times Y$ given by $f(a)=(f_1(a),f_2(a))$ is continuous iff the **coordinate functions** $f_1,f_2$ are continuous.
- **Limit of continuous function may not be continuous**: take, for instance, $$f_n(x)=|x|^{1/n},x\in[0,1]\quad\Longrightarrow\quad \lim_{n\to\infty}f_n(x)=\sgn(x)$$which is not continuous. The intuition is that, the preimage of $(-\delta,\delta)$ for some $0<\delta<1$, while being open for $f_n$, keeps shirking, hence $f^{-1}((-\delta,\delta))$, being a countable intersection of open sets, fail to be open itself. 
## Structure of $C(X,\mathbb R)$
Below we simply denote $C(X)=C(X,\mathbb R)$. Most results discussed below actually applies to [[Ring]] with and [[Order]] structure that is compatible with the ring operations. 
- **Ring structure**: $(C(X),+,\times)$ is a ring. 
- **Pedagogical behavior under different operations**: the notion of continuity behaves quite badly under different operations. For instance: 
	- **Monotonic limit**: the example above with a restriction on domain, $f_n(x)=|x|^{1/n},x\in[0,1]$ shows that monotonic limit of continuous functions may not be continuous. 
	- **Infimum & supremum**: countable infimum can be written as monotonic limit, not to mention the even more uncontrollable uncountable infimum. Similar argument applies to supremum. 

## Other note
- **Homeomorphism**: if both the function $f$ and $f^{-1}$ are continuous, then $f$ is called a homeomorphism. (corresponds to isomorphism in [[Group]])
	- **Counterexample**: a continuous bijection may not be homeomorphism, say, for $f:[0,1)\to\set{x^2+y^2=1}$ given by $f(t)=(\cos 2\pi t,\sin 2\pi t)$ the inverse $f^{-1}$ is not continuous.
	- **Topological property**: homeomorphism gives a bijective correspondence not only between $X,Y$ but also between $\mathcal T_X,\mathcal T_Y$. Any property of $X$ that is entirely expressed in terms of the topology of $X$ yields, via the correspondence $f$, the corresponding property of $Y$. Such property of $X$ is called a topological property.
	- **Topological imbedding**: an injective $f$ that is bijective on the restricted image, then it is a topological imbedding.