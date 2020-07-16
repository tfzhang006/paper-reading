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
		- To transform the feature vector back into the geometry representation.
		- Both bounding box decoder and point cloud decoder are implemented as a MLP.
	- Graph decoder
		- To transform a parent feature vector back into the child graph where each child part is represented by a feature vector and its label.
		- The decoder is designed to output a fixed maximum number(10) of child parts and all edges between them, together with a binary probability that predict part or node exists in the child graph.
		- Predicting initial feature vectors from parent feature vector and existence. Discarding no existing parts.
		- Recovering the edges between a pair of parts based on their pair of feature vectors based on predicted probability. Discarding no existing edges.
		- Performing two iterations of message passing.
		- Decoding the semantic labels and a leaf part probability.
## Evaluation

## Conclusion

## Notes
- The VAE is trained on a dataset of shapes from a given category.
## References
<!--stackedit_data:
eyJoaXN0b3J5IjpbNTQ1NjAyNTU3LDg4NTI4MDM1MSwyODAxNz
kyMDksLTE5ODUzNTc1NCwtNzA2MjY1MzMxXX0=
-->