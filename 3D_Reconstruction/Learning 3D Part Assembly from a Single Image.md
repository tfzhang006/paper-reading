# Learning 3D Part Assembly from a Single Image

## Summary
They introduce the task of single-image-guided 3D part assembly: inducing
6D poses of the parts in 3D space from a set of 3D *unlabeled* parts and an image depicting the complete object.
## Research Objective
They aim to learn generalizable skills that allow robots to autonomously assemble unseen objects from parts.
## Background and Problems
- Robots can acquire geometry information for each part using 3D sensing, but the only information provided for the entire object shape is the instruction image.
- Those structure-aware shape modeling works need to assume specific granularity or semantics of the input parts.
-  It is a hart problem to teach machines to read sequential instructions depicted with natural languages and figures in step- by-step assembling process.
## Methods
- Pose and scale normalization of parts
	- Normalize each part point cloud to have zero-mean center and use a local part coordinate.
	- The longest box diagonal across all parts of a shape has a unit length while preserving their relative scales.
- **Part-instance image segmentation**
	- To generate instance-level 2D segmentation mask on image.
	- For each part point cloud, we extract $f_{3d}=[f_{local}; f_{global}]$, where $f_{local}$ is a per-part local feature and $f_{global}$ is a contextual feature.
	- The U-Net takes an image as input and produce a bottleneck feature map $f_{2d}$. Concatenating the $f_{2d}$ and $f_{3d}$ as a new bottleneck feature, the decoder then produces a part mask for every input part.
- **Part pose prediction**
	- Leveraging both the 2D mask features and the 3D geometry features to propose 6D part poses.
	- Mask-conditioned part feature
		- $f_{img}, f_{mask}$ extracted from separate ResNet-18 and $f_{3d}$ mentioned before.
	- Two-phase graph convolution
		- The first phase. Drawing pairwise edges among all parts in every geometrically equivalent part classes and performing graph convolution.
		- The second phase. Drawing a new set of edges by finding top-5 nearest neighbors for each part based upon the initial assembly and performing graph convolution.
		- The graph convolution is implemented as two iterations of message passing.
		- A MLP is used to decoder part pose.
- Loss for part-instance image segmentation
	- Performing *Hungarian matching* within each geometrically equivalent class
	- 
- Loss for part pose prediction
	- Performing Hungarian matching within each geometrically equivalent class
	- L2 loss for part translation, *Chamfer distance* and L2 loss for part rotation, and holistic Chamfer distance for shape. 
## Evaluation
- Three furniture categories filtering out the shapes with more than 20 parts.
- Rendering images from PartNet models
- Part Accuracy Score
- Shape Chamfer distance
## Conclusion
- The part-instance im- age segmentation module plays the most important role in the pipeline.
- How to leverage multiple images or 3D partial scans as inputs to achieve better results.
- Explicitly considering the connecting junctions between parts as constraints.
## Notes

## References
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTcwNzI1Njk0NF19
-->