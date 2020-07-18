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
	- K part generators for K predefined semantic labels.
	- Each part generator is trained to generate a volume of a specific part from a random vector.
	- 3D volumes with a resolution of 64x64x64
	- VAE-GAN
- **Part assembler**. 
	- Taking K part volumes as input, part assembler regresses a transformation, including a scaling and a translation for 
## Evaluation

## Conclusion

## Notes
- Part generation in this paper means part category rather than part instance.
## References
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTQ2Mzc0MDQ3NCw0NjI4ODUzOTQsMjEyNT
A3ODM5MSwtMzk5Mjc5MTIzLC02NTU3MDA4NF19
-->