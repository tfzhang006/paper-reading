# Partnet: A recursive part decomposition network for fine-grained and hierarchical shape segmentation

## Summary
This paper proposes a model for hierarchical segmentation of 3D shapes, which is based on recursive binary decomposition.
## Research Objective
To segment a 3D shape in point cloud into an unfixed number of parts, depending on the shape complexity.
## Background and Problems
- Existing models are trained targeting a fixed set of labels.
- Labeling all primitives simultaneously cannot exploit the hierarchical nature.
## Methods
- Node decoding module
	-  Parent node feature(256D) is decoded into two features for child nodes, which is called *recursive context feature*(128D).
	- It is implemented with a two-layer fully connected network with tanh.
- Node classification module
	- *Part shape feature*(128D) is extracted for the partial shape at current node.
	- Taking the *current node feature*(256D) as input, which is formed by concatenation of part shape feature and recursive context feature, this module predicts its node type as one of the following three ones: adjacency, symmetry or leaf.
	- This module is implemented with two fully-connected layers with tanh.
	- It can be trained with the ground-truth hierarchical segmentation.
- Node segmentation module
	- *Point-wise PointNet feature* together with current node feature is used to produce point-wise binary labels.
- Overall loss function consists of average node classification loss and average node segmentation loss over all relevant nodes.
## Evaluation
- FineSeg dataset. Part hierarchy for each shape is 
## Conclusion

## Notes

## References
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjEwOTI5NDg2MiwtMTU0NDI5Mjg0XX0=
-->