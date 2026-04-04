# 👁️ CNN XAI: Layer-Wise Visualization & Analysis of Neural Network Filters

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=for-the-badge&logo=python)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-FF6F00?style=for-the-badge&logo=tensorflow)
![Keras](https://img.shields.io/badge/Keras-API-D00000?style=for-the-badge&logo=keras)
![Accuracy](https://img.shields.io/badge/Accuracy-98.9%25-brightgreen?style=for-the-badge)

> **Demystifying the "Black Box" of Deep Learning.** > This repository provides a systematic, layer-by-layer visualization framework for Convolutional Neural Networks (CNNs). By explicitly bypassing complex regularization, it extracts and interprets the pure, organic mathematical features learned by the AI. 

---

## 🚀 The Vision: Why Explainable AI (XAI) Matters
Despite achieving a stellar **98.9% classification accuracy** on the MNIST dataset, CNNs are notoriously difficult to interpret. This project bridges the gap between high predictive power and model transparency. Instead of treating the model as a black box, this framework surgically extracts intermediate feature maps, isolates 3x3 kernel weights, and tracks the exact logic the network uses to classify data.

---

## ✨ Standout Features & Capabilities

### 🔍 1. Raw Filter Extraction (The Edge Detectors)
Extracts the physical 3x3 kernel matrices and maps them using diverging seismic colormaps.
*Witness how the network independently organizes positive and negative weights to create genuine geometric edge detectors.*
> 🖼️ **[PLACEHOLDER: Insert your `Figure 4.3` image of the Seismic Filter Grid here]**

### 🧠 2. Deep Feature Clustering (t-SNE)
Applies t-Distributed Stochastic Neighbor Embedding (t-SNE) to the deep flatten layer. 
*See how the AI mathematically unscrambles raw pixel data into 10 highly distinct conceptual "islands" representing each digit.*
> 🖼️ **[PLACEHOLDER: Insert your `Figure 4.9` image of the t-SNE scatter plot here]**

### 🕵️ 3. Real-Time Network Wiretapping
Intercepts the CNN in real-time as an image passes through the hidden layers.
*Watch the network slice the input data—isolating top horizontal strokes from descending diagonal lines.*

### 🌌 4. Filter Hallucination via Gradient Ascent
Synthesizes artificial input patterns starting from random statistical noise by maximizing specific filter activations. 
*Discover the naked, secluded morphological patterns that a specific neural filter "desires to see".*

---

## 🛠️ System Architecture

A streamlined, robust Sequential CNN optimized for 28x28x1 grayscale images:

| Layer Type | Configuration | Purpose |
| :--- | :--- | :--- |
| **Conv2D** | 32 filters, 3x3 kernel, ReLU | Extracts low-level geometric features (edges/curves). |
| **MaxPooling2D** | 2x2 pool, stride 2 | Spatial compression to retain highest activations. |
| **Conv2D** | 64 filters, 3x3 kernel, ReLU | Merges simple edges into complex loops/intersections. |
| **MaxPooling2D** | 2x2 pool | Further dimensionality reduction. |
| **Flatten** | 3D to 1D Vector | Prepares features for the classification backend. |
| **Dense** | 10 Nodes, Softmax | Outputs probability distribution for digits 0-9. |

---

## 📊 Error Logic: AI Doesn't Guess, It Calculates
Interpretability is best proven through failure states. An analysis of misclassifications proves the network makes highly rational errors based on its learned geometric edge detectors:
* **True 2 predicted as 7:** Triggered when the top curve is steep and the horizontal base stroke is drawn too weakly.
* **True 4 predicted as 9:** Triggered when the upper gap of a '4' is closed, perfectly mimicking the loop-and-line structure of a '9'.

---

## 💻 Quick Start & Pipeline

The end-to-end framework operates in 7 sequential phases:
1. **Data Prep:** Reshape to `(28, 28, 1)` and normalize bytes to `0.0 - 1.0`.
2. **Train Model:** Adam Optimizer & Sparse Categorical Crossentropy Loss.
3. **Wiretap Features:** Intercept Layer 1 activations via Keras sub-models.
4. **Extract Raw Filters:** Pull pure 3x3 tensors.
5. **Hallucination:** Gradient Ascent optimization on noise
