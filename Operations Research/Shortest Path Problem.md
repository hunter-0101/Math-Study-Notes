The **shortest path problem** can be defined for [[Graph]] whether undirected, directed, or mixed. In general, given a graph $G=(E,V,\phi)$ with a real-valued weight function $f:E\to\mathbb R$ the shortest path from $v$ to $v'$ is the path ([[Graph]]) $P^*=(v_1,\cdots,v_n)$ with $v_1=v,v_ n=v'$ that satisfies $$P^*=\underset{P}{\arg\min}\ \sum_{i=1}^{n-1}f(e_{i,i+1})$$The above problem is usually called the **single-pair shortest path problem**, to distinguish it from the following variations:
- **Single-source shortest path problem**: we have to find shortest paths from a source vertex  $v$ to all other vertices in the graph.
- **Single-destination shortest path problem**: we have to find shortest paths from all vertices in the directed graph to a single destination vertex $v$. This can be reduced to the single-source shortest path problem by reversing the arcs in the directed graph.
- **All-pairs shortest path problem**: we have to find shortest paths between every pair of vertices $v, v'$ in the graph.
## Dijkstra's algorithm

## Floyd-Warshall algorithm
The pseudocode is for this algorithm is $$\begin{array}{l}\hline\text{Floyd-Warshall Algorithm}\\\hline
\text{let } dist \text{ be a } |V| \times |V| \text{ array of minimum distances initialized to } \infty \text{ (infinity)} \\
\text{for each edge } (u, v) \text{ do} \\
\quad dist[u][v] = w(u, v)  \quad \text{// The weight of the edge } (u, v) \\
\text{for each vertex } v \text{ do} \\
\quad dist[v][v] = 0 \\
\text{for } k \text{ from 1 to } |V| \\
\quad \text{for } i \text{ from 1 to } |V| \\
\quad \quad \text{for } j \text{ from 1 to } |V| \\
\quad \quad \quad \text{if } dist[i][j] > dist[i][k] + dist[k][j] \\
\quad \quad \quad \quad dist[i][j] = dist[i][k] + dist[k][j] \\
\quad \quad \quad \text{end if} \\
\hline\end{array}$$This algorithm is guaranteed to find all shortest paths and will terminate with $\Theta(|V|^3)$.