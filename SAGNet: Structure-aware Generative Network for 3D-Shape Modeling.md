# SAGNet: Structure-aware Generative Network for 3D-Shape Modeling

## Summary

## Research Objective

## Background and Problems

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

## Conclusion

## Notes

## References
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTQzNDg1NDExMSwyMDY0MDY1Mjg5XX0=
-->