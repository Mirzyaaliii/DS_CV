# Depper Systems Computer Vision
## To identify the orientation of an image and correct the image accordingly


## Implementation

All the implementation details for executing the code is provided in the .ipynb files -> change all the paths accordingly which is written at the top of the each .ipynb file


## Approach

We can formulate this problem as a classification problem and in which images are classifies into 4 classes - upright, rotated_left, rotated_right, or upside_down.

After classifying the image, need to rotate it according to its orientation.

For this problem, 2 Neural Network (NN)-based approach are analyzed which are as following:

i) Convolution Neural Network (CNN)-based approach

ii) Residual Network (ResNet)-based approach

### Analysis:
A recent trend indicates that a higher number of stacked layers of neural networks gives better results. However, current studies show that deeper neural networks are more challenging to train due to the problems, such as overfitting, vanishing gradient, etc. Although ResNet is deeper version of CNN, it solves these problem. The main reason behind this is the identity mapping. Due to the skip connections in ResNet, it would be easier to push the residual to zero than to fit an identity mapping by a stack of nonlinear layers. 

### Rotation:
To rotate (correct) the images OpenCV is used -
1) upright - do not rotate the image,
2) rotated_left - rotate the image 90 degree clockwise,
3) rotated_right - rotate the image 90 degree counterclockwise,
4) upside_down - rotate the image 180 degree.


## Results

-> Prediction of the test images are stored in .csv file in the result folder for both the approach.

-> results.txt file contains thh link of the .npy file of the size (5361, 64, 64, 3) and link of corrected images folder.
