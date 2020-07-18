# Learning Part Generation and Assembly for Structure-aware Shape Synthesis

## Summary
This paper proposes a part-aware deep generative network which delegates the learning of part composition and part placement into separate networks.
## Research Objective
To better model structural variants of 3D shapes through learning a part-aware generative network.
## Background and Problems
- Existing deep generative models tend to generate 3D models in a holistic manner, without comprehending its compositional parts explicitly.
- A consensus about the "structure" of a shape is the combination of part composition and the relative positioning between parts.
## Methods
- **Part generators**. 
	- K part generators for K predefined semantic labels. Each part generator is trained to generate a volume of a specific part from a random vector.
	- 3D volumes with a resolution of 64x64x64
	- VAE-GAN
- **Part assembler**. 
	- Taking K part volumes as input, part assembler regresses a transformation, including a scaling and a translation for each part.
	- A 64x64x64xK input tensor.
	- Five volumetric fully convolutional layers.
	- Specifying an anchor part which is kept fixed to make the transformation estimation determined. The occupied voxels in the anchor part volumes are set to -1.
## Evaluation
- ShapeNet part dataset
- Part generation: Average symmetry measure
- Part assembly: Part assembly quality(average IoU)
- Random shape generation: Diversity(inception score)
- Shape segmentation
## Conclusion
- The part assembler learns the spatial relations between semantic parts in terms of relative different parts, so it can assemble parts into a valid and complete shape volume.
## Notes
- Part generation in this paper means part category rather than part instance.
- The part generator and part assembler are not trained jointly.
## References
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTA2Nzc2ODI4NCwtMTI3MDgyMjQzLC02Mj
Y1MjEwNjYsMTI1OTk0NDQwMCwtOTE5MTQ1MjIyLDE4ODE0NjM0
OTIsNDYyODg1Mzk0LDIxMjUwNzgzOTEsLTM5OTI3OTEyMywtNj
U1NzAwODRdfQ==
-->