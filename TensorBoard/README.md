# 📊 TensorBoard – Neural Network Visualization & Debugging  

📌 A Deep Learning mini project demonstrating how to use **TensorBoard**
to visualize, monitor, and debug neural network training.

---

## 📖 About  
TensorBoard is a powerful visualization tool provided by TensorFlow that helps
understand what is happening **inside a neural network during training**.

This project builds on the **Handwritten Digit Recognition using ANN** project
and uses TensorBoard to visualize:
- Training loss
- Training accuracy
- Model computation graph

---

## ⚠️ Prerequisite (Important)  
Before running this notebook, you **must first run** the following project
present in the **same repository**:

📁 **`handwritten-digit-recognition-ann`**

This ensures:
- Model training is executed  
- Logs are generated correctly  

Without running that notebook first, TensorBoard will not display any data.

---

## ✨ Features  
- 🐞 Debugging neural networks  
- 📈 Visualizing loss and accuracy metrics  
- 🧠 Understanding model training behavior  
- 🔍 Inspecting the computation graph  

---

## 🛠️ Approach  
1. Train a neural network on the MNIST dataset  
2. Enable TensorBoard callback during model training  
3. Store logs inside a `logs/` directory  
4. Launch TensorBoard directly inside the notebook  
5. Analyze training metrics and model structure  

---

## ▶️ Usage  

### Step 1️⃣ Run ANN Notebook
- Open and run all cells in  
  **`handwritten-digit-recognition-ann.ipynb`**

---

### Step 2️⃣ Launch TensorBoard
Run the following commands inside this notebook:

```python
%load_ext tensorboard
%tensorboard --logdir logs/
