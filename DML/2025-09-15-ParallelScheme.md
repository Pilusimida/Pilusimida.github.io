---
layout: post
title: Introduction to Different Parallelism in DML
date: 2025-09-15
categories: [DML]
---
## Data Parallel(数据并行)
A batch of training data is divided into multiple packages. Each data package is feed into one individual computing cluster to generate gradients.

All-reduce is performed after all of computing clusters have generated their own gradients. The mean of sum gradients is used to update the parameter of the model. In this case, every computing cluster holds the same integral model. 

### FSDP: Fully Sharded Data Parallel

## Model Parallel(模型并行)
Compared to Data Parallel which preseve the integrity of model, Model Parallel divided models parameters into multiple parts in different ways.

The widely used strategies include: 
- **Pipeline Parallel**: models are divided by layers. Each device only holds some of the layers.
- **Tensor Parallel**: weights in one layers are distributed into different devices to calcualte the partial activations separately.
- **Expert Parallel**: in Mixture of Expert(MoE) architecture, divide different experts into different devices to do the computation simutaneously.
- **Seuence Parallel**: for long sequence model, sequences are often split into smaller chunks. Each device only accounts for calculation of each chunk. 

### Pipeline Parallel(流水线并行)
When the whole modes is too large to be stores in one single devices, we cut the weights layer by layer and distribute them into different devices.

Each device receives the activations from one device holding results from previous layer and transport results to another device holding next layer parameters.

### Tensor Parallel/Weight Sharded(权重分片)
Sometimes, weights in one single layer are too large to fit into one single GPU. In this case, weighets need to be distributed into different devices.

During the forwarding process, multiple devices calculate their parts of activations simutaneously. Then the computed results require synchronization.

### Expert Parallel

### Sequence Parallel

