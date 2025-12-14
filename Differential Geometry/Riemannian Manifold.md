A **Riemannian manifold** $(M,g)$ is a [[Smooth Manifold]] $M$ equipped with a **Riemannian metric** $g$ that is a **positive definition bilinear form** ([[Quadratic Form]]) $$g_p:T_pM\times T_pM\to\mathbb R$$on each tangent space $T_pM$ that is **smooth**, in the sense that for any $X,Y\in\mathfrak X(M)$ ([[Differential Calculus on Smooth Manifold]]) the function defined by $$g(X,Y):M\to\mathbb R,\quad p\mapsto g_p(X_p,Y_p)$$is a smooth function on $M$. Intuitively it serves as a smooth assignment of an inner product ([[Inner Product Space]]) on the tangent spaces.
- **Local coordinates representation**: given a chart $(U, x^1, \dots, x^m)$, the metric $g$ at $p \in U$ is represented by the [[Matrix]] of its components, $g_{ij}(p)$, written as $$g_{ij}(p) = g_p\left(\left.\frac{\partial}{\partial x^i}\right|_p, \left.\frac{\partial}{\partial x^j}\right|_p\right)$$By definition, the matrix $(g_{ij}(p))$ is symmetric and positive-definite. The value of the metric on two tangent vectors is given by $$g_p(X_p, Y_p) = g_{ij}(p) X^i Y^j\where X_p = X^i \left.\frac{\partial}{\partial x^i}\right|_p,Y_p = Y^j \left.\frac{\partial}{\partial x^j}\right|_p$$The requirement that $g(X, Y)$ is smooth is equivalent to requiring that all component functions $g_{ij}: U \to \mathbb R$ are smooth functions.
- **Existence of Riemannian metric**: every smooth manifold $M$ admits a Riemannian metric.
  **Proof**: consider $\set{(U_\alpha,\varphi_\alpha)}_{\alpha\in A}$ a locally finite atlas, and $\set{\tau_\alpha}_{\alpha\in A}$ a differentiable partition of unity subordinate to the given atlas ([[Smooth Manifold]]). Define $g$ by $$g=\sum_{\alpha\in A}\tau_\alpha\cdot\tilde g_\alpha\where\tilde g_\alpha=\varphi_\alpha^*g^\text{can}$$Here $g^\text{can}$ is the Euclidean metric ([[Euclidean Space]]) on $\mathbb R^n$. Since $\supp\tau_\alpha\subset U_\alpha$ we have $\tau_\alpha\tilde g_\alpha$ defined and smooth on $M$, and vanishes outside $M$. Since the atlas is locally finite, the sum is well-defined at every point. It's straightforward to check that $g$ is a Riemannian metric. 
