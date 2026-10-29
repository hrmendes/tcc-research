
Here I am designing an algorithm that uses  [[Sparse Spanners]] to compute [[Percolation Centrality]] when the graph edges are being inserted with a stream input ([[Data streams]]), in the [[Cash Register Model]]. The idea is that for each new edge that comes in, we only save it if it improves the distance by a stretch factor of $k$.

For semi-streaming purposes, we want to achieve an $O(V\text{ polylog } V)$ memory usage.

Recalling the Theorem 1 from [[Sparse Spanners]], we have that

For any integer $k \ge 1$, every graph $G$ with $n$ vertices possesses a $(2k - 1)$-spanner containing at most $O(n^{1 + \frac{1}{k}}) \text{ edges}$


If we had $k$ being a constant, memory would exceed the  $O(V\text{ polylog } V)$ limit, which made me think what would happen if we picked $k = \log V$, which we can do because the amount of nodes of the graph is previously known.

Then we would have $O(V^{1 + \frac{1}{\log V}})$ , we must answer if $V^{\frac{1}{\log V}}$ is $O(\text{polylog }V)$ .

Let $x = V^{\frac{1}{\log_b V}}$.
$$
\log_b(x) = \log_b\left(V^{\frac{1}{\log_b V}}\right)
\\\\
\log_b(x) = \left(\frac{1}{\log_b V}\right) \cdot \log_b V = 1
\\\\
\log_b(x) = 1
\\\\
x = b
$$
So $x$ is a constant, and therefore we have $V^{\frac{1}{\log V}}$ = $O(1)$ , so, in the end, the spanner that uses $k = \log V$ will use $O(V^{1 + \frac{1}{\log V}}) = O(V)$ memory.
