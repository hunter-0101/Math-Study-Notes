A **graph** is an ordered tuple $G=(V,E,\phi)$ consisting of:
- **Vertices**: a set $V$ of vertices (nodes, points).
- **Edges**: a set $E$ of edges (links, lines).
- **Incidence function**: a function $\phi:E\to\set{\set{x,y}:x,y\in V}$ that maps every edge on an unordered pair of vertices.
The above definition more specifically yields an **undirected multigraph**. When $\set{x,y}$ is replaced by $(x,y)$ the resulting collection is referred to as a **directed multigraph**.
- **Degree**: the degree of a vertex is the number of edges incident to it: $$\deg v=\#\set{e\in E:v\in\phi(e)}$$In a directed graph, we further distinguish the **indegree** and **outdegree** as $$\begin{align}&\deg^-(v)=\#\set{e\in E:\phi(e)=(*,v)}\\&\deg^+(v)=\#\set{e\in E:\phi(e)=(v,*)}\end{align}$$It's obvious that we have the equality $\deg(v)=\det^-(v)+\deg^+(v)$.
	- **Neighborhood**: the neighborhood of a vertex in defined as $$N_G(v)=\Set{v'\in V:\phi(e)=\set{v,v'}\text{ for some }e\in E}$$the neighborhood usually do not include $v$ itself, which is called an **open neighborhood**. In contrast, a **closed neighborhood** contains $v$ itself, and is usually denoted $N_G[v]$.
- **Walk**: a walk is a finite or infinite sequence of edges which joints a sequence of vertices, i.e., $$(e_{i})_{i\in I},I\subset\mathbb N\quad\st\quad \phi(e_i)=\set{v_{i},v_{i+1}},\quad\forall i\in I$$A walk is **closed** if $|I|=n<\infty$ and $v_{n+1}=v_1$, and **open** otherwise. A walk do not necessarily admit a first or last vertex, and we'll call such walk a infinite or semi-infinite one.
	- **Trail**: a trail is a walk in which $e_i\neq e_j,\forall i\neq j$, i.e., all edges are distinct.
		- **Circuit**: a circuit is a closed trail.
		- **Cycle**: a cycle (simple circuit) is a circuit in which only the first and last vertices are equal.
	- **Path**: a path is a trail in which $v_i\neq v_j,\forall i\neq j$, i.e., all vertices are distinct.
	- **Loop**: a loop is an edge that connects a vertex to itself, i.e. $\phi(e)=\set{v,v},v\in V$.
  Note that all the above concepts can be directed or undirected. 
- **Distance**: the distance between two nodes is the length of the shortest path joining two nodes.
- **Adjacency matrix**: the adjacency matrix of $G=(V,E,\phi)$ is a (0,1)-matrix defined as $$A_G=(a_{ij})\where a_{ij}=\begin{cases}1,&\text{if }(v_i,v_j)\in\im\phi\\0,&\text{otherwise}\end{cases}$$many of the graph operations are define via the adjacency matrix.
- **Clique**: graph **clique** $C\subset V$ is a subset of the set of vertices s.t. $$(i,j)\in E,\quad\forall i,j\in C$$that is, inherits a fully connected subgraph. The **clique number** $C(G)$ is the cardinality of the largest clique.
## Common types of graphs
- **Simple graph**: a graph is simple if it has no loop and multiple adjacencies, that is, $$\phi(e_i)\neq\phi(e_j),\quad\forall i\neq j$$In many cases, graphs are assumed to be simple unless specified otherwise, and for simple graphs we'll usually neglect $\phi$ and simply write $G=(V,E)$.
- **Regular graph**: a graph is regular if each vertex has the same number of neighbors, i.e. $$\#N_G(v)=k,\quad\forall v\in V\where N\in\mathbb N$$a graph satisfying the above equality is called a $k$-regular graph.
- **Connected graph**: for an undirected graph, it's connected if for any $u,v\in Vu\neq v$ there exists a path connecting $u,v$.
	- **Connected component**: a connected component is a maximal connected subgraph.
	- **Weak connectivity**: for a directed graph, it's weakly connected if its undirected version is connected. 
- **Tree**: a tree an undirected graph that is both connected and acyclic, or a directed graph in which there exists a unique walk from one vertex (the **root** of the tree) to all remaining vertices.
	- **Spanning tree**: a spanning tree $T$ of an undirected $G$ is a subgraph that is a tree with $$T=(V,E',\phi')\subset G$$that is, it contains all the vertices. 
- **Weighted graph**: 
## Graph operation
- **Cut**: a cut is partition of nodes in the following manner: $$C=(S,T)\where V=S\sqcup T$$ the cut-set is the set $$\set{e=\phi(u,v)\in E:u\in S,v\in T}$$If $s,t$ are specific vertices, then an $s$-$t$ cut is a cut in which $s,t$ belongs to $S,T$ respectively.
	- **Minimum cut**: a cut is minimum if the size or weight of the cut is not larger than the size of any other cut.
	- **Maximum cut**: A cut is maximum if the size of the cut is not smaller than the size of any other cut.
- **Transpose**: the transpose of a graph is defined as $$G^T=(V,E^T,\phi^T)\where E^T=\set{(v,u):(u,v)\in E}$$this implies that the adjacent matrix is transposed. 
- **Power**: the **$k$-th power** of $G$ is defined as $$G^k=(V,E^k,\phi^k)\where(u,v)\in\im\phi,\quad\forall d_E(u,v)\le k$$that is, any two nodes whose distance is no bigger than $k$ are adjacent in $G^k$.
- **Dual**: the dual graph of $G$ is defined as $$G^*=(V^*,E^*,\phi^*)$$where $V^*$ corresponds to the faces of $G$, and $E^*$ connects faces sharing an edge in $G$. 