- **Volume form**: on an $m$-dimensional Riemannian manifold $(M, g)$, the metric naturally induces a canonical volume $m$-form $\mu_g$ given by $$\mu_g = \sqrt{\det(g_{ij})} \, dx^1 \wedge \dots \wedge dx^m$$The volume of a measurable $A \subset M$ is then defined by the integral: $$\text{Vol}(A) = \int_A \mu_g$$as defined in [[Integral Calculus on Smooth Manifold]]. 
- **[[Metric Space]] structure**: given a Riemannian manifold $(M,g)$ we can define $$d_g(p,q)=\inf\Set{L(\gamma):\gamma\text{ regular with }\gamma(0)=p,\gamma(1)=q}$$where $L(\gamma)$ is the length ([[Curve]]), then $(M,d_g)$ is a metric space whose induced [[Metric Topology]] coincides with the topology on $M$. 
## Geodesic
A smooth [[Curve]] $\gamma: I \to M$ is a **geodesic** if $$\nabla_{\gamma'(t)}\gamma'(t) = 0,\quad\forall t\in I$$Intuitively, it's say that its acceleration is a multiple of the normal vector, which means the curve is "straightest" in the manifold.
- **Geodesic equation**: in a local coordinate chart $(U, x^1, \dots, x^m)$, where $\gamma(t) = (x^1(t), \dots, x^m(t))$, the vanishing covariant derivative leads to the geodesic equation: $$\frac{d^2 x^k}{d t^2} + \Gamma^k_{ij} \frac{d x^i}{d t} \frac{d x^j}{d t} = 0, \quad \text{for } k=1, \dots, m$$Here, $\frac{d x^i}{d t}$ are the components of the tangent vector $\dot{\gamma}(t)$, and $\Gamma^k_{ij}$ are the **Christoffel symbols of the second kind** (or **connection coefficients**) for the metric $g$, defined by: $$\Gamma^k_{ij} = \frac{1}{2} g^{k l} \left( \frac{\partial g_{l i}}{\partial x^j} + \frac{\partial g_{l j}}{\partial x^i} - \frac{\partial g_{i j}}{\partial x^l} \right)$$where $g^{kl}$ are the components of the inverse matrix of $[g_{ij}]$.
The geodesic curve $\gamma$ between two points is a critical point of the **Energy Functional** (or **Action Functional**):

$$E(\gamma) = \frac{1}{2} \int_a^b g(\dot{\gamma}(t), \dot{\gamma}(t)) \, dt$$

The Euler-Lagrange equations for this functional, viewed in local coordinates where the Lagrangian is $\mathcal L(x, \dot{x}) = \frac{1}{2} g_{ij} \dot{x}^i \dot{x}^j$, are:

$$\frac{d}{d t} \left( \frac{\partial \mathcal L}{\partial \dot{x}^k} \right) - \frac{\partial \mathcal L}{\partial x^k} = 0$$

1. Term 1:
    
    $$\frac{\partial \mathcal L}{\partial \dot{x}^k} = \frac{1}{2} g_{ij} (\delta_k^i \dot{x}^j + \dot{x}^i \delta_k^j) = \frac{1}{2} (g_{kj} \dot{x}^j + g_{ik} \dot{x}^i) = g_{ki} \dot{x}^i$$
    
    $$\frac{d}{d t} \left( \frac{\partial \mathcal L}{\partial \dot{x}^k} \right) = \frac{d}{d t} (g_{ki} \dot{x}^i) = \frac{\partial g_{ki}}{\partial x^j} \dot{x}^j \dot{x}^i + g_{ki} \ddot{x}^i$$
    
2. Term 2:
    
    $$\frac{\partial \mathcal L}{\partial x^k} = \frac{1}{2} \frac{\partial g_{ij}}{\partial x^k} \dot{x}^i \dot{x}^j$$
    
3. Substituting into E-L:
    
    $$g_{ki} \ddot{x}^i + \frac{\partial g_{ki}}{\partial x^j} \dot{x}^j \dot{x}^i - \frac{1}{2} \frac{\partial g_{ij}}{\partial x^k} \dot{x}^i \dot{x}^j = 0$$
    
4. Multiplying by $g^{lk}$ (the inverse metric):
    
    $$g^{lk} g_{ki} \ddot{x}^i + g^{lk} \left( \frac{\partial g_{ki}}{\partial x^j} - \frac{1}{2} \frac{\partial g_{ij}}{\partial x^k} \right) \dot{x}^i \dot{x}^j = 0$$
    
    Using $g^{lk} g_{ki} = \delta^l_i$, and replacing the dummy index $i$ with $l$:
    
    $$\ddot{x}^l + g^{lk} \left( \frac{\partial g_{ki}}{\partial x^j} - \frac{1}{2} \frac{\partial g_{ij}}{\partial x^k} \right) \dot{x}^i \dot{x}^j = 0$$
    
    This is equivalent to the standard form of the geodesic equation after applying the symmetric properties of the connection.
### Practical Results and Tools
- **Existence and Uniqueness (Tool)**: Given a point $p \in M$ and a tangent vector $v \in T_pM$, there exists a unique maximal geodesic $\gamma_v: I_v \to M$ such that $\gamma_v(0) = p$ and $\dot{\gamma}_v(0) = v$. This result follows from the **Picard-Lindelöf theorem** (existence and uniqueness for ODEs), as the geodesic equation is a second-order ODE system.
- **Completeness**: A Riemannian manifold $(M, g)$ is **geodesically complete** if every maximal geodesic is defined for all $t \in \mathbb R$.
	- **Hopf-Rinow theorem**: for a Riemannian manifold $(M, g)$, the following statements are equivalent:
		1. $(M, g)$ is geodesically complete.
		2. $(M, d_g)$ is a complete metric space (where $d_g$ is the distance induced by $g$).
		3. Every pair of points in $M$ can be joined by a length-minimizing geodesic (i.e., $(M, g)$ is **geodesically connected**).
- **Normal Coordinates**: A practical coordinate system $(\mathcal U, x^1, \dots, x^m)$ can be defined in a neighborhood of $p \in M$ such that geodesics through $p$ appear as **straight lines** emanating from the origin in $\mathbb R^m$. In these **normal coordinates**, the Christoffel symbols **vanish at $p$**: $\Gamma^k_{ij}(p) = 0$.