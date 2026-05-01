# Deep Learning Labs - Autoencoders

This directory contains Jupyter Notebooks that demonstrate how to build and train different types of Autoencoders using TensorFlow and Keras. The datasets explored include MNIST and Fashion MNIST.

## Files

* **`Simple.ipynb`**: Implements a simple, shallow autoencoder on the MNIST dataset. 
  * The encoder compresses the 784-pixel input image down to a 32-dimensional latent representation using a single `Dense` layer.
  * The decoder reconstructs the image back to 784 dimensions using another `Dense` layer with a sigmoid activation.
* **`Deepauto.ipynb`**: Implements a deep autoencoder on the MNIST dataset.
  * The encoder consists of multiple stacked `Dense` layers (128 -> 64 -> 32 units) for a deeper, hierarchical compression.
  * The decoder mirrors this architecture (64 -> 128 -> 784 units) to generate the original image from the compressed representation.
* **`CNN.ipynb`**: Implements a Convolutional Autoencoder on the Fashion MNIST dataset.
  * The encoder uses `Conv2D` and `MaxPooling2D` layers to extract spatial features and contract the image dimensions.
  * The bottleneck extracts dense features while a specific layer visualizes the encoded representation.
  * The decoder upsamples back to the original image dimensions using `Conv2D` and `UpSampling2D` layers.

## Overview

The notebooks generally follow a similar structured workflow:
1. **Dataset Preparation**: Loading the dataset (MNIST or Fashion MNIST) from `tensorflow_datasets` and normalizing the pixel values to a `[0, 1]` range. Dense models flatten the 2D images into vectors, while the convolutional model preserves the 2D spatial structure.
2. **Model Building**: Defining the encoder and decoder models using the Keras Functional API.
3. **Training**: Compiling the autoencoder models with the `Adam` optimizer and `binary_crossentropy` loss.
4. **Visualization**: Displaying the original input images, their compressed latent representations, and the final decoded outputs to visually evaluate the models' reconstruction performance.
