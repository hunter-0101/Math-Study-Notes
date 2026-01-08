Given nonempty [[Set]] $X,Y$, a **binary relation** $R$ from $X$ to $Y$ is a subset of the Cartesian product $$R \subseteq X \times Y$$If $(x, y) \in R$, we often write $xRy$. If $X = Y$, we say $R$ is a relation on $X$.
- **Domain & range**: the active elements of the relation are defined as $$\begin{align}\text{dom}(R) &= \set{x \in X : \exists y \in Y, (x, y) \in R}\\\text{ran}(R)& = \set{y \in Y : \exists x \in X, (x, y) \in R}\end{align}$$Note that range is sometimes called image. 
- **Inverse relation**: every relation $R$ has an inverse $R^{-1} \subseteq Y \times X$ defined by $$R^{-1} = \set{(y, x) \in Y \times X : (x, y) \in R}$$    
- **Composition**: given $R \subseteq X \times Y,S \subseteq Y \times Z$, the composition $S \circ R \subseteq X \times Z$ is defined as $$S \circ R = \{(x, z) \in X \times Z : \exists y \in Y \text{ s.t. } (x, y) \in R \land (y, z) \in S\}$$In finite contexts, relations can be viewed as Boolean matrices. The composition $S \circ R$ corresponds to the Boolean matrix product, providing an algorithmic path-finding tool for connectivity problems.
## Specific types of relation
### Logical Classification
Based on notations from [[Logic]], a relation $R$ on $X$ is:
- **Reflexive**: $\forall x \in X, xRx$.
- **Irreflexive**: $\forall x \in X, \neg(xRx)$.
- **Symmetric**: $\forall x, y \in X, xRy \implies yRx$.
- **Antisymmetric**: $\forall x, y \in X, (xRy \land yRx) \implies x = y$.
- **Asymmetric**: $\forall x, y \in X, xRy \implies \neg(yRx)$. 
	- Note: Asymmetric $\implies$ Antisymmetric + Irreflexive
- **Transitive**: $\forall x, y, z \in X, (xRy \land yRz) \implies xRz$.
- **Connected**: $\forall x, y \in X, x \neq y \implies (xRy \lor yRx)$.
- **Strongly Connected**: $\forall x, y \in X, (xRy \lor yRx)$.
### Uniqueness and Totality
These properties determine if a relation behaves like a function:
- **Left-unique (injective)**: $(x_1Ry \land x_2Ry) \implies x_1 = x_2$.
- **Right-unique (functional)**: $(xRy_1 \land xRy_2) \implies y_1 = y_2$.
- **Left-total (serial)**: $\forall x \in X, \exists y \in Y, xRy$.
- **Right-total (surjective)**: $\forall y \in Y, \exists x \in X, xRy$.
### Equivalence Relation
A relation $\sim$ is an **equivalence relation** if it is reflexive, symmetric, and transitive.
- **Quotient Set**: An equivalence relation induces a partition of $X$ into equivalence classes: $$X/\sim=\set{[x]}\where[x] = \set{y \in X : x \sim y}$$This is widely used in different fields of math. 
- **Fundamental theorem of equivalence relations**: there is a natural bijection between the set of all equivalence relations on $X$ and the set of all partitions of $X$.
## Function
A function $f: X \to Y$ is a relation $R_f \subseteq X \times Y$ that is right-unique and left-total: $$R_f = \set{(x, f(x)) \in X \times Y : \forall x \in X, \exists! y \in Y, (x, y) \in R_f}$$Here $R_f$ is also called the **graph** of $f$, also denoted $\Gamma_f$. 
- **Injectivity & surjectivity**: a function is **injective** if $$f:X\into Y\qiffq(Y x_1\neq x_2\implies f(x_1)\neq f(x_2))$$and is **surjective** if $$f:X\surto Y\qiffq \forall y\in Y\ \exists x\in X\ \st f(x)=y$$A function that is both injective and surjective is said to be **bijective**. The corresponding nouns are injection, surjection, and bijection. 
- **Image & preimage**: given $A\subset X,B\subset Y$ we define the image & preimage as $$f(A)=\set{f(x)\in Y:x\in A},\quad f^{-1}(B)=\set{x\in X:f(x)\in B}$$Note that the preimage operator $f^{-1}$ is well-defined, even if $f$ is not invertible, and should not be confused with the inverse function. 
- **Interaction with set operation**: for $f:X\to Y$ we have $$\begin{align}f(A\cup B)&=f(A)\cup f(B)\\ f(A\cap B)&\subset f(A)\cap f(B)\\f(A^c)&\supseteq\left(f(A)\right)^c\\ f(A\setminus B)&\supseteq f(A)\setminus f(B)\end{align}$$The preimage $f^{-1}$ is "better behaved" as it preserves all Boolean operations: $$\begin{align}f^{-1}(A\cup B)&=f^{-1}(A)\cup f^{-1}(B)\\f^{-1}(A\cap B)&= f^{-1}(A)\cap f^{-1}(B)\\  f^{-1}(A^c)&=\left(f^{-1}(A)\right)^c\\f^{-1}(A\setminus B)&=f^{-1}(A)\setminus f^{-1}(B)\end{align}$$The preimage is the primary tool in topology and measure theory because it preserves the algebraic structure of sets (unions, intersections, complements) without requiring the function to be a bijection.