## Ideas

- Combine the three image channels with the ground truth mask to create a 4 channel image
- For the images without ground truth masks, can we use SAM to create the masks?

## Useful models and their references

- Resnet18, with data augementation for imbalanced class, we arrive at 0.191
- Unet
- [Beginner CNN](https://medium.com/@agarwal.bh/multi-class-image-classification-model-using-cnn-dcf7eaa3391b) with data augmentation for imbalanced class, we arrive at 0.166
- 

## Observation notes
- There are 1945 images with ground truth masks, compared to 17053 without.
- The images are of different dimension
- Not pretrained Resnet18 is better than the one pretrained is because for the pretrained,
the model expect a normalized input. 
- 
## Notes for later to do 
- [x] Benchmark model without any pre-processing (**Kaggle score: 0.136**)
- [x] Benchmark model with data augmentation (**Kaggle score: 0.166**)
- [ ] Data augmentation
- [x] Address class imbalance with data augmentation
- [x] Resnet18 with balanced dataset, (**Kaggle score 0.191**)
- [x] Resnet18 but not pretrained, (**Kaggle score 0.275**)
- [x] Resnet18 not pretrained with meta data integrated, no imbalance augmentation (**Kaggle score 0.466**)
- [x] Resnet18 not pretrained with meta data integrated, with imbalance augmentation (**Kaggle score 0.364**)
- [x] Unet encoder with only image, score is very low (**Kaggle score 0.149**)
## Log
- Used pretrained Resnet18 model to train the dataset, general training data augmentation should only 
be to tensor, if we add others the training score will be very low
- Used unpretrained Resnet18 + meta data but no data augmentation for class imbalance, learning rate should be set to 0.01
