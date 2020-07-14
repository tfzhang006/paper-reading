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
	- A stochastic mechanism is adopted to find a good graph transition among large search space. The acceptance rate is defined to decide whether a random solution is reasonable.
	- According to the definition of acceptance rate, the model is more likely to accept a new graph structure that can bring more performance improvement and that has larger transition probability(multiplying all merging probabilities of eliminated edges).
	- Input states, hidden states and memory states of merged nodes are averaged and used for further updating.
- L2-norm loss for merging probability and cross entropy loss for segmentation.
## Evaluation
PASCAL-Person-part/Horse-Cow/ATR dataset
## Conclusion
- Using deterministic merging scheme is inferior to the stochastic policy.
- 
## Notes

## References
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTU2MzA2MTAyMSwxMTU2MjQwNzA5LC0xOD
Y4MzM5OTg2LDIxMzcyMDI1NDcsLTQ4NTI0MzIxOCwtMTEwNTUy
NTMyMiw0MjAzNDMzNjYsLTk2ODMzOTQyOSwzNTAyMTgwNzFdfQ
==
-->