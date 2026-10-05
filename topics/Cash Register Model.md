
Assume the input stream $A$ = $a_1, a_2, ...$ arrives sequentially, models define how are the $a_i$'s trying to describe $A$.

Cah register model essentially uses a difference array, input receives a pair $(j,I_i)$ and it means to increment $A_{i-1}[j]$ by $I_i$, i.e. $A_i[j] = A_{i-1}[j] + I_i$, and $I_i \geq 0$ 

In a graph streaming context, a cash register model can mean there are only edge insertions not deletions, deletions are only allowed in [[Turnstile Model]]
