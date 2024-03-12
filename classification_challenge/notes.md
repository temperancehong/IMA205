## Ideas

- Combine the three image channels with the ground truth mask to create a 4 channel image
- For the images without ground truth masks, can we use SAM to create the masks?

## Useful models and their references

- Resnet18
- Unet
- [Beginner CNN](https://medium.com/@agarwal.bh/multi-class-image-classification-model-using-cnn-dcf7eaa3391b)
- 

## Observation notes
- There are 1945 images with ground truth masks, compared to 17053 without.
- The images are of different dimension
- 
## Notes for later to do 
- [ ] Benchmark model without any pre-processing
- [ ] Data augmentation
