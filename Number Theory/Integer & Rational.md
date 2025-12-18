The set ([[Set Theory]]) of **integers** is defined as $$\mathbb Z=\mathbb Z_+\sqcup\set{0}\sqcup\mathbb Z_0$$where the three components are defined in a progressive manner:
1. **Foundation $\mathbb Z_+$**: this set is conventionally constructed via the **Peano axiom** - we assume a set $\mathbb Z_+$ and a successor function $S:\mathbb Z_+\to\mathbb Z_+$ s.t.:
	1. **Non-emptiness**: there exists an element $1\in\mathbb Z_+$.
	2. **Injectivity**: $S$ is injective.
	3. **Starting point**: $1\notin\im S$.
	4. **Induction**: any $A\subset\mathbb Z_+$ containing $1$ and closed under $S$ is $\mathbb Z_+$ itself. 
   In this way we construct a set $\mathbb Z_+$ with $|\mathbb Z_+|=\infty$.
2. **Arithmetic structure $(\mathbb Z_+\cup\set{0},+,\times)$**: we define the addition and multiplications to satisfy all the ordinary arithmetic properties we expect it to have. 
3. **Extension $(\mathbb Z,+,\times)$**: we define $\mathbb Z$ as the smallest [[Ring]] extension (up to isomorphism) of $\mathbb Z_+$. From this we define the set of negative integers $\mathbb Z_-$.
Conventionally we'll denote $\mathbb N=\mathbb Z\cup\set{0}$. More related concepts and notations can be found in [[Group Gallery]].
- **Equivalence class definition**: formally, $\mathbb{Z}$ is the set of equivalence classes ([[Set Theory]]) of ordered pairs $(a, b) \in \mathbb{Z}_+ \times \mathbb{Z}_+$ under the relation $(a, b) \sim (c, d) \iff a+d = b+c$. Intuitively, the class $[(a, b)]$ represents the integer $a-b$.
- **Algebraic structure**
	- **[[Integral Domain]]**: $\mathbb Z$ is an integral by assumptions of its arithmetic properties
	- **Characteristic:** $\mathbb{Z}$ is the initial object in the category of rings. For any ring $R$ with identity, there exists a unique ring homomorphism $\phi: \mathbb{Z} \to R$.
- **Ordering:** $\mathbb{Z}$ is a discrete totally ordered ring ([[Order]]). 
## Rationals $\mathbb Q$
The field of **rational numbers** is defined as the field of fraction ([[Integral Domain]]) $$\mathbb Q=\Frac\mathbb Z$$Any element in $\mathbb Q$ can be written as $\frac{a}{b},a,b\in\mathbb Z$.
- **Prime field**: $\mathbb{Q}$ is the smallest field of characteristic $0$. Any field of characteristic $0$ contains a subfield isomorphic to $\mathbb{Q}$, as discussed in [[Field]].
- **Countability:** $|\mathbb{Q}| = |\mathbb{Z}| = \aleph_0$, as discussed in [[Cardinality]].
### Ostrowski's theorem
**Ostrowski's theorem**: every non-trivial absolute value ([[Field]]) on $\mathbb{Q}$ is equivalent to either the usual real absolute value $|\cdot|_\infty$ or a [[p-adic Field]] absolute value $|\cdot|_p$ for some $p\in\mathbb P$.
**Proof**: if there exists $n \in \mathbb{Z}_+$ such that $|n| > 1$, one shows that for all $n > 1$, $|n| > 1$. By considering the base-$n$ expansion of large integers, one proves that $|n| = n^\lambda$ for some $0 < \lambda \leq 1$. This corresponds to the standard absolute value (or a power of it). If for all $n \in \mathbb{Z}_+$, $|n| \leq 1$, since the absolute value is non-trivial, there must be a smallest $n > 1$ such that $|n| < 1$. One proves this $n$ must be a prime $p$. It then follows that if $q$ is another prime, $|q| = 1$. Thus, the absolute value is determined by the power of $p$ dividing the numerator and denominator, which is the $p$-adic valuation.