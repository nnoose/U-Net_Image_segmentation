# U-Net_Image_segmentation
U-Net image segmentation project

# Overview
## Goal

The Goal of this project is to perform image segmentation on the OxfordIIITPets dataset using Pytorch using a machine learning model. 
Our model's architecture is based off of the U-Net described in the paper: "U-Net: Convolutional Networks for Biomedical Image Segmentation"

### Architecture From the paper
The overall architecture from the original paper is a fully convolutional neural network that is similar to an autoencoder. 
The model can be viewed as 9 "blocks" of convolutional layers with different functions applied before or after each block. After each of the first four "blocks,"
a copy of the output of the block is saved for later use and another copy is run through a max pooling layer with stride 2 and width 2, the output of which is the input to the next block.

The fifth block is just a normal set of convolutional layers; no output is saved.

Before each of the last 4 blocks is applied, an "up-convolution" is applied to the output of the previous block to increase the size, this "up-convolution" is a convolution transpose operation with kernel size = 2 and stride = 2. The output of each "up-convolution" is concatenated with each of the stored outputs from the first 4 blocks in reverse order (i.e. block 3's output is concatenated to the output of "up-convolution 0," block 2's output is concatenated to the output of "up-convolution 1" and so on). these concatenated ouputs are the inputs to the last 4 layers.


TODO

### Our Architecture
TODO

### Sources:
- Ronneberger, O., Fischer, P., Brox, T. (2015). U-Net: Convolutional Networks for Biomedical Image Segmentation. In: Navab, N., 
  Hornegger, J., Wells, W., Frangi, A. (eds) Medical Image Computing and Computer-Assisted Intervention – MICCAI 2015. MICCAI 2015. Lecture Notes in Computer Science(), vol 9351. Springer, Cham. https://doi.org/10.1007/978-3-319-24574-4_28
