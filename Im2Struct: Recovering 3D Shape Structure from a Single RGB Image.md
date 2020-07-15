# Im2Struct: Recovering 3D Shape Structure from a Single RGB Image

## Summary
This paper develop a network to recursively decodes a hierarchy of cuboids from a encoded image.
## Research Objective
To recover 3D shape structures from single RGB images, where structure refers to shape parts represented by cuboids.
## Background and Problems
- Existing models which learn to reconstruct 3D volumes from 2D images lose shape topology or part structure information.
- Shape structure, encompassing part com- position and part relations, has been found highly important to semantic 3D shape understanding and editing.
- Different from shape geometry, part decomposition and relations do not manifest explicitly in 2D images. Mapping from pixels to part structure is highly ill-posed.
- Natural images always contain cluttered background and the imaged objects have large variations of appearance due to different textures and lighting conditions.
## Methods
- Structure masking network
	- This is a two-scale network, in which the feature maps and outputs of the first scale network are fed into various layers of the second scale one for refinement.
- Structure recovery network
	- Feature map of the last layer of structure masking network concatenated with CNN feature of the input image is fed into the network.
	- The box structure decoder is a recursive neural network(RvNN), which includes a node classifier and three types of node decoders for different nodes.
	- The structure recovery loss is computed as the sum of the *box reconstruction error* and the *cross entropy loss for node classification*.
## Evaluation
- 800 3D shapes from three categories in ShapeNet.
- Rendering 60 images for each shape with randomly selected backgrounds from NYU v2.
- Inferring consistent hierarchy trees for the shapes of each category.
## Conclusion
- The firsh work to recover detailed 3D shape structures from 2D images.
- Applications includes structure-aware image editing and structure-assisted 3D volume refinement.
## Notes

## References
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTExODM2MDg3NDJdfQ==
-->