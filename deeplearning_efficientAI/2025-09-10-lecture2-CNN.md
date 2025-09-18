---
layout: post
title: "Lecture2: CNN"
categories: [deeplearning_efficientAI]
---


# Basic Building Blocks
## Convolutional Neural Networks
- CNNs are a type of artificial neural network intended to process structured grid data especially images. They are effective in tasks like recognition, object detection and segmentation.
- Building blocks of a CNN includes
  - Convolutional Layer
  - Activation Layer
  - Normaliztaion Layer
  - Pooling Layer
  - Softmax Layer

### Convolutional Layer
Core builing block of a CNN and the most computational intensie layer.
**- Step 1:** Each kernel moves across the spatial dimensions of feature maps in the input activation, gathering the information within those spatial dimensions.
**- Step 2:** Information from each feature maps are then aggregated by summing the Convolutional feature maps together. A bias may be introduced.

#### Paddings: 
used to preserve the spatical size of the output features.

#### Stride:
control the walking step of kernel

### Activation Functions
GeLL: Gaussian error linear unit.
GeLU is increasingly being adopted in transformers and CNNs today.

### Batch Normalization
Used to improve training stability and performance of neural networks.

### Pooling
- Reduce the spatial size of the representation and reduce the amount of parameters and computation in the CNN.
- Enhance the model invariance to spatial transformations such as translation and rotation, thereby reducing the risk of overfitting

### Fully Connected Layers
Normally used in the last several layers to generate the classification results.

# Popular CNN Architectures

## ResNet
- Bypass the input to the output(residual link) to enable stability during training.
- The performance is at least as good as the shallower DNN.

## MobileNet
- Step 1: Depthwise Convolution

Each kernel moves across the spatial dimensions of feature maps in the input activations, analyzing the information within those spatial dimensions.

- Step 2: Pointwise Convolution

The information from each feature maps are then aggregated by multiplying with the weight in the pointwise conv kernel and summing the Convolutional feature maps together.

A bias may be introduced.

- Key Points: Share the depthwise filters

## MobileNet-V2

- Add residual link between the blocks
- Adopt ReLU6 replace ReLU

## Group Convolution

- Only use a subset(group) of input activations for one convolutional operation.
- Each group of feature maps within the input only convolved with partial weight kernels
- Large saving on memory consumption and computation cost.

## ShuffleNet
- Shuffle operatio is used to exchange information across the groups
- Shuffle with group convolution can replace conventional full-channel convolution without noticeable accuracy degradation.
- Under the same level of computational complexity, shufflenet is better than MobileNet.


## SqueezeNet
- Aims to reduce the CNN parameter size rather than computational cost
- Strategies:
  - Replace 3x3 filters with 1x1 filters
  - Decrease the number of input channels to 3x3 filters
  - Downsample late to make large activation maps.

## DenseNet
Every previous activations will be concatenated with current activations to build input for next layer.

## EfficientNet
- Balance all dimensions of network width/depth/resolution, and surprisingly such balance can be achieved by simple scaling each of them with constant ratio.
- SiLU is used in the EfficientNet architecture

## ConvNext
- Leverage the insight of vision transformer to enhance the performance of CNN.
- Major changes from ResNet50 to ConvNext 50
  - #blocks from (3, 4, 6, 3) to (3, 3, 9, 3)
  - Use depthwise separable convolution
  - Large convolutional kernel
  - Replacing ReLU with GELU
  - Substituting BN with LN

## ShiftNet
- Completely remove the computation for the depthwise convolution.
- The shift positions are predefined for each channel.

## Deformable Convolutional Networks

# CNN Architecture for other Vision Task

## Image Segmentation

## Object Detection

### Transposed Convolution

### Focal Loss
Downweight easy examples and thus focus training on hard negatives.

## Video Processing

### 2D convolution