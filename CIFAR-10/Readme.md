# 📦 CIFAR-10 Image Classification Using Pretrained EfficientNet

This project applies **EfficientNet**, a cutting-edge convolutional neural network pretrained on ImageNet, to classify images from the **CIFAR-10 dataset**.
Instead of building a CNN from scratch, this approach uses **transfer learning** to achieve significantly better accuracy with fewer training steps.

---

## 🚀 Project Overview

The CIFAR-10 dataset contains:

* **60,000 color images**
* **32×32 resolution**
* **10 classes** representing common object categories
  *(airplane, automobile, bird, cat, deer, dog, frog, horse, ship, truck)*

EfficientNet provides a powerful feature extractor, so the model can learn high-level patterns even though CIFAR-10 images are small.

---

## 🧠 Features

### 🔹 Transfer Learning with EfficientNet

* Uses **EfficientNetB0/B1/B2** pretrained on ImageNet
* Base model has *frozen* layers initially
* A new classification head is added on top
* Later, some layers may be unfrozen for fine-tuning

### 🔹 Data Preprocessing

* Images are **resized** to EfficientNet input size (224×224 or similar)
* Pixel values normalized to [0, 1]
* Labels converted to integer class IDs

### 🔹 Data Augmentation

* Random flipping
* Random rotation
* Random zooming
* Random shifting

This improves robustness and reduces overfitting.

### 🔹 Evaluation Tools

* Accuracy and loss curves
* Predictions on test samples

---

## 🧰 Technologies Used

* Python
* TensorFlow / Keras
* NumPy
* Matplotlib

---

## 📂 Dataset

The CIFAR-10 dataset is loaded using:

```python
from tensorflow.keras.datasets import cifar10
```

It automatically downloads the data with images and labels ready to use.

Classes include:

```
airplane, automobile, bird, cat, deer, dog, frog, horse, ship, truck
```

## 📈 Training

The model is trained with:

* **optimizer:** Adam
* **loss:** Sparse Categorical Crossentropy
* **epochs:** 20–40 cumulative (often enough with pretrained models)
* **callbacks:**

  * EarlyStopping
  * ReduceLROnPlateau
  * ModelCheckpoint

### Training Strategy

#### **Phase 1: Frozen Base**

* The EfficientNet layers are frozen
* Only the custom classification layers are trained
* This stabilizes learning and prevents large weight changes

#### **Phase 2: Fine-Tuning**

* Unfreeze a few top EfficientNet layers
* Train with a very low learning rate
* Boosts accuracy significantly on CIFAR-10

---

## 📊 Evaluation

During and after training, you evaluate:

* Training vs validation accuracy
* Training vs validation loss
* Final test accuracy
* Confusion matrix
* Visualization of predictions

---

## 📜 Summary

Using **EfficientNet with transfer learning** provides:

* Higher accuracy than training a CNN from scratch
* Faster convergence
* Less need for a massive architecture
* Better generalization even with small images
* More stability thanks to pretrained ImageNet weights

This makes it ideal for CIFAR-10 experiments and showcases the power of transfer learning in modern image classification.
