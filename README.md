# MNIST Autoencoders

This directory contains two Jupyter Notebooks that demonstrate how to build and train Autoencoders on the [MNIST dataset](https://www.tensorflow.org/datasets/catalog/mnist) using TensorFlow and Keras.

## Files

* **`Simple.ipynb`**: Implements a simple, shallow autoencoder. 
  * The encoder compresses the 784-pixel input image down to a 32-dimensional latent representation using a single `Dense` layer.
  * The decoder reconstructs the image back to 784 dimensions using another `Dense` layer with a sigmoid activation.
* **`Deepauto.ipynb`**: Implements a deep autoencoder.
  * The encoder consists of multiple stacked `Dense` layers (128 -> 64 -> 32 units) for a deeper, hierarchical compression.
  * The decoder mirrors this architecture (64 -> 128 -> 784 units) to generate the original image from the compressed representation.

## Overview

Both notebooks follow a similar workflow:
1. **Dataset Preparation**: Loading the MNIST dataset from `tensorflow_datasets`, normalizing the pixel values to a `[0, 1]` range, and flattening the 28x28 images into 784-dimensional vectors.
2. **Model Building**: Defining the encoder and decoder models using the Keras Functional API.
3. **Training**: Compiling the autoencoder model with the `Adam` optimizer and `binary_crossentropy` loss, and training it for 50 epochs.
4. **Visualization**: Displaying the original input images, their compressed latent representations, and the final decoded output to evaluate the model's performance visually.
