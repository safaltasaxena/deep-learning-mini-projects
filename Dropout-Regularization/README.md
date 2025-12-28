# 🎯 Dropout Regularization in ANN – Handling Overfitting  

📌 A Deep Learning mini project demonstrating **overfitting in neural networks**
and how **Dropout Regularization** helps improve generalization and test accuracy.

---

## 📖 About  
Overfitting is a common problem in Deep Learning where a model performs extremely
well on training data but fails to generalize to unseen data.

This project:
- First **intentionally overfits** an ANN
- Then applies **Dropout Regularization**
- Shows how dropout improves real-world performance

---

## 📊 Dataset  
Dataset used: **Sonar Dataset**

- 60 numerical input features  
- Binary classification:
  - `1` → Mine  
  - `0` → Rock  

This dataset is small and noisy, making it ideal for demonstrating overfitting.

---

## 🧹 Data Preprocessing
- Checked for missing values
- Separated features and target
- Converted categorical target into numeric form
- Train–test split (75% train, 25% test)

---

## 🧠 Baseline ANN Model (Overfitting Case)

### Architecture:
- Dense (60 neurons, ReLU)
- Dense (30 neurons, ReLU)
- Dense (15 neurons, ReLU)
- Dense (1 neuron, Sigmoid)

### Observations:
- Training accuracy ≈ **100%**
- Test accuracy ≈ **73%**
- Clear sign of **overfitting**

---

## ⚠️ Problem Identified
The model memorizes training data instead of learning general patterns,
leading to poor performance on unseen data.

---

## 🛠️ Dropout Regularization Applied

### Updated Architecture:
- Dense (60 neurons, ReLU)
- **Dropout (0.5)**
- Dense (30 neurons, ReLU)
- **Dropout (0.5)**
- Dense (15 neurons, ReLU)
- **Dropout (0.5)**
- Dense (1 neuron, Sigmoid)

Dropout randomly disables neurons during training, forcing the network
to learn robust features instead of memorizing data.

---

## 📈 Results Comparison

| Model Type | Training Accuracy | Test Accuracy |
|----------|------------------|---------------|
| Without Dropout | ~100% | ~73% |
| With Dropout | ~91% | **Improved & Stable** |

- Reduced overfitting  
- Better generalization  
- More reliable predictions  

---

## 📊 Evaluation Metrics
- Accuracy
- Precision
- Recall
- F1-score
- Confusion Matrix

---

## ▶️ Usage
1. 📥 Clone the repository  
2. 📓 Open the notebook in **Google Colab** or **Jupyter Notebook**  
3. ▶️ Run all cells to:
   - Train ANN without dropout  
   - Observe overfitting  
   - Apply dropout regularization  
   - Compare results  

---

## 🧠 Key Learnings
- Why neural networks overfit
- How dropout prevents co-adaptation of neurons
- Why training accuracy alone is misleading
- Importance of regularization in Deep Learning

---

## 📌 Conclusion
Dropout Regularization is a powerful technique to prevent overfitting in
neural networks.  
This project clearly demonstrates how applying dropout leads to **better
generalization and more trustworthy models**.

---

🚀 *Part of my Deep Learning mini projects focused on building robust and
generalizable neural networks.*
