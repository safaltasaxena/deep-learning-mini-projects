# 🌸 Flower Image Classification using Transfer Learning (MobileNetV2)

---

## 📌 Overview
This project demonstrates **image classification using Transfer Learning**
with a **pretrained MobileNetV2 model** from **TensorFlow Hub**.  
Instead of training a convolutional neural network from scratch, the model
reuses **ImageNet-trained features** and learns a lightweight classifier for
flower categories, resulting in **fast training and strong performance**.

---

## 📊 Dataset
**Flower Photos Dataset** (TensorFlow public dataset)

### Classes
- Roses  
- Daisy  
- Dandelion  
- Sunflowers  
- Tulips  

The dataset contains real-world images with varying backgrounds, lighting
conditions, and orientations.

---

## 🧹 Data Preprocessing
- Images loaded using **OpenCV and PIL**
- Resized to **224 × 224**
- Converted to NumPy arrays
- Pixel normalization (**0–255 → 0–1**)
- Train–test split

---

## 🏗️ Model Architecture
Input Image (224 × 224 × 3)
↓
MobileNetV2 Feature Extractor (Frozen)
↓
Feature Vector (1280)
↓
Dense Layer (5 Units)
↓
Output (Logits)

---

The pretrained **MobileNetV2** layers are frozen to preserve learned visual
features, while only the final classification layer is trained.

---

## ⚙️ Training Configuration
- **Optimizer:** Adam  
- **Loss Function:** Sparse Categorical Crossentropy (`from_logits=True`)  
- **Metric:** Accuracy  
- **Epochs:** 5  

Fewer epochs are sufficient due to pretrained feature reuse.

---

## 📈 Results

| Metric | Value |
|------|------|
| Training Accuracy | ~92% |
| Test Accuracy | ~86.8% |
| Epochs | 5 |

---

## 🧪 Evaluation
The model generalizes well on unseen test images and demonstrates significantly
reduced overfitting compared to training a CNN from scratch.

---

## ▶️ How to Run
1. Clone the repository  
2. Open the notebook in **Google Colab** or **Jupyter Notebook**  
3. Run all cells to train and evaluate the model  

---

## 🛠️ Tech Stack
- Python  
- TensorFlow / Keras  
- TensorFlow Hub  
- OpenCV  
- NumPy  
- Matplotlib  

---

## ⭐ Conclusion
This project highlights the effectiveness of **Transfer Learning** for image
classification tasks. By leveraging pretrained ImageNet features, the model
achieves strong accuracy with minimal training time, making it suitable for
practical computer vision applications.

---
🚀 Part of my Deep Learning & Computer Vision learning projects using
TensorFlow, TensorFlow Hub, and pretrained CNN architectures.
