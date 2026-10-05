
A dense graph can have $E = \mathcal{O}(V^2)$ edges
The semi-streaming model limits memory to $O(V polylog V)$, so i cannot store edges to run that multiple dijkstras algorithms i described in [[Percolation Centrality]] 

There is an useful invariant, when an edge arrives, shortest paths distance can only decrease or not change, never increase. In a [[Turnstile Model]] this invariant wouldn't exist, which is probably why that would make it MUCH harder to design a data strucutre for such a stream.

Connectivity and edge insertion does resemble DSU, so can I perhaps design a variant of it to handle the shortest paths?

But I am looking to track [[Percolation Centrality]], not simple distances, which is likely harder to track.
The percolation relies on the count of shortest paths $\sigma_{s,r}$ , so I need a way to update such a thing when an edge is inserted

There are at least 3 cases when im inserting an edge $u \to v$  with cost $c$
1. $c < d(u,v)$ , which invalidates all shortest paths from $u$ to $v$ and makes $\sigma_{u,v}=1$ (the $\sigma_{u,v}(w)$ for all nodes $w$ in the previous shortest paths from $u$ to $v$ would become 0)
2. $c = d(u,v)$ , adds one more shortcut between $u$ and $v$, so $\sigma_{u,v} += 1$
3. $c > d(u,v)$, nothing changes, no new shortest path is created

But the problem is that I dont even have memory to store the distances $d$,  which is $\mathcal{O}(V^2)$, much less for the $\sigma$ table, which can take up to $\mathcal{O}(V^3)$ space.

Writing this down will help me design a deterministic algorithm that receives an input and has update time $O(V)$ I guess, one that uses $O(V^3)$ memory and updates every distance on the fly.
For that checker, I will probably have to propagate new distances using the dijkstra DAG, and partially run it again from $v$. Or perhaps go simple and brute force the recaltulation of the metrics in $O(VE\log V)$ and thats it

Now I need to go research for more data structures that can help me with those shortest paths counts.
TODO: i found out about the existence of Dynamic Spanners that can approximate the shortest paths
I think i will also need some sampling techniques compute those proportions of $\sigma$, for that, read [[ApproximationAlgorithmsInGraphsViaSampleComplexity-Alane.pdf]].