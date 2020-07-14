# Hierarchical Human Parsing with Typed Part-Relation Reasoning

## Summary
This work aims at modeling human structure using graph neural network(GNN) for better human parsing.
## Research Objective
Exploiting the representation capacity of deep neural networks to model human hierarchical structure and then perform human parsing.
## Background and Problems
- Human bodies present a highly structured hierarchy and body parts inherently interact with each other.
- Thus the central problem in human parsing is how to model such relations between parts.
- Efforts encoding pose information just weakly utilize the structural information.
- Modeling relations by only a single type is over-general and simple.
- Immediate feed-forward prediction is sub-optimal.
## Methods
- Representing the human semantic structure as a directed, hierarchical graph(three levels). Accordingly, the gt maps are also organized in a hierarchical manner.
- Node embedding(for node embedding$h_v$).
- Part relation modeling(for edge embedding$h_{u,v}$).
	- Decompositional/Compositional/Dependency relation
	- A general formulation: $h_{u,v} = R^r(F^r(h_u), h_v)$
	- Relation network$R^r$: concatenation and convolution
	- Feature adaption$F^r$ is specific for edge type.
	- Decompositional: $F(h_u) = h_u \odot att_{u,v}(h_u)$.  $att_{u,v}$ is specific for each sub-node of $u$, but is depended on all sub-nodes(soft-max).
	- Compositional: $F(h_u) = h_u \odot att_v([h_u])$. $att_v([h_u])$ is consistent for each sub-node of $v$, and is implemented by concatenation and convolution.
	- Dependency: $F(h_u) = F^{cont}(h_u) \odot att_{u,v}(F^{cont}(h_u))$. $att_{u,v}(F^{cont}(h_u))$ is specific for each sibling of $u$, but is computed on all siblings(soft-max). $F^{cont}$ collects context from original image feature in a non-local manner.
- Iterative inference.
	- Message function. Aggregating information from all edges which is directed to a node to form a message. 
	- Node update function. Updating state of the node by fusing message and node embedding in last iteration through a convGRU module.
- Readout. Obtaining predictions of each layer by applying convolution and soft-max.
## Evaluation
- LIP/PASCAL-Person-Part/ATR/PPSS/Fashion Clothing dataset
## Conclusion
- Structure modeling is essential.
- Exploring different kinds of relations is meaningful.
## Notes
- The hierarchy of human body is predefined and supervision is imposed on every layer, which is no flexible while processing other objects.
- [Code](https://github.com/hlzhu09/Hierarchical-Human-Parsing)
- CVPR 2020
## References
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTM2MTQxNDQ1Nyw1MjkxMjk3NDQsLTEzND
YzNjA3MTAsLTIxMjU0MTE2NTRdfQ==
-->