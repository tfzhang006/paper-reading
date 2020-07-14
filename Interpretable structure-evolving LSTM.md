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
- Structure-evolving LSTM
	- While computing gates, hidden states(t) and memory states(t), besides input states(t) and hidden states(t-1), 
## Evaluation

## Conclusion

## Notes

## References
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTQ4NDg3NjE2NiwyMTM3MjAyNTQ3LC00OD
UyNDMyMTgsLTExMDU1MjUzMjIsNDIwMzQzMzY2LC05NjgzMzk0
MjksMzUwMjE4MDcxXX0=
-->