A **probability space** is a [[Measure]] space $(\Omega, \Sigma, P)$ with $P(\Omega)=1$. 
- **Discussion**: the utilization of measure theory allows us to construct a mathematically rigorous framework for classical probability theory. Of course there are sacrifices, as discussed in [[Philosophy of Probability & Statistics]]. 
- **Conditional probability**: for $A, B \in \Sigma,P(B) > 0$, the conditional probability of $A$ given $B$ is: $$P(A|B) = \frac{P(A \cap B)}{P(B)}$$More about this can be found in [[Conditional Probability]].
## Independence
we progressively define independence for objects of different level:
- **Sets**: for $A,B\in\Sigma$ we denote $A\perp B$ if $P(A\cap B)=P(A)P(B)$. This essentially says that occurrence of $A$ gives no information about $B$, since $P(B|A)=\frac{P(A\cap B)}{P(A)}=P(B)$ in this case. If otherwise $$P(AB)>P(A)P(B)\quad\iff\quad P(B|A)=\frac{P(A\cap B)}{P(A)}>P(B)$$then we know that $A,B$ shows a tendency of co-occur. For $<$ similarly $A,B$ appears to repel each other.
- **Sub-$\sigma$-algebras**: $\sigma_1\perp\sigma_2$ if $A\perp B,\forall A\in\sigma_1,B\in\sigma_2$. Following above, it's essentially saying that the measure on $\sigma_1\otimes\sigma_2$ coincides with the product $P|_{\sigma_1}\times P|_{\sigma_2}$, i.e., anything $A\in\sigma_1$ leaks no information about any $B\in\sigma_2$.
## Other properties
- **Continuity of Probability**
	- **Continuity from below**: If $A_n \uparrow A$ (i.e., $A_n \subseteq A_{n+1}$ and $\bigcup A_n = A$), then $\lim_{n \to \infty} P(A_n) = P(A)$.
	- **Continuity from above**: If $A_n \downarrow A$ (i.e., $A_n \supseteq A_{n+1}$ and $\bigcap A_n = A$), then $\lim_{n \to \infty} P(A_n) = P(A)$.
    - **Discussion:** This is a direct consequence of $\sigma$-additivity and is the primary tool for evaluating limits of event sequences.
- **Dynkin's theorem** If $\mathcal{P} \subseteq \mathcal{L}$ and $\mathcal{P}$ is a $\pi$-system, then $\sigma(\mathcal{P}) \subseteq \mathcal{L}$. See [[Set]]
	- **Application:** To prove a property holds for all $A \in \Sigma$, show it holds for a $\pi$-system that generates $\Sigma$ and that the set of "well-behaved" events is a $\lambda$-system.
### Borel-Cantelli Lemmas
Used to determine the probability of events occurring "infinitely often" ($\limsup A_n$).
1. **First BC Lemma:** If $\sum P(A_n) < \infty$, then $P(A_n \text{ i.o.}) = 0$. (Applies to any sequence).    
2. **Second BC Lemma:** If $\sum P(A_n) = \infty$ **and** $\{A_n\}$ are independent, then $P(A_n \text{ i.o.}) = 1$.
## 4. Illustrative Examples of Insights
To illustrate how these tools operate in practice, consider the problem of **characterizing the equality of two measures**.
### Example A: The $\pi$-system Approach (Uniqueness)
Suppose we want to prove that two probability measures $P$ and $Q$ are identical on the Borel $\sigma$-algebra $\mathcal{B}(\mathbb{R})$.
- **Insight:** We do not need to check every Borel set. We only need to check the $\pi$-system of semi-infinite intervals $\mathcal{I} = \{(-\infty, x] : x \in \mathbb{R}\}$.
- **Execution:** Because $\mathcal{I}$ is closed under intersection ($(-\infty, a] \cap (-\infty, b] = (-\infty, \min(a,b)]$) and generates $\mathcal{B}(\mathbb{R})$, if $P((-\infty, x]) = Q((-\infty, x])$ for all $x$ (i.e., they have the same CDF), then $P = Q$ on the entire $\sigma$-algebra.
### Example B: Kolmogorov’s 0-1 Law (Asymptotic Behavior)
Consider a sequence of independent random variables $X_1, X_2, \dots$. Let $A$ be an event in the **tail $\sigma$-algebra** $\mathcal{T} = \bigcap_{n=1}^\infty \sigma(X_n, X_{n+1}, \dots)$ (e.g., the event that $\sum X_n$ converges).
- **Insight:** For independent sequences, "terminal" properties are deterministic.
- **Execution:** Using the insight that the tail $\sigma$-algebra is independent of itself, we prove $P(A) = P(A \cap A) = P(A)P(A)$, which implies $P(A) \in \{0, 1\}$. This serves as a "classification tool" that tells us a limit either almost surely exists or almost surely does not, without needing to calculate the specific value. 