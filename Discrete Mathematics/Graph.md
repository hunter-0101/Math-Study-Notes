A **graph** refers to a ordered tuple $(V,E,\phi)$ consisting of:
- **Vertices**: a set $V$ of vertices (nodes, points).
- **Edges**: a set $E$ of edges (links, lines).
- **Incidence function**: a function $\phi:E\to\set{\set{x,y}:x,y\in V}$ that maps every edge on an unordered pair of vertices.
The above definition more specifically yields an **undirected multigraph**. When $\set{x,y}$ is replaced by $(x,y)$ the resulting collection is referred to as a **directed multigraph**.
- **Degree**: the degree of a vertex is the number of edges that are incident to it, denoted $\deg v$. A loop is counted twice. For directed graph is this further refined into indegree/outdegree.
- **Clique**: graph **clique** $C\subset V$ is a subset of the set of vertices s.t. $$(i,j)\in E,\quad\forall i,j\in C$$that is, inherits a fully connected subgraph. The **clique number** $C(G)$ is the cardinality of the largest clique.