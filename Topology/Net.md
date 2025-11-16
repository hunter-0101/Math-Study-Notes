A **directly set** $J$ is a set with partial order $\preceq$ such that for each pair $\alpha,\beta\in J$ there exists $\gamma\in J$ s.t. $\alpha\preceq\gamma,\beta\preceq\gamma$ ([[Order]]). Given topological space $(X,\mathcal T)$, any function $f:J\to X$ is called a **net**. Usually we denote $f(\alpha)$ as $x_\alpha$, and $f$ as $(x_\alpha)_{\alpha\in J}$.
- **Convergence**: $x_\alpha\to x$ if for each neighborhood $U$ of $x$ there exists $\alpha\in J$ s.t. $\alpha\preceq\beta\Rightarrow x_\beta\in U$.
	- If $x_\alpha\to x,y_\alpha\to y$, then $(x_\alpha,y_\alpha)\to(x,y)$ due to property of product topology. [[Point Set Topology]]
	- If $X$ is Hausdorff, then a net converges to at most one point. [[Separation Axioms]]
- **Limit point**: let $A\subset X$, then $x\in\overline A$ iff there is a net of points of $A$ converging to $x$.
- **Criterion of continuity**: $f:X\to Y$ is continuous iff $x_\alpha\to x\Rightarrow f(x_\alpha)\to f(x)$.
## Subnet
Given net $f:J\to X$, if $K$ is a directed set and $g:K\to J$ satisfies:
1. $i\preceq j\Rightarrow g(i)\preceq g(j)$.
2. $g(K)$ is co-final in $J$, i.e. for any $\alpha\in J$ there exists $\beta\in g(K)$ s.t. $\alpha\preceq\beta$.
Then $f\circ g:K\to X$ is called a **subnet** of $(x_\alpha)$.
- **Accumulation point**: $x$ is point of accumulation if for any neighborhood $U$ of $x$, the index set for which $x_\alpha\in U$ is co-final in $J$.
	- The net $(x_\alpha)$ has a point of accumulation $x$ iff some subnet of $(x_\alpha)$ converges to $x$.
- $X$ is compact iff every net has a convergent subnet.