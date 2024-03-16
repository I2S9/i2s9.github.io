---
title: Fashion Class Classification
publishDate: 2024-02-21 00:00:00
img: /assets/fashion-class.png
img_alt: Fashion Class Classification
description: |
  Fashion Class Classification based on convolutional neural network & deep learning
tags:
  - Data
  - CNN
  - Machine learning
---

<p align="justify">
 The fashion industry is undergoing a dramatic transformation by adopting new computer vision and ML and deep learning techniques. We're going to use the Fashion MNIST data that contains images like dress, bags and shoes We want to build a model (based on deep learning & machine learning model) that look at an image and tell us what type of clothes. We can do target marketing to specific customer 
</p>

<p align="justify">
Objective: build a classifier, build a kind of a deep learning network that can look at these images and can tell us the category of clothes.
</p>

##### Our Fashion Dataset

Fashion dataset contains 28x28 greyscale image with values ranging from 0-255

'0' represents black and '255' represents white

Each image is represented by a row with 784 (i.e 28x28) values
Artificial Neural Network basics

The neuron collects signals from input channels named dendrites, processes information in its nucleus, and then generates an output in a long thin branch called the axon.

Human learning occurs adaptively by varying the bond strength between these neurons.

Convolutional neural network feature detector

Convolutions use a kernel matrix to scan a given image and apply a filter to obtain a certain effect.

An image Kernel is a matrix used to apply effects such as blurring and sharpening.

Kernels are used in machine learning for feature extraction to select most important pixels of an image.

Convolution preserves the spatial relationship between pixels.


##### Convolutional neural network - RELU

RELU layers are used to add non-linearity in the feature map

It also enhances the sparsity or how scattered the feature map is

##### Convolutional neural network - maxpolling/flattening

Pooling or down sampling layers are placed after convolutional layers to reduce feature map dimensionality

This improves the computational efficiency while preserving the features

Pooling helps the model to generalize by avoiding overfitting. If one of the pixel is shifted, the pooled feature map will still be the same

Max pooling works by retaining the maximum feature response within a given sample size in a feature map

#### References 

