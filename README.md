# Depper Systems - Computer Vision (DS_CV)
## To identify the orientation of an image and correct the image accordingly


## Implementation

All the implementation details for executing the code is provided in the .ipynb files -> change all the paths according to the instruction written for the each .ipynb file


## Approach

We can formulate this problem as a classification problem. In particular, the task is to identify the rotation of the image. To solve this problem, feature mapping technique along with supervised learning is used to build efficient classifier for this task. Here, images are classifies into four categories: 
1. upright
2. rotated_left 
3. rotated_right 
4. upside_down

For supervised training of classifier, labels are mapped with numerical values, i.e.,rotated_right - 0, rotated_left -1, upright - 2, upside_down - 3.  Image tensor is given as input to classifier along with the ground truth for supervised training. After classification, image is rotated upright according to its predicted orientation.

For classification purpose, two Deep Neural Network (DNN)-based approach are used as below:

i) Convolution Neural Network (CNN)-based Approach

ii) Residual Network (ResNet)-based Approach

Both the network are trained on the given training data for two epochs. CNN-based network is optimized with RMSprop optimization technique, whereas ResNet is optimized using Adam optimization with 0.0001 learning rate.


### Why ResNet?
A recent trend indicates that a higher number of stacked layers of neural networks gives better results. However, current studies show that deeper neural networks are more challenging to train due to the problems, such as overfitting, vanishing gradient, etc. Although ResNet is deeper version of CNN, it solves these problem. The main reason behind this is the identity mapping. Due to the skip connections in ResNet, it would be easier to push the residual to zero than to fit an identity mapping by a stack of nonlinear layers. Hence, ResNet is used here to improve the classification results compare to the CNN-based approach.

### Rotation:
OpenCV is used to do rotation of the images to make it upright. The rotations are done based on the predictions and below rotation techniques are used -
1) upright - do not rotate the image,
2) rotated_left - rotate the image 90 degree clockwise,
3) rotated_right - rotate the image 90 degree counterclockwise,
4) upside_down - rotate the image 180 degree.


## Results

* Prediction of the test images are stored in .csv file in the result folder for both approaches.

* results.txt file contains link of the .npy file of the size (5361, 64, 64, 3) and link of corrected images folder.
