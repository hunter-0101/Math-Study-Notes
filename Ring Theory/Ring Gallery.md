## Construction of $\mathbb R$ from $\mathbb Q$
Ways to construct $\mathbb R$ from $\mathbb Q$ includes Dedekind cuts ([[Real Number System]]), taking completion of $\mathbb Q$ w.r.t its Euclidean metric, etc. Here we use a ring-theoretic approach of construction real number as a factor ring of the ring of Cauchy sequences of rational numbers modulo its ideal of null sequence.
- **Cauchy sequence**: Consider $T=\prod_{i=1}^\infty\mathbb Q$. A element $\alpha=(a_1,\cdots)\in T$ is a Cauchy sequence if for every $n\in\mathbb N$ there exists $m\in\mathbb N$ such that for all $i,j\in\mathbb N_{>m}$, we have $|a_i-a_j|<1/n$. Let $\mathcal C$ contain all Cauchy sequences in $T$, then $\mathcal C$ is a subring.
- **Null sequence**: a sequence with limit $0$ is called null sequence. Denote $\mathcal N$ the set of null sequences, then $\mathcal N$ is an ideal of $\mathcal C$.
- Let $\mathcal R=\mathcal C/\mathcal N$. then $\mathcal R$, as a field, is an candidate for $\mathbb R$. It can be shown that it has all the basic properties that characterize $\mathbb R$.
## Quaternion
**Complex number**: We can construct the complex number $\mathbb{C}$ using $\mathbb{R}$ as below: consider $$\mathcal{C}=\Set{\begin{pmatrix}a&b\\-b&a\end{pmatrix}|a,b\in\mathbb{R}}\subset M_2(\mathbb{R})$$then $\mathcal{C}$ is a subring and a field. Let $$\mathcal{R}=\Set{\begin{pmatrix}r&0\\0&r\end{pmatrix}|r\in\mathbb{R}},\quad\mathbf{i}=\begin{pmatrix}0&1\\-1&0\end{pmatrix}$$then we can identify $\mathcal{R}\cong\mathbb{R},\mathcal{C}\cong\mathbb{C}$.
**Quaternion**: similarly, let $$\mathbb{H}=\Set{\begin{pmatrix}\alpha&\beta\\-\overline\beta&\overline\alpha\end{pmatrix}|\alpha,\beta\in\mathbb{C}}\subset M_2(\mathbb{C})$$and define the four elements$$\mathbf{1}=\begin{pmatrix}1&0\\0&1\end{pmatrix},\quad\mathbf{i}=\begin{pmatrix}i&0\\0&-i\end{pmatrix},\quad\mathbf{j}=\begin{pmatrix}0&1\\-1&0\end{pmatrix},\quad\mathbf{k}=\begin{pmatrix}0&i\\i&0\end{pmatrix}$$then we establish the quaternion ring.
- By the definition or the matrix representation, we can show that $Z(\mathbb H)=\mathbb R$.
- **Involution**: define the map $\sigma(r\mathbf 1+s\mathbf i+t\mathbf j+u\mathbf k)=r\mathbf1-s\mathbf i-t\mathbf j-u\mathbf k$, then it's called the convolution. It can be shown that $h\sigma(h)=\det(h)\mathbf 1$, and $\sigma\circ\sigma=id_{\mathbb H}$.
- **Pure part**: let $P=\set{s\mathbf i+t\mathbf j+u\mathbf k|s,t,u\in\mathbb R}$, then it's called the pure part of $\mathbb H$. If we identity $P$ with 3-dimensional column vector space $R^3$ by the correspondence of entries, then for $p,q\in P$ we have $$pq=-(p\cdot q)\mathbf1+p\times q$$For $h\in\mathbb H$, if we define $\gamma_h:l\mapsto hlh^{-1}$, then it can be shown that the action of $\gamma_h$ on $P$ is actually rotation.
## Matrix ring
Denote $F$-algebra a ring $A$ with a multiplicative identity such that $A$ is an $F$-vector space and is linear on $F$. Define the tensor product $\otimes$ for an extension field $K$ of $F$ as$$M_n(F)\otimes_F K\cong M_n(K)$$
- **Automorphism preserves determinant and characteristic polynomial**: 
- **Automorphisms of matrix group**: for an arbitrary field $K$, we will show that $Aut(M_n(K))$ consists only the inner automorphisms.
  **Proof**: Denote $E_{ij}$ the matrix whose entries equals $1$ at $(i,j)$ and $0$ otherwise.
  1. Any automorphism $\phi$ on $M_n(K)$ preserves determinant and characteristic polynomial, thus the image of the projector of rank $1$ is still a projector of rank $1$.
  2. From above we know that $\phi(E_{11})=vv_1^T$ with $v_1^Tv=1$. For $2\le j\le n$ define $v_j=\phi(E_{j1})v$. Notice that $\phi(E_{ij})v_m=\delta_{jm}v_i$ for $1\le i,j,m\le n$ where $\delta$ is the Kronecker delta.
  3. By considering $\phi(E_{1j})v_j$ we know that $v_1=v$ and $v_j\neq0$ for any $j$.
  4. Now $\{v_1,\cdots,v_n\}$ forms a basis for $K^n$. Let $P=(v_1,\cdots,v_n)$, then $\phi(E_{ij})P=PE_{ij}$.
  5. Finally we know that $\phi(X)=PXP^{-1}$, which is inner.