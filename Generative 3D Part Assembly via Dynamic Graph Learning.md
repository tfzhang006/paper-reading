# Generative 3D Part Assembly via Dynamic Graph Learning

## Summary
This paper propose to use a dynamic graph learning framework that predicts a 6-DoF part pose for each input part point cloud via forming a dynamically varying part graph and iteratively reasoning over the part poses and their relations.
## Research Objective
- To assemble 3D shapes conditioned on a given set of part geometry with variable number of parts. Moreover, the model knows little semantic knowledge on the input parts.
## Background and Problems
- Without referring to any procedural or external guidance, the task of 3D part assembly involves exploring an extremely large solution spaces and reasoning over the input part geometry for candidate assembly proposals. 
- Existing methods always assume certain part priors.
## Methods
- Iterative GNN backbone
	- Encoding each part geometry as a node.
	- Alternatively updating the edge and node features.
- Dynamic relation reasoning module
	- Learning to reason a directed edge-wise weight scalar to indicate the significance of the relation. Then, the node feature can be updated via multiplying the weight scalar and edge attribute.
- Dynamic part aggregation module
	- A dense node set including all the part nodes. A sparse node set crea
	- Alternatively updating the relation graph between the dense and sparse node sets.
## Evaluation

## Conclusion

## Notes

## References
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE2MzYzMDI3NzcsMTgwNTMwNDQ5LC0xMj
Q2ODM2NTQ5XX0=
-->