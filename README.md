## CVPR Midterm Assignment - SVHN Classification with CNN

**📘 Course:** Computer Vision and Pattern Recognition (CVPR)  
**👤 Student Name:** Nurul Azam Bhuiyan  
**🆔 Student ID:** 23-50020-1  
**🏫 Section:** C  
**⚙️ Framework:** PyTorch  
**📂 Dataset:** SVHN (Street View House Numbers)

---

## 📌 Project Overview

This project presents a custom **Convolutional Neural Network (CNN)** for **multi-class image classification** using the **SVHN (Street View House Numbers)** dataset.

The main goal of this assignment is to compare the performance of:

- 🧱 a **baseline CNN**
- 🛡️ a **regularized CNN with Batch Normalization and Dropout**

The models are evaluated using multiple performance metrics, visualizations, and class-wise analysis to understand both **accuracy** and **generalization behavior**.

---

## 🗂️ Dataset

**SVHN (Street View House Numbers)** is a real-world image dataset containing cropped house-number digits collected from street-view images.

### ✨ Key Characteristics
- 🌈 Colored digit images
- 🏙️ Real-world background clutter
- ✍️ Different writing styles and scales
- 🌫️ Blur, lighting variation, and noise
- 🔢 10 classes (`0–9`)

### 📊 Dataset Split Used
- **Training images:** 65,932  
- **Validation images:** 7,325  
- **Test images:** 26,032  

### 🔗 Dataset Link
[SVHN Dataset](http://ufldl.stanford.edu/housenumbers/)

---

## 🎯 Project Objectives

- ✅ Build a custom CNN for multi-class image classification
- ✅ Compare performance **with and without Batch Normalization and Dropout**
- ✅ Evaluate the final model using:
  - Accuracy
  - Precision
  - Recall
  - F1 Score
  - Confusion Matrix
  - Per-class analysis
- ✅ Analyze overfitting and generalization behavior

---

## 🧪 Data Preprocessing and Augmentation

### 🏋️ Training Preprocessing
- Random crop with padding
- Small random rotation
- Color jitter
- Channel-wise normalization

### 🧾 Validation / Test Preprocessing
- No augmentation
- Channel-wise normalization only

This setup improves generalization during training while keeping validation and testing fair and consistent.

---

## 🏗️ Model Architectures

Two CNN variants were implemented:

### 1️⃣ Baseline CNN
A plain convolutional neural network without regularization.

### 2️⃣ BN + Dropout CNN
A regularized CNN that includes:
- 🧼 **Batch Normalization**
- 🎲 **Dropout**

These components help reduce overfitting and improve generalization performance.

---

## ⚙️ Hyperparameters

| Hyperparameter | Value |
|---|---:|
| Batch size | 128 |
| Evaluation batch size | 512 |
| Learning rate | 1e-3 |
| Epochs | 15 |
| Loss function | CrossEntropyLoss |
| Optimizer | Adam |
| Scheduler | ReduceLROnPlateau |

---

## 📈 Model Performance

### 🏆 Best Results

| Metric | Plain CNN | BN + Dropout CNN |
|---|---:|---:|
| Best Validation Accuracy | 0.9414 | 0.9461 |
| Test Accuracy | 0.9475 | 0.9516 |
| Weighted Precision | 0.9477 | 0.9520 |
| Weighted Recall | 0.9475 | 0.9516 |
| Weighted F1 Score | 0.9475 | 0.9516 |

### ⭐ Final Selected Model
The **BN + Dropout CNN** achieved the best validation and test performance and was selected as the final model.

---

## 📋 Evaluation Summary

The final model achieved:

- **🎯 Test Accuracy:** 95.16%
- **📌 Macro Precision:** 94.68%
- **📌 Macro Recall:** 94.91%
- **📌 Macro F1 Score:** 94.77%
- **🏅 Weighted Precision:** 95.20%
- **🏅 Weighted Recall:** 95.16%
- **🏅 Weighted F1 Score:** 95.16%

These results indicate strong overall classification performance and good class-wise behavior.

---

## 🔍 Per-Class Analysis

- **🌟 Best-performing class:** `4`
- **⚠️ Worst-performing class:** `8`

The confusion matrix and class-wise metrics show that most predictions fall correctly on the diagonal, while the remaining mistakes mostly occur between visually similar digits or low-quality blurred samples.

### 🔁 Top Confusing Class Pairs
- `3 → 9`
- `8 → 6`
- `7 → 1`
- `1 → 0`
- `1 → 7`

---

## 🖼️ Visualizations Included

This notebook includes:
- 🧷 Sample images from the dataset
- 📊 Class distribution chart
- 📉 Validation loss comparison
- 📈 Validation accuracy comparison
- 📚 Training vs validation curves
- 🧩 Confusion matrix
- 🧾 Normalized confusion matrix
- 📌 Per-class F1-score bar chart
- ❌ Misclassified sample visualization
- 🔎 Confusion-pair analysis

---

## 🧠 Overfitting and Generalization

The baseline CNN performed well but showed a **larger train-validation gap**, indicating stronger overfitting.

The **BN + Dropout CNN** reduced this gap and achieved better validation and test accuracy, showing stronger generalization.

---

## 💾 Saved Model Weights

The following model weights were saved:

- `plain_cnn.pth`
- `bnd_cnn.pth`

The saved regularized model was reloaded successfully and verified on the test set.

---

## 📁 Files

- `CNN_23_50020_1.ipynb` — main notebook
- `plain_cnn.pth` — baseline model weights
- `bnd_cnn.pth` — regularized model weights

---

## ✅ Conclusion

A custom CNN was successfully developed for **multi-class image classification** on the SVHN dataset.  
The model with **Batch Normalization and Dropout** outperformed the plain CNN and achieved strong final performance.

This project demonstrates that regularization significantly improves generalization and helps reduce overfitting in CNN-based image classification tasks.

---

## 🚀 Future Work

- Tune augmentation more carefully for SVHN
- Use a more effective learning-rate schedule
- Try deeper CNN architectures or residual connections
- Perform more detailed analysis of difficult confusion pairs

---

## 👨‍💻 Author

**Nurul Azam Bhuiyan**  
**Student ID:** 23-50020-1  
**Section:** P
