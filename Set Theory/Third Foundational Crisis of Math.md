The third foundational crisis of math mainly involves the definition of  a "set", and operations we're allowed to perform involving the object called "set". 
### Naive set theory & the third crisis of mathematics
The third **crisis of foundation of mathematics** was precipitated by the realization that the **axiom of unrestricted comprehension** - the idea that any property $\phi(x)$ defines a set - is logically fatal. In particular, consider the **Russel's paradox**: 

> Let $\phi(x)$ be the property $x \notin x$. In **naive set theory**, we define the set: $$R = \{x \mid x \notin x\}$$The paradox arises when we ask if $R$ is a member of itself: $$(R \in R) \iff (R \notin R)$$This is a pure logical contradiction ($\text{True} \iff \text{False}$).

The paradox revealed that **membership ($\in$) cannot be an arbitrary relation.** It proved that a "set of all sets" or a "set of all non-self-membered entities" is not merely too large, but logically impossible. It destroyed the hope of Gottlob Frege and others that mathematics could be derived purely from a "common sense" logic of collections.
- **Other similar examples**
	- **The barber paradox**: a barber shaves all those, and those only, who do not shave themselves. Does the barber shave himself? If he does, he shouldn't; if he doesn't, he must. This illustrates that the **definition** of a role can be **self-negating**.
	- **Power set of the universe**: consider the "Set of all Sets", $U$. By Cantor's Theorem ([[Cardinality]]), $|\mathcal{P}(U)| > |U|$. However, since $\mathcal{P}(U)$ is a collection of sets, it must be a subset of $U$, implying $|\mathcal{P}(U)| \leq |U|$. This creates a cardinal contradiction, showing that the "Universal Container" is a structural impossibility.
### Axiomatic set theory
Mathematicians, primarily Zermelo and Fraenkel (ZFC), resolved the crisis by replacing **axiom of unrestricted comprehension** with the **axiom schema of specification (separation)**. 
In ZFC, you cannot define a set simply by a property $\phi(x)$. Instead, you must already possess a set $A$ and carve out a subset: $$\set{x \in A : \phi(x)}$$Under this rule, Russell's set $R$ cannot be formed unless you already have a "super-set" $A$ that contains all sets - which ZFC carefully ensures you cannot build. If you try to form $R$ inside a set $A$, you simply get a subset of $A$ that does not contain itself, which is no longer paradoxical. 
- **Sacrifice of the universal**: the "cost" of ZFC is the loss of the **Universal Set**. In ZFC, we must distinguish between **Sets** (objects that can be members of other objects) and **Proper Classes** (collections like "the class of all sets" that are "too big" to be treated as mathematical objects). We trade the intuitive "Set of all things" for a rigid, hierarchical "Cumulative Hierarchy" ($V$).
- **Axiom of specification**: this axiom is a **limitation axiom** - it tells you what you **cannot** do (create a set out of nothing just by describing it). To balance this, ZFC includes **existence** and **construction** axioms that allow us to "bootstrap" the universe from nothing.
- **Example**: we'll take the definition of [[Group]] to explain the underlying mechanism of ZFC. To define a group we invoke the following axioms in order:
	1. **Axiom of emptiness**: formally, $\exists x \forall y (y \notin x)$. This gives us the "ur-element," the empty set $\emptyset$.
	2. **Axiom of infinity**: this asserts the existence of a set containing $\emptyset$ and all its successors. This gives us the set of natural numbers $\mathbb{N}$.
	3. **Axiom of power set**: this allows us to "explode" the size of any set. From $\mathbb{N}$, we get $\mathcal{P}(\mathbb{N})$, which eventually leads to the Reals $\mathbb{R}$.
	4. **Axiom of pairing & union**: these allow us to combine existing sets into new ones (like Cartesian products $G \times G$, which is necessary to define the operation $+$).
  **The Logic:** You don't define $G$ by carving it out of a "universal set." You define $G$ by **constructing** it from $\emptyset$ using a finite number of these existential steps. Once $G$ is constructed, you use the Axiom of Power Set to create the set of all possible relations on $G$, and _then_ you use Specification to pick out the specific relation $+$ that satisfies the group axioms.
## ZFC system
The "overall picture" of ZFC is best visualized as the **Cumulative Hierarchy**, denoted by the class $V$. This is the "map" of the mathematical universe.
### The Global Structure
ZFC views the universe as a series of layers (Stages) indexed by ordinal numbers $\alpha$:
- **$V_0 = \emptyset$** (The void).
- **$V_{\alpha+1} = \mathcal{P}(V_\alpha)$** (The next layer is the power set of the previous).
- **$V_\lambda = \bigcup_{\beta < \lambda} V_\beta$** (For "limit" stages like $\omega$, we take the union of everything before).
The entire universe $V$ is the union of all these stages. Crucially, **$V$ itself is not a set.** It is a **Proper Class**.
### The ZFC "Shield"
The ZFC axioms act as a shield that prevents us from reaching "paradoxical" sizes:
1. **Foundation (Regularity):** Ensures every set belongs to _some_ $V_\alpha$. This forbids sets like $x \in x$, because a set can only contain elements from "earlier" layers. 
2. **Replacement:** This is the most technical axiom. It says that if you have a set $A$ and a function-like formula, the "image" of $A$ is also a set. This allows us to "reach" very high levels of the hierarchy without the universe collapsing. 