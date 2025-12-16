Decision Analysis is a systematic approach to identifying the best course of action among a set of alternatives, where the consequences of each action are uncertain. It's a normative and descriptive discipline concerned with how decisions should be made (normative) and how they are actually made (descriptive) in complex situations involving **multiple alternatives** and **uncertain outcomes**.
A standard representation of a decision analysis problem in table is like: 
```sheet
| :---: | :---: | :---: | :---: | :---: | :---: |
|$R(a,x)$|<|$S$|<|<|<|
|^|^|$x_1$|$x_2$|$\cdots$|$x_n$|
|^|^|$p(x_1)$|$p(x_2)$|$\cdots$|$p(x_n)$|
|$A$|$a_1$|$r_{11}$|$r_{12}$|$\cdots$|$r_{1n}$|
|^|$a_2$|$r_{21}$|$r_{22}$|$\cdots$|$r_{2n}$|
|^|$\vdots$|$\vdots$|$\vdots$||$\vdots$|
|^|$a_m$|$r_{m1}$|$r_{m2}$|$\cdots$|$r_{mn}$|
```
## Risk management and decision
Consider the cases in which **probabilities** of the different states of nature are **known or estimable**. This is often referred to as decision-making under **risk**. Let $P(\theta_j)$ be the probability of state $\theta_j$.
- **Maximum Likelihood Method**: identify the column with $$p(x_j^*)=\max_{1\le j\le n}p(x_j)$$and pick the $a_i$ with largest $r_{ij}$ among that column.
- **Expected Value Method**: replace outcomes with their expected values, and make the decision. 
- **Decision Tree Analysis**: a **Decision Tree** is a graphical representation of the decision process.4 It is particularly useful for sequential decisions.
	- **Structure:**
	    - **Decision Node (Square $\square$):** Represents a point where a decision must be made.
	    - **Chance Node (Circle $\bigcirc$):** Represents a point where an uncertain event occurs.    
	    - **Branches:** Represent alternatives (from $\square$) or possible states of nature (from $\bigcirc$).
	- **Procedure (Folding Back/Rollback):**
    1. Start from the end of the tree.
    2. For a **Chance Node**, calculate the EMV: $E[V] = \sum P(\theta_j) V_j$.
    3. For a **Decision Node**, choose the branch with the maximum EMV: 10$V_{\text{max}} = \max_i \{E[V_i]\}$.
    4. Repeat until the first decision node is reached. The path selected represents the optimal sequence of actions.
## Decision making under uncertainty
Consider the cases in which the **probabilities** of the different states of nature are **unknown** or cannot be reliably estimated. This is decision-making under **uncertainty**. Let $V_{ij}$ be the payoff matrix, where $i$ is the action and $j$ is the state of nature.
- **Optimistic Criterion (Maximax)**: assumes the best possible state of nature will occur. Focuses on maximizing the maximum possible payoff.
	- **Criterion:** Maximize the maximum payoff for each action.
	- Optimal Action: $$A^* = \arg \max_i \left\{ \max_j \{V_{ij}\} \right\}$$
- **Pessimistic Criterion (Maximin)**: assumes the worst possible state of nature will occur. Focuses on maximizing the minimum possible payoff (a cautious approach).
	- **Criterion:** Maximize the minimum payoff for each action.
	- **Optimal Action**: $$A^* = \arg \max_i \left\{ \min_j \{V_{ij}\} \right\}$$
- **Criterion of Realism (Hurwicz)**: a compromise between optimism and pessimism, using a coefficient of realism 12$\alpha$, where 13$0 \le \alpha \le 1$.14 $\alpha=1$ is optimistic, $\alpha=0$ is pessimistic.
	- Criterion Value for action $A_i$ ($H_i$): $$H_i = \alpha \left( \max_j \{V_{ij}\} \right) + (1 - \alpha) \left( \min_j \{V_{ij}\} \right)$$Optimal Action: $$A^* = \arg \max_i \{H_i\}$$
- **Regret Criterion (Minimax Regret)**: minimizes the maximum **regret** (opportunity loss) that might be incurred.
	1. Construct the Regret Matrix ($R_{ij}$): Regret is the difference between the best possible payoff for a given state $\theta_j$ and the payoff of choosing action $A_i$ for that state. $$R_{ij} = \max_k \{V_{kj}\} - V_{ij}$$    
	2. Determine the Maximum Regret for each action $A_i$ ($R_i^{\text{max}}$): $$R_i^{\text{max}} = \max_j \{R_{ij}\}$$
	3. Optimal Action (Minimize the Maximum Regret): $$A^* = \arg \min_i \{R_i^{\text{max}}\}$$
- **Criterion of Insufficient Reason (Laplace)**: assumes that since the probabilities are unknown, all states of nature are equally likely. It is essentially an Expected Value method with uniform probabilities.
	- **Uniform Probability:** $P(\theta_j) = 1/N$, where $N$ is the number of states.
	- Optimal Action (Maximize the average payoff): $$A^* = \arg \max_i \left\{ \frac{1}{N} \sum_j V_{ij} \right\}$$