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
- Trained on flattened image inputs  

---

### 3. Convolutional Neural Network (CNN)
 
- Stacked Conv2D + pooling layers  
- End-to-end image classifier  
- Designed specifically for CIFAR-10  
- Includes training monitoring  

This model represents the primary deep learning approach in the project.

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
