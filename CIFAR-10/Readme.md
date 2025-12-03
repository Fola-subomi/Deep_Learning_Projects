# 📦 CIFAR-10 Image Classification (CNN)

This project uses a Convolutional Neural Network (CNN) to classify images from the **CIFAR-10 dataset** into 10 categories such as airplanes, cars, birds, cats, dogs, and more.
The goal is to build and train a deep learning model that correctly identifies real-world objects in small 32×32 color images.

---

## 🚀 Project Overview

The CIFAR-10 dataset contains:

* **60,000 images**
* **32×32 resolution**
* **3 color channels (RGB)**
* **10 distinct classes**

This project implements a **deep CNN with Batch Normalization, Dropout, and Data Augmentation** to achieve strong generalization and stable training.

---

## 🧠 Features

* Preprocessing of CIFAR-10 data
* Deep CNN architecture
* Batch Normalization for stable training
* Data Augmentation to improve robustness
* Evaluation with accuracy & loss curves
* Prediction on test images

---

## 🧰 Technologies Used

* Python
* TensorFlow / Keras
* NumPy
* Matplotlib

---

## 📂 Dataset

CIFAR-10 is automatically downloaded using:

```python
from tensorflow.keras.datasets import cifar10
```

Classes include:

```
airplane, automobile, bird, cat, deer, dog, frog, horse, ship, truck
```

---

## 🏗️ Model Architecture (Summary)

* Conv2D + BatchNorm
* Conv2D + BatchNorm
* MaxPooling + Dropout
* Conv2D + BatchNorm
* Conv2D + BatchNorm
* MaxPooling + Dropout
* Conv2D + BatchNorm
* Conv2D + BatchNorm
* MaxPooling + Dropout
* Dense(256) + Dropout
* Dense(10, softmax)

This architecture helps balance depth, stability, and generalization.

---

## 📈 Training

The model is trained using:

* **optimizer:** Adam
* **loss:** Sparse Categorical Crossentropy
* **epochs:** 30–50
* **data augmentation:** rotation, shifting, flipping
* **callbacks:** EarlyStopping + ReduceLROnPlateau


