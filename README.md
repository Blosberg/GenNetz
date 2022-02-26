# GenNetz

Final project for the Building AI course

## Summary

The human genome comprises roughly 30,000 genes representing an immensely complex, dynamic, and self-regulating system. 

Mapping the network of dependencies in this network is a massive ongoing challenge. For example, gene A may produce a protein that increases the expression of gene B, which, in turn, produces a protein the represses gene C _and_ gene A, and so on. Some of these dependencies are well-established and known, while many more involve indirect influences, cascading networks, and complicated logic (e.g. gene X1 can repress gene Y, but only in combination with gene Z, however X2 can substitute for X1, etc. etc.) --this is a combinatorial explosion of influences that lends itself naturally to an AI-based network.

## Background

A popular approach is to treat nodes in a recurrent neural network as representing genes rather than neurons --their connecting weights represent their influence (either via promotion or inhibition). Validation can be done via knock-out experiments, lineage tracing, and looking at stable fixed-points of known cell types.  

Generally, however, the networks that I have seen of this type employ a single-dimensional approach. That is, they have an array of values for, say, RNA transcription --the model weight for A->B then reflects the influence from the transcription of A onto the trancription of B. 

Other datasets, however, come in the form of Epigenetics, for example:
  * Methylation (BSseq)
  * Transcription Factor binding (ChIPseq)
  * Dynamic TAD boundaries containing Enhancers with corresponding binding motifs,
    etc.

Ultimately the goal is to infer weights connecting genes, but with an explainable mechanism that accounts for the intermediate effects of, e.g., epigenetic changes, chromatin structure. 
I haven't seen a model yet that incorporates this kind of multi-dimensional gene modelling. RNNs would then capture the influence of transcription factor prodcution, methylation, epigenetic changes, and various time-lagged effects of transcription and RNA degradation for each gene.

Admittedly, I haven't yet done an exhaustive literature review on this yet, and am merely suggesting a potential project of curiosity (My current work deals with processing genomics data with much more conventional approaches), but if anyone out there is interested in this type of work, perhaps I'll come back to this and update this later if time allows.


## Previous Work.
* [Zhao et al(2019)](https://shinlab.uconn.edu/wp-content/uploads/sites/2045/2020/01/bibmManuscript2019.pdf)
* [Mandal (2017) ](https://pubmed.ncbi.nlm.nih.gov/28659000/)
