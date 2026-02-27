# Image Classification: Classical ML vs Deep Learning

This project presents a systematic benchmark on the **CIFAR-10** dataset, comparing classical machine learning methods with deep learning models.

The goal is to analyze how model capacity and representation learning affect image classification performance.

The overall workflow of CNN&MLP is applicable to most image datasets to accomplish image classification tasks in deep learning.

---

## Dataset

- **CIFAR-10**
- 10 object classes
- 32×32 RGB images
- You can use your own dataset instead.

---

## Project Pipeline

The project implements two parallel preprocessing pipelines to properly support different model families.

---

### 🔹 Classical ML Pipeline (for SVM)

- Image flattening to feature vectors  
- Feature standardization
- Optional dimensionality reduction via **PCA**   

This pipeline enables traditional machine learning methods to handle high-dimensional image data.

---

### 🔹 Deep Learning Pipeline (for MLP & CNN)

- Preserve original image structure (32×32×3)
- Dataset partitioning and preprocessing
- Using TensorFlow/Keras library(It will be better if you know how to use PyTorch since more convenient)  

The experiment was first run for a few epochs to confirm the number of network layers in the MLP and CNN.

---

## Models Implemented

### 1. Support Vector Machine (SVM)

- Implemented with sklearn 
- Integrated with preprocessing pipeline  
- Hyperparameter tuning via **GridSearchCV**  
- Serves as classical ML baseline  

---

### 2. Multi-Layer Perceptron (MLP)

- Fully connected architecture
- The MLP consists of **three fully connected hidden layers**, and the following hyperparameters were tuned:

**Architecture**
- `units_1` ∈ {256, 512}
- `units_2` ∈ {256, 512}
- `units_3` ∈ {256, 512}
- `activation` ∈ {"relu", "sigmoid", "tanh"} (shared across all hidden layers)

**Optimization**
- `optimizer` ∈ {"SGD", "Adam"}
- `learning_rate` ∈ {1e-3, 1e-4, 1e-5}

---

### 3. Convolutional Neural Network (CNN)
 
- Stacked Conv2D + pooling layers    
- The CNN contains **two convolutional blocks**, the following hyperparameters were tuned:

**Convolutional Layers**
- `filters_1` ∈ {32, 64, 128}
- `filters_2` ∈ {32, 64, 128}
- `kernel_size_1` ∈ {3, 5}
- `kernel_size_2` ∈ {3, 5}
- `activation` ∈ {"relu", "tanh", "sigmoid"} (shared across conv layers)
- `padding` ∈ {"same", "valid"} (shared across conv layers)

**Optimization**
- Optimizer: **Adam** (fixed)
- `learning_rate` ∈ {1e-3, 1e-4, 1e-5}

---

## Hyperparameter Tuning

- **GridSearchCV** used for classical models  
- **Keras Tuner** used for neural networks  
- Parameter sensitivity analysis performed  

---

## Evaluation Metrics

Models are evaluated using:

- Accuracy  
- Classification report  
- Confusion matrix  
- Visualization of training behavior  

---

Thanks to the other three members who contributed to this code.
