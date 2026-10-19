
Lets assume we have $PC(v)$ precomputed for all the nodes in the current state of the network.
Now we must process an edge insertion, a new directed edge from $u$ to $v$ with weight $w$.

Lets assume for a moment that we have a way to know the current distance from $u$ to $v$ (before inserting the new edge), and call it $dist(u,v)$. There are 3 cases to work with.
- 1. $dist(u,v) < w$ : in this case no shortest path will ever pass through $w$, so there is no use saving this edge at all
- 2. $dist(u,v) > w$ : in this case all shortest paths that used the path $u \ldots v$ inside it will be rerouted to use the edge that is now being inserted, recomputing $PC$ would require finding out these shortest paths and updating every vertex in them.
- 3. $dist(u,v) = w$ : this is the case where there is an increase in the amount of shortest paths, as it presents a new alternative path from $u$ to $v$ that can be used in many other shortest paths

Something to notice is that $dist$ is monotonically non-increasing, i.e., no distance can increase with any positive weighted edge being inserted


- **IDEA**: perhaps we can find a way to prove that in dense graphs ($E = \mathcal{O}(V^2)$), there cant be many edges lying in some shortest path. I feel like assuming we have that many edges in shortest paths would lead us to some contradictions. Unless we were assuming weights can be 0, so we must ensure edge weights are **STRICTLY POSITIVE** . Idk if this is actually true, but if it is it will be of MAJOR help designing the solution. I will look into it (and also ask Zatesko if he can help me prove or contradict this idea). Perhaps the proof that there are not that many edges can revolve around an attempt at constructing this network that always tries to fall into case 3
