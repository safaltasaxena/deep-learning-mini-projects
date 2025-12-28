# ⚡ GPU Benchmarking using Artificial Neural Networks (ANN)

📌 A Deep Learning mini project that demonstrates **CPU vs GPU performance benchmarking**
by training an **Artificial Neural Network (ANN)** on an image classification task.

---

## 📖 About
Deep Learning models involve heavy matrix computations, making **hardware choice**
crucial for performance.  
This project benchmarks **training time on CPU vs GPU** using the same ANN architecture
to clearly show the speed advantage of GPUs.

The experiment is conducted using **TensorFlow & Keras** on the **CIFAR-10 dataset**.

---

## 📊 Dataset
**CIFAR-10 Dataset**

- 🖼️ 32 × 32 RGB images  
- 🎯 10 image classes:
  - airplane, automobile, bird, cat, deer  
  - dog, frog, horse, ship, truck  

---

## ✨ Features
- 🧠 Image classification using ANN  
- ⚡ GPU vs CPU performance comparison  
- ⏱️ Training time benchmarking  
- 🧩 TensorFlow device placement  
- 📊 Model evaluation and prediction  

---

## 🧰 Preprocessing
- Scale pixel values from **0–255 → 0–1**
- One-hot encode class labels
- Flatten image data for dense layers

---

## 🏗️ Model Architecture
- **Input Layer:** Flatten (32 × 32 × 3 → 3072)
- **Hidden Layer 1:** Dense (3000 neurons, ReLU)
- **Hidden Layer 2:** Dense (1000 neurons, ReLU)
- **Output Layer:** Dense (10 neurons, Sigmoid)

---

## 🛠️ Training Configuration
- Optimizer: **SGD**
- Loss Function: **Categorical Crossentropy**
- Metric: **Accuracy**
- Epochs: **50** (for training)
- Epochs: **1** (for benchmarking)

---

## ▶️ Usage

### 1️⃣ Check Hardware Support
```python
tf.config.experimental.list_physical_devices()
tf.test.is_built_with_cuda()
