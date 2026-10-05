
Percolation Centrality is defined in [[PercolationCentrality.pdf]]

Centrality is a way to measure the "importance" of a node in a network. Percolation Centrality differs from other centrality measuresbecause it considers a dynamic "state" of nodes.

The percolation centrality of a node $v$ in a network is $PC(v)$. It is the proportion of [[Percolated paths]] that go through $v$.

It is defined as
$$
PC^t(v) = \frac{1}{N-2}\sum_{s \ne v \ne r}\frac{\sigma_{s,r}(v)}{\sigma_{s,r}}\frac{x_s^t}{[\sum x_i^t] - x_v^t}
$$
from Piraveenan definition, but this paper is considering dynamic states, therefore it uses the $^t$ to denote a time. Im working with dynamic networks not dynamic states, so i rewrite it like this

$$
PC(v) = \frac{1}{n-2}\sum_{s \ne v \ne r}\frac{\sigma_{s,r}(v)}{\sigma_{s,r}}\frac{x_s}{\sum_{w\ne v} x_w}
$$
Definitions used above

$\sigma_{s,r}$   is the total number of shortest paths from $s$ to $r$.
$\sigma_{s,r}(v)$   is the amount of such paths that fo through $v$.
$x_v$ is the percolation state of the $v$, it is a value in the interval $[0,1]$ that representas the node's "activation", kindof like contamination
$\frac{1}{n-2}$ is there to normalize $PC(v)$ in the interval $[0,1]$

(Im not using $t$ for destination node to allow us to use it for input time in the data stream model, when we get there)

Betweeness assumes the $x_v$ was a constant common to every vertex, percolation doesn't.

So, in a way, percolation centrality measures how responsible is a node for retransmitting an infection in an epidemiologic network

What if i wanted to build an algorithm to calculate current percolation centrality for all nodes in a network.

I could count the shortest paths $\sigma$ using one dijkstra per node, which is $\mathcal{O}(VE\log V)$ and then running the naive $\mathcal{O}(V^2)$ loop for each vertex to calculate their percolation, which is $\mathcal{O}(VE\log V + V^3)$.

Dijkstra builds a DAG, so perhaps there is an optimization using this DAG to make it faster

The main difference to betweeness centrality is that betweeness does not consider node states, active or inactive nodes, it is defined as

$$
BC(v) = \frac{1}{(n-1)(n-2)}\sum_{s\ne v\ne r}\frac{\sigma_{s,r}(v)}{\sigma_{s,r}}
$$