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
		- PerformmingSeveral iterations of message passing in a child graph.
		- Perform
	- Geometry decoder
	- Graph decoder
## Evaluation

## Conclusion

## Notes

## References
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjAzNzYyNjEyMiwtMTk4NTM1NzU0LC03MD
YyNjUzMzFdfQ==
-->