This note elaborates on the math and algorithms used in [[data streams]] models. The more technical stuff is going on here.

# Math

## Sampling

Every input is seen , but only a subset of items are retained.
We generally want this subset to be of *polylogarithmic*  size.

Some sampling algorithms are known for:
- Finding quantiles on a [[Cash Register]] data stream
- Finding frequent items in a [[Cash Register]] data stream (is it [[heavy hitters]]?)
- Estimating the [[inverse distribution]] in a [[Cash Register]] data stream (wtf is an inverse distribution?)
- Finding rangesums of items in a [[Cash Register]] data stream

### Quantile Sampling

Let $S$ be a sorted set of items, a $\phi$ quantile ($0 < \phi < 1$) are items with rank $k\phi|S|$ for $k = 0\ldots1/\phi$ 

The intuition is that we want to get "quantile points" of the stream every $100\phi$% of the data, e.g. if $\phi = 0.25$, then we would get a sample every $25$% of the data. So we are dividing $|S|$ into partitions of size $\phi|S|$ and choosing the first element of every partition to represent it.

Lets define an approximation version of this problem:

(remember that $||A||_1 = \sum_iA[i]$)
DEFINITION
$(\phi,\varepsilon)-Quantiles$

TODO: continue from here, end of page 19 of Data Streams Algorithms and Applications


