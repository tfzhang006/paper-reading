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
	- A stochastic mechanism is adopted to find a good graph transition among large search space.
## Evaluation

## Conclusion

## Notes

## References
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTkxNzc4NTAwMywxMTU2MjQwNzA5LC0xOD
Y4MzM5OTg2LDIxMzcyMDI1NDcsLTQ4NTI0MzIxOCwtMTEwNTUy
NTMyMiw0MjAzNDMzNjYsLTk2ODMzOTQyOSwzNTAyMTgwNzFdfQ
==
-->