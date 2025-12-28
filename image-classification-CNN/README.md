# 🖼️ Image Classification using CNN (CIFAR-10)

📌 A Deep Learning mini project demonstrating **image classification**
using **Convolutional Neural Networks (CNNs)** and comparing performance
with a traditional **Artificial Neural Network (ANN)**.

---

## 📖 About
Image data contains spatial patterns that traditional ANNs fail to capture
efficiently.  
This project highlights **why CNNs outperform ANNs for image classification**
by training both models on the **CIFAR-10 dataset** and comparing results.

---

## 📊 Dataset
Dataset used: **CIFAR-10**

- 🖼️ 32 × 32 RGB images  
- 🎯 10 classes:
  - airplane, automobile, bird, cat, deer  
  - dog, frog, horse, ship, truck  

---

## 🧹 Data Preprocessing
- Normalized pixel values (0–255 → 0–1)
- Reshaped labels into 1D format
- Visualized sample images with class labels

---

## 🧠 Model 1: Artificial Neural Network (ANN)

### Architecture:
- Flatten layer
- Dense (3000 neurons, ReLU)
- Dense (1000 neurons, ReLU)
- Dense (10 neurons, Sigmoid)

### Observations:
- Treats images as flat vectors
- Loses spatial information
- Lower classification performance on images

---

## 🧠 Model 2: Convolutional Neural Network (CNN)

### Architecture:
- Conv2D (32 filters, 3×3, ReLU)
- MaxPooling (2×2)
- Conv2D (64 filters, 3×3, ReLU)
- MaxPooling (2×2)
- Flatten
- Dense (64 neurons, ReLU)
- Dense (10 neurons, Softmax)

---

## 🛠️ Training Configuration
- Optimizer: **Adam**
- Loss Function: **Sparse Categorical Crossentropy**
- Metrics: **Accuracy**
- Epochs:
  - ANN: 5
  - CNN: 10

---

## 📈 Results & Comparison

| Model | Accuracy | Notes |
|------|---------|-------|
| ANN | Lower | Fails to capture spatial patterns |
| CNN | Higher | Learns spatial features effectively |

CNN significantly outperforms ANN due to its ability to learn **edges, textures,
and spatial hierarchies**.

---

## 📊 Evaluation
- Accuracy
- Classification report
- Confusion matrix (optional)
- Visual prediction inspection

---

## ▶️ Usage
1. 📥 Clone the repository  
2. 📓 Open the notebook in **Google Colab** or **Jupyter Notebook**  
3. ▶️ Run all cells to:
   - Train ANN model  
   - Evaluate ANN performance  
   - Train CNN model  
   - Compare results  

---

## 🧠 Key Learnings
- Why CNNs are superior for image data
- Difference between ANN and CNN architectures
- Role of convolution and pooling layers
- Importance of preserving spatial information

---

## 📌 Conclusion
Convolutional Neural Networks are essential for image classification tasks.
This project clearly demonstrates the **limitations of ANNs** and the
**effectiveness of CNNs** on real-world image data.

---

🚀 *Part of my Deep Learning mini projects focused on computer vision and
convolutional neural networks.*
