# Learning 3D Part Assembly from a Single Image

## Summary
They introduce the task of single-image-guided 3D part assembly: inducing
6D poses of the parts in 3D space from a set of 3D unlabeled parts and an image depicting the complete object.
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
- Part-instance image segmentation
- Part pose prediction
## Evaluation

## Conclusion

## Notes

## References
<!--stackedit_data:
eyJoaXN0b3J5IjpbMzc0MDA0NzgxLDMzODI3NjE2NiwtMzUxMD
k3MzIyLC00MjY0MzcyNTRdfQ==
-->