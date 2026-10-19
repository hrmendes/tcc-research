Percolation State stands for how "infected" a node is, it represents a value in the interval $[0,1]$, with 0 denoting it is not infected and 1 denoting it is 100% infected.

Recalling the [[Percolation Centrality]] expression:


$$
PC(v) = \frac{1}{n-2}\sum_{s \ne v \ne r}\frac{\sigma_{s,r}(v)}{\sigma_{s,r}}\frac{x_s}{\sum_{w\ne v} x_w}
$$

The percolation state is the $x_v$.