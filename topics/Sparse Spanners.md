
**Reference:** [[SparseSpanners.pdf]]

  

## 1. Definition: $t$-Spanner

Given a weighted graph $G = (V,E)$, a subgraph $G' = (V,E')$ is a **$t$-spanner** of $G$ if for every pair of vertices $u, v \in V$, the shortest path distance in $G'$ satisfies:
  $$d_{G'}(u,v) \le t \cdot d_G(u,v)$$

The parameter $t \ge 1$ is called the **stretch factor**.
  

## 2. The Size-Stretch Trade-off (Theorem 1)
**Reference**: [[SparseSpanners.pdf#page=3&selection=129,0,131,1&color=yellow|Theorem 1]]


For any integer $k \ge 1$, every graph $G$ with $n$ vertices possesses a $(2k - 1)$-spanner containing at most: 

$$O(n^{1 + \frac{1}{k}}) \text{ edges}$$

