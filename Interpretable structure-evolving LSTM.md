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
	- 
## Evaluation

## Conclusion

## Notes

## References
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjEzNzIwMjU0NywtNDg1MjQzMjE4LC0xMT
A1NTI1MzIyLDQyMDM0MzM2NiwtOTY4MzM5NDI5LDM1MDIxODA3
MV19
-->