---
layout: post
title: "Lecture 1: DNN Basics
categories: [deeplearning_efficientAI]
---

# Overview
Deep Neural Network(DNN) in the most exciting research topic in the area of Machine Learning(ML). Inspired by the structure of neuron system in human brain, scientists proposed to build Neural Network, which consists of many layers of computation nodes(neurons), to fit functions mapping from any inputs to outputs that are hard for humans to define and find.

The journey to DNN starts with Multi-Layer Perceptrons(MLP).

# Multi-Layer Perceptrons(MLP)
MLP is the most straightforward neural network. It consists of many sequential layers. Each layer contains multiple independent nodes that take outputs(activations) from previous layer and pass the activated weighted sum-up to the next layer.

Most MLPs are fully-connected which means each node(except that in the first layer) takes inputs from all the nodes in the previous layer to calcualte the activations.

Due to the native structure of MLP, we can use a vector to represent the values in each layer and regard the passing between layers as a Matrix Multiplication. It is noteworthy that a Bias is added to the multiplication result to serve as deviation in latent space. We call the procedure to calculate next layer activation based on current layer activation as "forwarding". 

The mathmatical expresssion is $Y = X*W+b$, where $X$ is the batched input from previous layer with shape of $(batch, input\_activation)$, $W$ is the matrix of weighs from each node in previous layer to each node in next layer with shape of $(input\_activation, output\_activation)$, $b$ is the bias vector of next layer with length of $(output\_activation)$ and $Y$ is the weighted sum of previous layer with bias with shape of $(batch, output_activation)$.

To increase the expressiveness of model, a non-linear activation function is often extended to the tail of previous operation. Think about it, without non-linear activation, the MLP can only do the linear transformation!

# Activation Functions
There are different types of activation fuction in different shape and range. Belows are the most common ones in DNN:

## Sigmoid
Function: $\sigma(x) = \frac{1}{1+e^{-x}}$

Range: [0, 1]

Derivative: $\sigma(x)(1-\sigma(x))$

## Tanh
Function: $tanh(x) = \frac{e^{2x} - 1}{e^{2x} + 1}$

Range: [-1, 1]

Derivative: $1-tanh^2(x)$

## ReLU: Rectified Linear Unit
Function: $ReLU(x) = x\ if\ x\geq\ 0\ else\ 0$

Range: [0, $\infty$]

## Leaky ReLU
Function: $ReLU(x) = x\ if\ x\geq\ 0\ else\ \alpha x$

Range: [-$\infty$, $\infty$]

## Softmax
Function: $s_i = \frac{e^{z_i}}{\sum_{j=0}^{N-1}e^{z_j}}$

# Loss Function
Given previous content, we can calculate the prediction result using input data. However, the prediction results are far away from the correst results. To make our model perform better, we need ground truth output to guide the adjustment of our model parameters like weights and bias.

To measure the gap between model prediction and ground truth, we need Loss Functions.

# Training Process

## Optimizer

### RMSProp: Root Mean Square Propagation

## Learning Rate Scheduler

### Multistage Learning Rate

### Cosine Learning Rate

### Cyclical Learning Rate

## Initialization
