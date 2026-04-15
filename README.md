🔢 Handwritten Digit Recognition using CNN
📌 Overview

This project implements a Convolutional Neural Network (CNN) to classify handwritten digits (0–9) using the MNIST dataset. The model learns image patterns and can be applied in real-world tasks such as digit recognition systems and automation.

📂 Dataset

The MNIST dataset is used and converted into CSV format for easier handling:

First column → Digit labels (0–9)
Remaining 784 columns → Pixel values (28×28 grayscale image)

Both training and testing datasets follow the same structure.

❓ Why CNN?

Traditional neural networks (MLPs) are not suitable for image data because they:

Require a large number of parameters
Increase computational cost
Are prone to overfitting

CNNs address these issues by:

Capturing spatial relationships in images
Using local feature extraction
Providing better accuracy and efficiency
🧠 CNN Architecture
Input → Conv(32) → BN → ReLU → Conv(32) → BN → ReLU → MaxPool →
Conv(64) → BN → ReLU → Conv(64) → BN → ReLU → MaxPool →
Dropout → Flatten → Dense(256) → Dropout → Dense(10) → Softmax → Output
⚙️ Key Components
1. Convolutional Layer
Applies filters to extract features
Detects edges, shapes, and patterns
2. Activation & Normalization
ReLU improves learning efficiency
Batch Normalization stabilizes training
3. Pooling Layer
Reduces spatial dimensions
Helps prevent overfitting
Types: Max Pooling, Average Pooling
4. Fully Connected Layer
Converts features into a vector
Performs final classification using Softmax
💾 Model Saving & Loading
HDF5 Format (.h5)

Stores complete model (architecture + weights + optimizer)

Save Model:

model.save("model.h5")

Load Model:

from keras.models import load_model
model = load_model("model.h5")
YAML Format

Stores only model architecture

Save:

model.to_yaml()

Load:

model = model_from_yaml(yaml_file)
model.load_weights("weights.h5")
🛠️ Technologies Used
Python
TensorFlow
Keras
NumPy
Matplotlib
h5py

▶️ How to Run
Clone the repository
git clone <repository-link>
Navigate to project folder
cd project-folder
Install dependencies
pip install -r requirements.txt
Run the model
python main.py
🎯 Applications
Digit recognition systems
Automated form processing
Bank cheque reading
OCR-based applications
