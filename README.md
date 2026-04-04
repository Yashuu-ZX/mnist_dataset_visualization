# Layer-Wise Visualization and Analysis of CNN Filters Using MNIST

## 📌 Overview
This repository contains the implementation of a systematic, layer-by-layer visualization framework for Convolutional Neural Networks (CNNs). By explicitly avoiding complex regularization techniques like Batch Normalization and Dropout, this project maintains the purity of learned filter weights. The resulting model achieves 98.9% classification accuracy on the MNIST dataset while effectively demystifying the "black-box" nature of deep learning through raw tensor extraction and geometric interpretation.

## 🚀 Key Features
- **Raw Filter Visualization:** Extracts physical 3x3 kernel weights and plots them using diverging seismic colormaps to expose organically learned geometric edge detectors.
- **Intermediate Feature Maps (Wiretapping):** Intercepts network layers in real-time to visualize how the model conceptually slices and extracts features from input data (e.g., isolating horizontal strokes or diagonal lines).
- **Deep Feature Clustering (t-SNE):** Applies t-Distributed Stochastic Neighbor Embedding to the deep flatten layer, illustrating how the network mathematically isolates the 10 digits into distinct conceptual "islands".
- **Filter Hallucination (Gradient Ascent):** Synthesizes artificial input patterns from random statistical noise through gradient ascent to discover the exact morphological structures a specific filter "desires to see".
- **Comprehensive Diagnostics:** Generates class-wise heatmaps tracking Precision, Recall, and F1-Scores alongside detailed misclassification error analysis to prove the network's logical (rather than random) failure states.

## 🛠️ Tech Stack
- **Language:** Python
- **Deep Learning:** TensorFlow, Keras API
- **Data Manipulation:** NumPy, Pandas
- **Visualization:** Matplotlib, Seaborn
- **Machine Learning Utilities:** Scikit-learn

## 🧠 Model Architecture
A streamlined, feed-forward Sequential CNN tailored for 28x28x1 grayscale images:
1. **Conv2D** (32 filters, 3x3 kernel, ReLU activation)
2. **MaxPooling2D** (2x2 pool size, stride 2)
3. **Conv2D** (64 filters, 3x3 kernel, ReLU activation)
4. **MaxPooling2D** (2x2 pool size)
5. **Flatten** (Converts 3D multidimensional tensors into a 1D vector)
6. **Dense Output** (10 nodes corresponding to digits 0-9, Softmax activation)

## ⚙️ The 7-Step Execution Pipeline
1. **Data Preprocessing:** Reshape the MNIST dataset to (28, 28, 1) and normalize raw pixel bytes to 32-bit floats scaled between 0.0 and 1.0.
2. **CNN Training:** Compile using the Adam optimizer and Sparse Categorical Crossentropy loss
