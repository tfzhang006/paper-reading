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
	- 
## Evaluation

## Conclusion

## Notes
[Code](https://github.com/hlzhu09/Hierarchical-Human-Parsing)

## References
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTkwMjA4MDc2NCwtMjEyNTQxMTY1NF19
-->