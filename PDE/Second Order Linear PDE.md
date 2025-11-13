Consider the second order linear PDEs with constant coefficients: $$\sum_{i,j}a_{ij}u_{x_ix_j}+\sum_{i}b_iu_{x_i}+cu=f\quad\text{where}\quad a_{ij}=a_{ji},\quad\forall i\neq j$$Using similar reasoning as in [[Quadratic Form]] we can classify these equations into three categories:
1. **Elliptic PDE**: the eigenvalues are all positive or all negative.
2. **Parabolic PDE**: the eigenvalues are all positive or all negative, except one that is zero.
3. **Hyperbolic PDE**: there is only one negative eigenvalue and all the rest are positive, or there is only one positive eigenvalue and all the rest are negative.
	- **Ultra-hyperbolic PDE**: there is more than one positive eigenvalue and more than one negative eigenvalue, and there are no zero eigenvalues
The detailed transformation process goes as follows: denote $A=(a_{ij})$, then by [[Matrix]] there exists $P\in\gl_n(\mathbb R)$ s.t. $P^TAP=\Lambda$, hence by setting $y=Px$ and utilize [[Differential Calculus on Euclidean Space]] we get $$\frac{\partial}{\partial x}=\frac{\partial}{\partial y}\frac{\partial y}{\partial x}=P\frac{\partial}{\partial y}\quad\Longrightarrow\quad\begin{pmatrix}\dfrac{\partial}{\partial x}\end{pmatrix}^TA\begin{pmatrix}\dfrac{\partial}{\partial x}\end{pmatrix}=\begin{pmatrix}P\dfrac{\partial}{\partial y}\end{pmatrix}^TA\begin{pmatrix}P\dfrac{\partial}{\partial y}\end{pmatrix}=\begin{pmatrix}\dfrac{\partial}{\partial y}\end{pmatrix}^T(P^TAP)\begin{pmatrix}\dfrac{\partial}{\partial y}\end{pmatrix}$$which is diagonalized.
- **Well-posed problem**: a problem is said to be well-posed if it satisfies 
  1. **Existence of solution**: the problem has a solution.
  2. **Uniqueness of solution**: the solution to the problem is unique.
  3. **Continuity of solution**: the solution's behavior changes continuously with the initial condition.
