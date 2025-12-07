An **Euclidean vector** over [[Field]] $F$ of dimension $n$ is a tuple $$x=\begin{pmatrix}x_1\\\vdots\\x_n\end{pmatrix}\where x_i\in F,1\le i\le n$$The set of euclidean vectors of dimension $n$ is denoted $F^n$. This can be seen as a specific representation of general elements in a finite dimensional [[Vector Space]] given a (standard) basis.
- **Linear independence**: viewing $\mathbb R^n$ as an $\mathbb R$-[[Vector Space]], then linear independence is defined similarly as in [[Group]]. 
- **Inner product**: for two vectors $x,y\in F^n$ we define their inner product as $$x\cdot y=\braket{x,y}=\sum_{i=1}^nx_iy_i$$this coincides with the tradition in [[Hilbert Space]].
	- **Exterior product**: an example of exterior product in $F^3$ is provided below. This can be generalized under the framework of [[Exterior Algebra]]. 
## The space $\mathbb R^3$
The space $\mathbb R^3$ is of particular interest of study due to its wide applications in and outside math. Below we record some of the basic concepts and properties.
- **Inner (dot) product**: for $x,y\in \mathbb R^3$ we define $$x\cdot y=\sum_{i=1}^3x_iy_i=|x||y|\cos\theta$$where $\theta$ is the angle between $x,y$. Note that axiomatically we define $\theta$ via the formula above, rather than calculating $x\cdot y$ with a known angle.
	- **Projection**: the projection of $x$ onto $y$ is given by $$\text{proj}_y(x)=\frac{x\cdot y}{|y|^2}y$$This follows directly from the definition of inner product.
- **Outer (cross) product**: the outer product of $x,y\in\mathbb R^3$ is defined as $$x\times y=\begin{vmatrix}e_1&e_2&e_3\\x_1&x_2&x_3\\y_1&y_2&y_3\end{vmatrix}$$here $e_i$ is a formal placeholder for the index of coefficient.
	- **Anti-commutative**: $\mathbf{a} \times \mathbf{b} = -(\mathbf{b} \times \mathbf{a})$.
	- **Distributive**: $\mathbf{a} \times (\mathbf{b} + \mathbf{c}) = \mathbf{a} \times \mathbf{b} + \mathbf{a} \times \mathbf{c}$.
	- **Not associative**: $\mathbf{a} \times (\mathbf{b} \times \mathbf{c}) \neq (\mathbf{a} \times \mathbf{b}) \times \mathbf{c}$.
	- **Area of parallelogram**: by [[Determinant]] we have that $|x\times y| = |x| |y|\sin\theta$ is the area of the parallelogram formed by $x,y$.
- **Scaler triple product**: the scaler triple product of $x,y,z\in\mathbb R^3$ is defined as $x\cdot(y\times z)$.
	- **Invariance under circular shift**: this follows directly from the definition of outer product and property of [[Determinant]].
	- **Volume of parallelepiped**: the scaler triple product represents the volume of the parallelepiped formed by $x,y,z$.
- **Vector Triple Product**: The vector triple product of $x,y,z$ is: $$x\times (y\times z)=(x\cdot z)y-(x\cdot y)z$$this is sometimes useful. 
### Application in geometry
The above results are useful in many problems concerning the geometry of $\mathbb R^3$.
- **Area of a Triangle**: For vectors $\mathbf{a}$ and $\mathbf{b}$ representing two sides of a triangle: $$\text{Area} = \frac{1}{2} |\mathbf{a} \times \mathbf{b}|$$
- **Volume of a Parallelepiped**: Given vectors $\mathbf{a}, \mathbf{b}, \mathbf{c}$: $$\text{Volume} = |\mathbf{a} \cdot (\mathbf{b} \times \mathbf{c})|$$
- **Distance Between Two Points**: Given points $\mathbf{P_1} = (x_1, y_1, z_1)$ and $\mathbf{P_2} = (x_2, y_2, z_2)$,  $$d = \sqrt{(x_2 - x_1)^2 + (y_2 - y_1)^2 + (z_2 - z_1)^2}$$
- **Distance Between a Point and a Line**: Given a point $\mathbf{P}$ and a line through points $\mathbf{A}$ and $\mathbf{B}$, the distance $d$ is: $$d = \frac{|(\mathbf{P} - \mathbf{A}) \times (\mathbf{B} - \mathbf{A})|}{|\mathbf{B} - \mathbf{A}|}$$
- **Distance Between a Point and a Plane**: Given a point $\mathbf{P} = (x_1, y_1, z_1)$ and a plane with equation $Ax + By + Cz + D = 0$, the distance is: $$d = \frac{|Ax_1 + By_1 + Cz_1 + D|}{\sqrt{A^2 + B^2 + C^2}}$$
- **Distance Between Two Parallel Planes**: For planes $Ax + By + Cz + D_1 = 0$ and $Ax + By + Cz + D_2 = 0$, the distance between them is:$$d = \frac{|D_1 - D_2|}{\sqrt{A^2 + B^2 + C^2}}$$
- **Distance between two skewed lines**: for two lines denoted $l_1:\mathbf{r_1}+t\mathbf{e_1},l_2:\mathbf{r_2}+t\mathbf{e_2}$, we can find their direction vector $\mathbf{n}=\mathbf{e_1}\times\mathbf{e_2}$, and the distance is $$d=\frac{|\mathbf{n}\cdot(\mathbf{r_1}-\mathbf{r_2})|}{||\mathbf{n}||}$$
- **Condition for Three Points to Be Collinear**: Points $\mathbf{P_1}, \mathbf{P_2}, \mathbf{P_3}$​ are collinear if: $$(\mathbf{P_2} - \mathbf{P_1}) \times (\mathbf{P_3} - \mathbf{P_1}) = 0$$
- **Condition for Four Points to Be Coplanar**: Points $\mathbf{P_1}, \mathbf{P_2}, \mathbf{P_3}, \mathbf{P_4}$ are coplanar if the scalar triple product: $$(\mathbf{P_2} - \mathbf{P_1}) \cdot [(\mathbf{P_3} - \mathbf{P_1}) \times (\mathbf{P_4} - \mathbf{P_1})] = 0$$