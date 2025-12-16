The **shortest path problem** can be defined for [[Graph]] whether undirected, directed, or mixed. In general, given a graph $G=(E,V,\phi)$ with a real-valued weight function $f:E\to\mathbb R$ the shortest path from $v$ to $v'$ is the path ([[Graph]]) $P^*=(v_1,\cdots,v_n)$ with $v_1=v,v_ n=v'$ that satisfies $$P^*=\underset{P}{\arg\min}\ \sum_{i=1}^{n-1}f(e_{i,i+1})$$The above problem is usually called the **single-pair shortest path problem**, to distinguish it from the following variations:
- **Single-source shortest path problem**: we have to find shortest paths from a source vertex  $v$ to all other vertices in the graph.
- **Single-destination shortest path problem**: we have to find shortest paths from all vertices in the directed graph to a single destination vertex $v$. This can be reduced to the single-source shortest path problem by reversing the arcs in the directed graph.
- **All-pairs shortest path problem**: we have to find shortest paths between every pair of vertices $v, v'$ in the graph.
## Dijkstra's algorithm
The Dijkstra's algorithm finds the shortest path **from a given source node to every other node**. It does so by constructing a minimum spanning [[Tree]], hence it's also used for picking the MST in many application scenarios. The pseudocode is provide below: $$\begin{array}{l}\hline
\text{Dijkstra's Algorithm}\\\hline
\text{create vertex set } Q \text{ as the set of unvisited vertices initiated to }V\\
\text{for each vertex } v \text{ do}\\
\quad dist[v]= \infty \\
\quad prev[v] = \text{undefined} \\
\quad \text{add } v \text{ to } Q \\
dist[source] = 0 \\
\text{while } Q \text{ is not empty do} \\
\quad u = \text{vertex in } Q \text{ with minimum } dist[u] \\
\quad \text{remove } u \text{ from } Q \\
\quad \text{for each neighbor } v \text{ of } u\text{ do} \\
\quad \quad alt = dist[u] + \text{weight}(u, v) \\
\quad \quad \text{if } alt < dist[v]\text{ do} \\
\quad \quad \quad dist[v] = alt \\
\quad \quad \quad prev[v] =u \\
\text{return } dist[], prev[]\\\hline
\end{array}$$Here $dist[]$ is the array recording the distance from $v$ to the source, and $prev[]$ records the previous node in the shortest path to the source.
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