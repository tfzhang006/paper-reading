# Learning Compositional Neural Information Fusion for Human Parsing
## Summary
This work proposes to combine neural networks with the compositional hierarchy of human bodies for efficient and complete human parsing.
## Research Objective
To utilize cross-level information of body structure based on graph.
## Background and Problems
- Existing models fail to make full use of the rich structures in this task.
- Only focusing on leaf nodes in human hierarchy loses cross-level information.
## Methods
- Direct inference network
	- A backbone network for *image embedding*
	- Three level-specific FCN for *level-specific embedding*
	- A Squeeze-and-Excitation block for *node-specific embedding*
	- The direct inference network predicts segmentation
- Top-down inference network
	- We concatenate initial estimation of parent node and current node feature and feed it into FCN-based top-down inference network.
- Bottom-up inference network
	- By using position-wise max-pooling, we can gather information from multiple descendants.
	- Then we concatenate information from children and current node to give a prediction.
- Conditional fusion network
	- 
## Evaluation

## Conclusion

## Notes

## References
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTMxMzg5OTUxLDE3NjgwMDkwNDUsLTE0Mj
Y0MDM4MzhdfQ==
-->