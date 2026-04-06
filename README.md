Handwritten Digit Recognition using CNN
Overview

This project builds a Convolutional Neural Network (CNN) model to classify handwritten digits from the MNIST dataset. The trained model can also be reused for digit recognition tasks in real-world applications.

Dataset Preparation

The MNIST dataset is preprocessed into a CSV format for easier handling.

The first column represents the digit labels (0–9).
The remaining 784 columns (28×28 pixels) represent grayscale pixel values of each image.

Both training and testing datasets follow this structure.

Why Convolutional Neural Networks?

Traditional fully connected neural networks (MLPs) are inefficient for image data because they require a very large number of parameters. This often leads to:

Increased computation time
Overfitting issues

CNNs solve this by leveraging spatial relationships in images. Instead of connecting every neuron, CNN layers focus on local regions, making them more efficient and accurate.

Key CNN Components

A typical CNN consists of the following layers:

1. Convolutional Layer
Applies filters (kernels) over input images
Extracts important features like edges and shapes
Output depth depends on number of filters
2. Activation & Normalization
Batch Normalization stabilizes training
Activation functions like ReLU improve learning efficiency
3. Pooling Layer
Reduces spatial dimensions
Helps in lowering computation and avoiding overfitting
Common types: Max Pooling, Average Pooling
4. Fully Connected Layer
Flattens feature maps into a vector
Used for final classification using Softmax
Model Architecture
Input → Conv(32) → BN → ReLU → Conv(32) → BN → ReLU → MaxPool →
Conv(64) → BN → ReLU → Conv(64) → BN → ReLU → MaxPool →
Dropout → Flatten → Dense(256) → Dropout → Dense(10) → Softmax → Output
Model Saving & Loading

The trained model is saved in different formats:

HDF5 Format (.h5)

Includes:

Model architecture
Weights
Training configuration
Optimizer state

Save:

model.save("model.h5")

Load:

from keras.models import load_model
model = load_model("model.h5")
YAML Format
Stores only the model structure (not weights)

Save:

model.to_yaml()

Load:

model = model_from_yaml(yaml_file)
model.load_weights("weights.h5")
Technologies Used
TensorFlow
Keras
NumPy
Matplotlib
h5py
Author
falguni sultane
