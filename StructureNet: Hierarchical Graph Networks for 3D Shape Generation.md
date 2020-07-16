# StructureNet: Hierarchical Graph Networks for 3D Shape Generation

## Summary

## Research Objective
To build a continuous latent space that can incorporate diverse shape variations, and subsequently to be exploited by various applications.
## Background and Problems
- Because of the binary constraint, GRASS has to search over possible binarizations of the n-ary hierarchies found in objects. The task of finding a canonical binary tree representation becomes increasingly challenging on a very large shape family.
## Methods
- A hierarchy of graph
	- Part representation. Minimum oriented bounding box or a point cloud. Each part also has a semantic label.
	- Hierarchical decomposition.
	- Geometric relationship. Adjacency, reflective symmetry, rotational symmetry, and translational symmetry.
- Hierarchical graph networks
	- Geometry encoder.  Encoding the geometric representation of a leaf node into a feature vector.
	- Graph encoder.
		- Performing Several iterations of message passing in a child graph.
		- The graph feature vector is computed by max-pooling over all child parts.
		- Concatenating the graph feature vector computed after each iteration and pass them through a SLP.
	- Geometry decoder
		- Both bounding box decoder and point cloud decoder are implemented as a MLP.
	- Graph decoder
		- 
## Evaluation

## Conclusion

## Notes

## References
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjgwMTc5MjA5LC0xOTg1MzU3NTQsLTcwNj
I2NTMzMV19
-->