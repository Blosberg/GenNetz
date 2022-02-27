# GenNetz

Building AI course project

## Summary

The human genome comprises roughly 30,000 genes representing an immensely complex, dynamic, and self-regulating system. 

Mapping the network of dependencies in this network is a massive ongoing challenge. For example, gene A may produce a protein that increases the expression of gene B, which, in turn, produces a protein the represses gene C _and_ gene A, and so on. Some of these dependencies are well-established and known, while many more involve indirect influences, cascading networks, and complicated logic (e.g. gene X1 can repress gene Y, but only in combination with gene Z, however X2 can substitute for X1, etc. etc.) --the combinatorial explosion of influences presents challenges to scientists and experimentalists, but lends itself naturally to an AI-based network.

## Background

A popular approach is to treat nodes in a recurrent neural network as representing genes rather than neurons --their connecting weights represent their influence (either via promotion or inhibition), in addition to cues from the environment and neighbouring cells. Validation can be done via knock-out experiments, lineage tracing, and looking at stable fixed-points of known cell types. 
While many genes --often referred to as "housekeeping genes"-- are insensitive to the state of the system (and are consistently expressed with low variance independent of cell state), there is enormous medical and biological interest in determining which genes provide critical regulation in steering cell behaviour \-- that is to say, which nodes in such a network have the greatest weights and what the geometry of such a graph of connections looks like. If we know that, then we know what genes to target for therapy for various illnesses.

Generally, however, the networks that I have seen of this type employ a single-dimensional approach. That is, they have an array of values for, say, RNA transcription \--hence, the model weight for A->B reflects the _direct_ influence from the transcription of A onto the trancription of B. 

In reality, however, there are intermediates between these effects that can also be measured from epigenetics analysis, for example:
  * Cytosine methylation
  * Acetylation and tri-methylation of histone tails
  * Transcription Factor binding
  * Dynamic TAD boundaries containing Enhancers with corresponding binding motifs,
  ... among others.

An illustrative sketch is provided by [Jaenisch and Bird (2003)](https://www.nature.com/articles/ng1089z)

<img src="https://media.springernature.com/full/springer-static/image/art%3A10.1038%2Fng1089/MediaObjects/41588_2003_Article_BFng1089z_Fig1_HTML.gif" width="500">

Ultimately the goal is to infer weights connecting genes to flesh out the network between genes, but with an explainable mechanism that accounts for the intermediate effects of, e.g., epigenetic changes and chromatin structure. 
I haven't seen a model yet that incorporates this kind of multi-dimensional gene modelling. RNNs would then capture the influence of transcription factor prodcution, methylation, epigenetic changes, and various time-lagged effects of transcription and RNA degradation for each gene.

It would be interesting to incorporate these sorts of additional features into an RNN and if anyone out there is interested in this type of work, perhaps I'll come back to this and update with more detail (I have limited time to put into this at the moment, but it is something I'm curious about).


## Previous Work.
See also:
* [Zhao et al (2019)](https://shinlab.uconn.edu/wp-content/uploads/sites/2045/2020/01/bibmManuscript2019.pdf)
* [Mandal et al (2017) ](https://www.worldscientific.com/doi/10.1142/S0219720017500160?url_ver=Z39.88-2003&rfr_id=ori:rid:crossref.org&rfr_dat=cr_pub%20%200pubmed)
