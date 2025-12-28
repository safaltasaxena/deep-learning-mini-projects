# ✍️ Handwritten Digit Recognition using ANN  

📌 A Deep Learning mini project demonstrating **Artificial Neural Networks (ANN)**
to recognize handwritten digits using the **MNIST dataset**.

---

## 📖 About  
This project focuses on building a **basic neural network from scratch concepts**
using **TensorFlow & Keras**.  
It starts with a **single-layer neural network (no hidden layer)** and gradually
improves performance by adding **hidden layers**, activation functions, and better
architectural choices.

---

## 📊 Dataset  
Dataset used: **MNIST Handwritten Digits**

- 🖼️ 28 × 28 grayscale images  
- 🔢 Digits from **0 to 9**  
- 🎯 Multi-class classification problem  

---

## ✨ Concepts Covered  
- 🧠 Artificial Neural Networks (ANN)  
- 🔢 Input flattening (28×28 → 784)  
- ⚡ Activation functions (Sigmoid, ReLU)  
- 📉 Loss function: Sparse Categorical Crossentropy  
- 🔁 Forward & Backpropagation  
- 🎯 Multi-class classification  
- 📊 Confusion matrix visualization  
- 📈 TensorBoard for model monitoring  

---

## 🛠️ Approach  

### 🔹 Data Preprocessing
- Normalize pixel values (0–255 → 0–1)
- Flatten image data for dense layers

### 🔹 Model 1: No Hidden Layer
- Single dense output layer
- Sigmoid activation
- Baseline accuracy

### 🔹 Model 2: With Hidden Layer
- One hidden layer with 100 neurons
- ReLU activation
- Improved accuracy

### 🔹 Model 3: Using `Flatten` Layer
- Avoids manual reshaping
- Cleaner and scalable architecture

---

## ▶️ Usage  
1. 📥 Clone the repository  
2. 📓 Open the notebook in **Google Colab** or **Jupyter Notebook**  
3. ▶️ Run all cells to:
   - Train neural networks  
   - Evaluate performance  
   - Visualize predictions and confusion matrix  

---

## 🧠 Model Details  
- Framework: **TensorFlow / Keras**  
- Optimizer: **Adam**  
- Loss Function: **Sparse Categorical Crossentropy**  
- Metrics: **Accuracy**

---

## 📈 Results  
- Accuracy improves after adding hidden layers  
- Neural network successfully recognizes handwritten digits  
- Confusion matrix helps visualize prediction performance  

---

## 📊 Visualization  
- Sample digit images  
- Confusion matrix heatmap  
- TensorBoard logs for training analysis  

---

🚀 *Part of my Deep Learning mini projects focused on building strong neural network fundamentals!*  
