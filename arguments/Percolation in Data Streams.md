I aim here to connect the [[Percolation Centrality]] metric with [[Data streams]], finding out a way to compute $PC(v)$ for all nodes in a network using only $\mathcal{O}(V polylog V)$ memory.
First notice we cannot store all edges in a dense graph, where it is $O(V^2)$ edges

For this thesis scope, I will consider the network nodes have fixed [[Percolation State]]s, that is $x_v$ is a constant $\forall v \in V(G)$

For starters, we will aim only at the [[Cash Register Model]], where there are only edge insertions, working in it here [[Percolation Centrality and Data Streams - Cash Register]]

In the future, we can consider diving into the [[Turnstile Model]], allowing for edge deletions

The work with a fixed network and dynamic percolation states is also interesting