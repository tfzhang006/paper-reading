# Partnet: A Recursive Part Decomposition Network for Fine-grained and Hierarchical Shape Segmentation

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
- FineSeg dataset. Part hierarchy for each shape is constructed using [method](#References).
- Comparison of semantic segmentation and instance segmentation.
- PartNet does not produce semantic labels for points, so it needs extra module to predict a semantic label for each part.
## Conclusion
- Divide-and-conquer nature of recursive decomposition does help reduce the difficulty of segmentation learning.
## Notes
- PartNet still needs to be trained for each shape category separately. Learning a general decompositional model for shapes from multiple classes is a future direction. 
- PartNet is trained with reasonable ground-truth hierarchies. An unsupervised method is demanded.
## References
- Symmetry hierarchy of man-made objects
- Learning hierarchical shape segmentation and labeling from online repositories
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTk0NjYxNDczNSwtNTc2OTcyMzAzLDIxMD
kyOTQ4NjIsLTE1NDQyOTI4NF19
-->