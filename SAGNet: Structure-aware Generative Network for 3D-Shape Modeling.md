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
	- The geometry and structure information is exchanged between two branches. Attention here acts as a weight
- 2-way VAE
## Evaluation

## Conclusion

## Notes

## References
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE4OTA5OTk5NjIsMjA2NDA2NTI4OV19
-->