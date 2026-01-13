**Discussion**: the field of PDE is largely **phenomenon-driven** (top-down). A PDE is a constraint on the "local shape" of a field. The classification into **Elliptic**, **Parabolic**, and **Hyperbolic** types is not just a quadratic form analogy; it defines the "Domain of Dependency."
- **Elliptic (Equilibrium):** e.g., [[Laplace's Equation]] $\Delta u = 0$. Information propagates everywhere instantly. There is no "time."
- **Parabolic (Diffusion):** e.g., [[Heat Equation]] $u_t - \Delta u = 0$. Information propagates forward in time with infinite speed (smoothing).
- **Hyperbolic (Causality):** e.g., [[Wave Equation]] $u_{tt} - \Delta u = 0$. Information propagates at a finite speed (preserving discontinuities).
We need different tools because these equations have fundamentally different "regularity" behaviors. For instance, in heat equation even if we start with a jagged initial temperature the final solution will still be smooth, hence we use the Fourier transform; in wave equation a "kink" created somewhere will propagates without being smoothed out, which necessitates the method of characteristics. 

- **Equation-centric vs. method-centric**: some textbooks of PDE choose to organize its contents in methods to solve PDEs (e.g., Walter A. Strauss) while other choose to organize by classification of equation (e.g., Evans). This is due to the intersection nature of PDE - you *can* solve a wave equation even if you don't know what a Sobolev space is. This decoupling allows authors to choose:
	- **Inductive order**: solve specific cases -> notice patterns -> generalize to theory (weak solution).
	- **Deductive order**: define distributions/Sobolev space -> treat specific PDEs as operators on those spaces. 
  Regardless of the order, the central goal is always to prove **Hadamard's well-posedness**, as discussed below. 

---
Consider a $k$-th order PDE for a function $u: \Omega \subseteq \mathbb{R}^n \to \mathbb{R}$ given by $$F(x, u, Du, D^2u, \dots, D^k u) = 0$$Let $S \subset \Omega$ be a smooth [[Hypersurface]] with a unit normal vector field $\nu(x)$. The **Cauchy problem** consists of finding a solution $u$ that satisfies PDE in $\Omega$ and attains prescribed **Cauchy data** on $S$: $$\frac{\partial^j u}{\partial \nu^j} \Big|_S = \phi_j, \quad j = 0, 1, \dots, k-1$$where $\phi_j$ are given functions on $S$ ([[Function on Euclidean Space]]). 
- **Classification by domain**: there are two major classifications of Cauchy problem:
    - **Initial value problem (IVP)**: $S$ represents a time-slice (e.g., $t=0$) in a space-time manifold. Typical for hyperbolic and parabolic equations.
    - **Boundary value problem (BVP)**: $S$ is the boundary $\partial \Omega$ of a spatial domain. Typical for elliptic equations.
  When both initial values and boundary values are provided in a Cauchy problem we'll refer to it as an **initial-boundary-value problem (IBVP)**. 
- **Cauchy-Kowalevski theorem**: if the PDE coefficients, the surface $S$, and the Cauchy data $\phi_j$ are all real analytic ([[Taylor's Theorem]]), and $S$ is non-characteristic at $x_0 \in S$, then there exists a unique analytic solution $u$ in a neighborhood of $x_0$.
- **Hadamard's well-posedness**: a Cauchy problem is well-posed in a functional space $X$ if:
    1. **Existence:** A solution $u \in X$ exists.
    2. **Uniqueness:** The solution is unique in $X$.        
    3. **Stability:** The solution depends continuously on the data $\{\phi_j\}$.
  More about this can be found in [[Inverse Problem]]. 
- **Characteristic condition**: to determine if the Cauchy data can uniquely determine the $k$-th order derivatives at $S$, we examine the principal symbol $\sigma_P(x, \xi)$. We say that $S$ is **non-characteristic** at $x$ if: $$\sigma_P(x, \nu(x)) \neq 0$$If $\sigma_P(x, \nu(x)) = 0$, the Cauchy problem may have no solution or infinitely many solutions.
### Classification of conditions
The nature of the constraints imposed on $S$ dictates the qualitative behavior of the solution and the choice of solution space (e.g., Sobolev spaces $H^s(\Omega)$). $$\begin{array}{l}\text{Dirichlet}& u=f \\\text{Neumann}& \dfrac{\partial u}{\partial n}=f \\\text{Robin}& c_0u+c_1\dfrac{\partial u}{\partial n}=f \\\text{Mixed}& u=f\text{ or }c_0y+c_i\dfrac{\partial u}{\partial n}=g \\\text{Cauchy}& u=f ,\quad\dfrac{\partial u}{\partial u}=g\end{array}$$In general an BVP may have different types of conditions on different boundaries, or even multiple types of conditions on the same different boundary for different intervals.
- **Characteristics of conditions**
	- **Dirichlet (Essential):** Directly constrains the solution in the trace space $H^{1/2}(\partial \Omega)$.
	- **Neumann (Natural):** Constrains the derivative. For elliptic operators, a compatibility condition (e.g., $\int_\Omega f = \int_{\partial \Omega} g$) is often required for existence.
	- **Cauchy Conditions & Ellipticity:** While Cauchy data is natural for the Wave Equation ($u_{tt} - \Delta u = 0$), it leads to **ill-posedness** for the Laplace Equation ($\Delta u = 0$).
## Insights and Practical Tools
#### Insight I: The Necessity of Non-Characteristic Surfaces
The Cauchy-Kowalevski theorem fails if the initial surface "flows" along the information propagation paths of the PDE. For a $k$-th order linear operator $L$, the data $\phi_j$ must be transverse to the characteristic directions to allow for the computation of the $k$-th transversal derivative.
Example 1: The Wave Equation (Hyperbolic)
Consider $u_{tt} - u_{xx} = 0$.
- **Angle A (Non-characteristic):** Data on $t=0$. $\sigma_P = \xi_t^2 - \xi_x^2$. For $S=\{t=0\}$, $\nu = (1, 0)$, so $\sigma_P(1, 0) = 1 \neq 0$. The IVP is well-posed (D'Alembert's solution).
- **Angle B (Characteristic):** Data on $t=x$. $\nu = (1, -1)/\sqrt{2}$. $\sigma_P(1, -1) = 1^2 - (-1)^2 = 0$. On this "light-cone" surface, the Cauchy data cannot be assigned arbitrarily; it must satisfy the PDE internally, and the solution is not uniquely determined in the neighborhood.
#### Insight II: Instability of Cauchy Data for Elliptic Operators
Cauchy data is "too much" information for elliptic problems, leading to a violation of Hadamard's stability criterion. This serves as a warning tool: never model a steady-state system (elliptic) with both value and flux data on the same boundary segment.
Example 2: Hadamard's Counter-example
Consider the Laplace equation $\Delta u = 0$ in $\mathbb{R} \times (0, \infty)$ with Cauchy data at $y=0$: $$u(x, 0) = 0, \quad \frac{\partial u}{\partial y}(x, 0) = \frac{1}{n} \sin(nx)$$
- **Observation:** As $n \to \infty$, the data $(\phi_0, \phi_1) \to (0, 0)$ uniformly.
- **Solution:** $u_n(x, y) = \frac{1}{n^2} \sin(nx) \sinh(ny)$. 
- **Instability:** For any $y > 0$, $\sinh(ny)$ grows exponentially. Thus, $u_n$ does not converge to $0$, even though the data converges to $0$. A small perturbation in high-frequency data results in an arbitrarily large change in the solution.
#### Actionable Tool: The Trace Theorem
When working with weak solutions in $H^1(\Omega)$, the Dirichlet data $u|_{\partial \Omega}$ is not merely a restriction but an image of the **Trace Operator** $\gamma_0: H^1(\Omega) \to H^{1/2}(\partial \Omega)$.
- **Practical application:** To prove a BVP has a solution, one must first ensure the boundary data $f$ resides in the correct fractional Sobolev space $H^{s-1/2}(\partial \Omega)$ to ensure the existence of a $H^s(\Omega)$ lifting.