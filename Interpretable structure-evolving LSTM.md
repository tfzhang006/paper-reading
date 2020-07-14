# Interpretable structure-evolving LSTM
## Summary
A bottom-up method is proposed to progressively obtain abstract representation in higher levels, which is based on evolving graph and LSTM network.
## Research Objective
Taking advantage of structure-evolving LSTM to perform human parsing.
## Background and Problems
- Existing LSTM models can only process data with pre-fixed structure.
- Semantic object parsing can benefit from modeling the contextual dependencies among regions in different levels.
## Methods
- Initial graph is constructed on super-pixels using SLIC. Node feature are computed by averaging convolutional feature of all pixels within a super-pixel.
- Learning new graph structure and updating LSTM parameters are alternatively performed.
-  LSTM update
	- While computing gates, hidden states(t) and memory states(t) for a specific node, those input states(t), hidden states(t-1) of current node and *hidden states of neighboring nodes* have influence on them.
	-  Additional merging probabilities of edges are predicted and supervised at the same time.
- Structure evolving
	- A stochastic mechanism is adopted to find a good graph transition among large search space. The acceptance rate is defined to decide whether a random merge solution is reasonable.
	- According to the definition of acceptance
## Evaluation

## Conclusion

## Notes

## References
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjE0NzQxOTc3LDExNTYyNDA3MDksLTE4Nj
gzMzk5ODYsMjEzNzIwMjU0NywtNDg1MjQzMjE4LC0xMTA1NTI1
MzIyLDQyMDM0MzM2NiwtOTY4MzM5NDI5LDM1MDIxODA3MV19
-->