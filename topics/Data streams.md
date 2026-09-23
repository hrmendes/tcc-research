Input arrives very rapidly and there is limited memory to store the input

Some methods for dealing with this type of restrictions are [[Metric embeddings]], [[Pseudo-random computations,]] [[Sparse aproximation theory]] and [[Communication complexity]].

Some citations from [[Data Streams Algorithms And Applications]].

> [!PDF|yellow] [[DataStreamsAlgorithmsAndApplications.pdf#page=11&selection=23,0,24,54&color=yellow|DataStreamsAlgorithmsAndApplications, p.11]]
> > With traditional data feeds, one modifies the underlying data to reflect the updates, and real time queries are fairly simple such as looking up a value. 

Motivation
> [!PDF|yellow] [[DataStreamsAlgorithmsAndApplications.pdf#page=12&selection=6,89,7,86&color=yellow|DataStreamsAlgorithmsAndApplications, p.12]]
> > Given a certain amount of resources, a data stream rate and a particular analysis task, what can we (not) do?


Most approaches involve approximations

We call the input stream  $A$ = $a_1, a_2, ...$ , and it arrives sequentially, [[Data Stream Models]] define how are the $a_i$'s trying to describe $A$.


Performance metrics:
- **Proc. Time** - Processing time per item $a_i$ in the stream
- **Storage** - Space to store data structure on $A_t$ at time $t# 


> [!PDF|yellow] [[DataStreamsAlgorithmsAndApplications.pdf#page=14&selection=10,0,27,1&color=yellow|DataStreamsAlgorithmsAndApplications, p.14]]
> At any time t in the data stream, we would like the per-item processing time, storage as well as the computing time to be simultaneously o(N, t), preferably, polylog(N, t)

weaker model
> [!PDF|yellow] [[DataStreamsAlgorithmsAndApplications.pdf#page=14&selection=57,0,74,40&color=yellow|DataStreamsAlgorithmsAndApplications, p.14]]
> > At any time t in the data stream, per-item processing time and storage need to be simultaneously o(N, t) (preferably, polylog(N, t)), but the computing time may be larger.

This "weaker" model is especially useful when update rate is super higher than query (computing) rate.

Nice quote:
> ([[DataStreamsAlgorithmsAndApplications.pdf#page=14&selection=155,22,157,47&color=yellow|DataStreamsAlgorithmsAndApplications, p.14]])
> However, over the course of our life, we manage to abstract and store only part of the observations, and function adequately even if we can not recall every detail of each instant of our lives. We are biological data stream processing machines.


Some potential scenarios besides IP traffic analysis
- Multiple satellites gathering multiple terrestrial, atmospheric and ocean-surface observetions f the entire earth;
- Stream of financial transactions of multiple types from multiple sources;
- Continuous physical observations from a network of sensors;
- Distributed server processing stream of text files sent between users, what may we want to extract from here? (information retrieval problems)

The math and algorithmic foundations are distilled int [[Data Streams Foundations]]