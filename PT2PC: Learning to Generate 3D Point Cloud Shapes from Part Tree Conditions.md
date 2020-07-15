# PT2PC: Learning to Generate 3D Point Cloud Shapes from Part Tree Conditions

## Summary
This paper provides a solution for a novel conditional shape generation problem, which generates diverse 3D point clouds given the part tree condition.
## Research Objective
To generate a 3D point cloud geometry for a shape from a symbolic part tree representation.
## Background and Problems
- Extant work on holistic 3D shape generation does not explicitly consider part semantic and structural information in the generation process.
- In contrast, a structure-conditioned 3D generative model enables many real-world applications in computer vision and graphics.
## Methods
- Symbolic part tree representation. 
	- Following the semantic part hierarchy defined in PartNet.
	- Each part instance is composed of two components: a semantic label and a part instance identifier, both of which are represented as one-hot vectors.
- Part-tree conditioned **generator**
	- Part-tree encoder. Taking node feature, semantic label and part instance identifier of all children as input, the encoder, which is implemented as a PointNet, computes node feature for current node. Leaf node features are initialized as zero.
	- Part-tree feature decoder. Taking node feature, semantic label, part instance identifier and decoded feature from parent node as input, the decoder, which is implemented as a MLP, outputs *part feature*. Parent node feature is replaced as random noise.
	- Part point cloud decoder. The point cloud decoder is designed to deform a fixed surface point cloud of a unit cube into target part point cloud based on its input. Specifically, the input is a 1000-size point cloud and each point's coordinate is concatenated with the part feature. After obtaining coordinates of target point cloud, FPS is adopted to perform downsample.
- Part-tree conditioned **discriminator**
	- Part point cloud discriminator
		- Part point cloud encoder. 
		- Tree-based feature encoder. In a bottom-up fashion, the features propagate from the leaf level finally to the root.
		- Scoring network. A simple fully-connected layer.
	- Shape point cloud discriminator
		- PointNet encoder
		- Scoring network
## Evaluation

## Conclusion

## Notes

## References
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTMwNTI2Nzk2NiwtMTg2MTg0MDc5LDI1OD
UxODE4NSwxOTAxMzY5MDk0LDEzNzk1NTQwNTVdfQ==
-->