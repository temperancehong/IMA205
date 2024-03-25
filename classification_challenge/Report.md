# Literature Review

## 1. Automated Melanoma Recognition

[Link](https://ieeexplore.ieee.org/document/918473)

The type of lighting used to obtain the image does not affect the classification and segmentation result.

The task is a three class classification problem: benign, malignant, and dysplastic.

### Segmentation

Many region based segmentation methods are used. 

- Thresholding operation
- Adaptive thresholding
- PCT/median-cut algorithm
- Combined methods

- Hair problem:
  - dark elongated structure: applying grey scale morphological operation of closing.

Main algorithm: (best method in the paper)
- Global thresholding
- dynamic thresholding
- 3D color clustering

Fusion of individual segmentation results: rejection of certain results (outlisers among all the segmentation result of the same lesion).


### Feature Calculation

ABCD rule. Asymmetry, Border irregularity, Color variegation, Dermatoscopical structures.
And also further eight parameters.

- Asymmetry: different shape features
- Border irregularity: sharpness of the transition from lesion interior to border, mean and standard deviation of these gradient values. fractal dimensions
- Color: statistical parameters of RGB and HSV color spaces. Normal skin colors lies on a 2D plan in 3D splace, while atypical skin structures deviate from the surface.

### Feature selection

Most important feature: size of the lesion.

- Sequential forward selection: five features starting from 87.
- feature selection with NN, node pruning. 

No normalization of color during image processing.

### Feature calculation

- Global features
  - size
  - shape descriptor, and further descriptors are derived from the bounding rectangle
  - Color features: from RGB into HSI color space; min, max, avg, var of Intensity channel and Hue channel
  - Normalize the color channels: subtracting avg intensity in skin area (negative class in binary mask); Hue channel normalization by subtracting the hue value with highest probability in the skin area. (negative class in binary mask
  - The min, max, avg, std are again calculated as features
  - Significant colors: using *median cut color quantization*, 15 colors are selected from the lesion area. The color histogram is calculated for each color channel. Parameter: numbers of colors in the lesion area(positive class in binary mask), and percentage of the 15 colors in the lesion area.
  - Transition areas: gradient mask. (border features)
- Local features
  - Category of shape and size: From segmentation mask: perimeter, area and formfactor
  - Symmetry: ratio of feature values in different quadrant


### Feature subset selection

KNN (24NN) chosen as separability criterion for feature subset selection.

Sequential forward floating selection (SFFS, result: subset size 10) and Sequential backward floating selection (SBFS, result: subset size 15) are used.

## 2. Multi-features extraction based on deep learning for skin lesion classification

[Link](https://www.sciencedirect.com/science/article/pii/S0040816621002172)
