
My interpretation of [[DataStreamsAlgorithmsAndApplications.pdf#page=12&selection=30,0,30,17&color=red|DataStreamsAlgorithmsAndApplications, p.12]]

Assume the input stream $A$ = $a_1, a_2, ...$ arrives sequentially, models define how are the $a_i$'s trying to describe $A$.

- **Time series model**: like storing absolute values, assumes $i$-th entry is $A_i$

- **Cash Register Model**: essentially a difference array, input receives a pair $(j,I_i)$ and it means to increment $A_{i-1}[j]$ by $I_i$, i.e. $A_i[j] = A_{i-1}[j] + I_i$, and $I_i \geq 0$ 

- **Turnstile Model**: Similar to Cash Register, but allow $I_i$ to be negative, you can interpret is as the classic bus ride problem, where you only receive the amount of people coming into the bus at each point in time (negative values mean a flow of people coming out of the bus) where you can query amount of people currently in the bus at any point in time..
	This model is more general, as it can handle fully dynamic scenarios, with both insertions and deletions, but getting bounds for it might be harder

Order of generality: *Turnstile*  > *Cash Register*  > *Time series*
