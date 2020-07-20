# SAGNet: Structure-aware Generative Network for 3D-Shape Modeling

## Summary
Given a set of segmented objects of a certain class, the geometry of their parts and the pairwise relationships between them (the structure) are jointly learned and embedded in a latent space by an autoencoder. 
## Research Objective

## Background and Problems
- Structure and geometry are often interdependent, exhibiting complex relations and dependencies that are hard to model directly.
## Methods
- Two-branch autoencoder
	- The geometry branch accepts a series of k voxel maps as input and outputs k 512D features. 
	- The structure branch takes in K=k(k-1)/2 pairs of bounding boxes and produces K 512D feature.
	- Then the features are fed into two different GRUs.
- Attention component
	- The geometry and structure information is exchanged between two branches. Attention here acts as a weight for summation.
- 2-way VAE
	- The k 512D geometry features and K 512D structural features are fused into a single 512D feature separately through two different GRUs. They are fed into the third GRU with additional part mask to produce a new feature and then to yield mean and standard deviation of a Gaussian distribution.
	- The decoder GRU transform latent code back into voxel maps and k bounding boxes for all parts.
## Evaluation
- Shape generation
- Geometry-structure mapping
## Conclusion

## Notes
- The model is trained on a set of segmented and consistently oriented shapes.
- A shape is represented by k voxel maps and K pair of axis-aligned bounding boxes where each pair contains 2x6 coordinates(three for center of a box and three for its length, width and height).
- Missing parts are represented using zeros. 
- [SAGNet](https://github.com/zhijieW94/SAGNet)
## References
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTY0NzM2MjY0MCwyMDY0MDY1Mjg5XX0=
-->