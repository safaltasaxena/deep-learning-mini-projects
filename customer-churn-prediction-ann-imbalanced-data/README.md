# 📉 Customer Churn Prediction using ANN (Imbalanced Dataset Handling)

📌 A Deep Learning mini project that predicts **customer churn** using an
**Artificial Neural Network (ANN)** and explores **multiple techniques to handle
imbalanced datasets**.

---

## 📖 About
Customer churn prediction is a critical business problem where the goal is to
identify customers who are likely to leave a service.

This project builds an **ANN-based binary classification model** and goes beyond
basic training by addressing the **class imbalance problem**, which is common in
real-world churn datasets.

---

## 📊 Dataset
Dataset used: **Telco Customer Churn Dataset**

### Target Variable:
- **Churn**  
  - `1` → Customer churned  
  - `0` → Customer retained  

### Key Features:
- Customer tenure  
- Monthly charges  
- Total charges  
- Contract type  
- Payment method  
- Internet & phone services  
- Demographic information  

---

## 🧹 Data Preprocessing
- Dropped irrelevant features (e.g., customer ID)
- Converted numeric columns stored as strings
- Handled missing values
- Binary encoding for Yes/No features
- One-hot encoding for multi-class categorical features
- Feature scaling using **MinMaxScaler**

---

## 📊 Exploratory Data Analysis (EDA)
- Churn distribution by **tenure**
- Churn distribution by **monthly charges**
- Visualization of churn vs non-churn customers

---

## 🧠 Model Architecture (ANN)
- Input layer: 26 features
- Hidden Layer 1: Dense (20 neurons, ReLU)
- Hidden Layer 2: Dense (15 neurons, ReLU)
- Output Layer: Dense (1 neuron, Sigmoid)

---

## 🛠️ Training Configuration
- Optimizer: **Adam**
- Loss Function: **Binary Crossentropy**
- Metric: **Accuracy**
- Epochs: **100**

---

## 📈 Model Evaluation
- Accuracy
- Precision
- Recall
- F1-score
- Confusion Matrix visualization

Initial results show **poor recall for churned customers** due to class imbalance,
which motivates further techniques.

---

## ⚠️ Handling Imbalanced Dataset

The project implements **four different techniques** to improve churn prediction
performance:

---

### 1️⃣ Random Under-Sampling
- Reduces majority class samples
- Balances dataset by removing excess non-churn records
- Improves recall for minority class

---

### 2️⃣ Random Over-Sampling
- Duplicates minority class samples
- Maintains all majority samples
- Reduces bias toward majority class

---

### 3️⃣ SMOTE (Synthetic Minority Over-sampling Technique)
- Generates synthetic samples for minority class
- Preserves feature distribution
- Provides better generalization than simple oversampling

---

### 4️⃣ Ensemble Method with Under-Sampling
- Splits majority class into multiple batches
- Trains multiple ANN models
- Combines predictions using majority voting
- Produces the most stable and balanced results

---

## ▶️ Usage
1. 📥 Clone the repository  
2. 📓 Open the notebook in **Google Colab** or **Jupyter Notebook**  
3. ▶️ Run all cells to:
   - Preprocess data  
   - Train ANN model  
   - Evaluate baseline performance  
   - Apply imbalance handling techniques  
   - Compare results  

---

## 🧠 Key Learnings
- Why accuracy alone is misleading for imbalanced data
- Importance of recall & F1-score in churn prediction
- How different imbalance techniques affect ANN performance
- How to build production-ready churn models

---

## 📌 Conclusion
Handling imbalanced datasets is **critical** in churn prediction.
Applying resampling techniques and ensemble methods significantly improves
model performance and real-world usability.

---

🚀 *Part of my Deep Learning mini projects focused on solving real-world,
business-critical problems using neural networks.*
