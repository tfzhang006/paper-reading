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
	- 256D duplicated parent node feature is decoded into two 128D features for child nodes, which is called *recursive context feature*.
	- It is implemented with a two-layer fully connected network with tanh.
- Node classification module
	- *Part shape feature* is extracted for the shape 
	- Taking the *current node feature* as input, which is formed by concatenation of part shape feature and recursive context feature, this module predicts its node type as one of the following three ones: adjacency, symmetry or leaf.
	- 
- Node segmentation module
## Evaluation

## Conclusion

## Notes

## References
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTUzMDI4MjAyMiwtMTU0NDI5Mjg0XX0=
-->