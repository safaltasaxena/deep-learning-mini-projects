# 🌸 Data Augmentation in CNN – Image Classification  

📌 A Deep Learning mini project demonstrating **Data Augmentation**
to improve **CNN generalization** and reduce overfitting in image
classification tasks.

---

## 📖 About  
Deep Learning models often **overfit** when trained on limited image data.
This project demonstrates how **Data Augmentation** artificially increases
training data diversity, helping CNNs generalize better on unseen images.

The project compares:
- CNN without data augmentation (overfitting)
- CNN with data augmentation (improved performance)

---

## 📊 Dataset  
Dataset used: **Flower Photos Dataset**

- Classes:
  - Roses  
  - Daisy  
  - Dandelion  
  - Sunflowers  
  - Tulips  
- Images of varying sizes and orientations
- Real-world, unstructured image data

Dataset source: TensorFlow public dataset

---

## 🧹 Data Preprocessing
- Loaded images from disk using OpenCV & PIL
- Resized all images to **180 × 180**
- Converted images to NumPy arrays
- Normalized pixel values (0–255 → 0–1)
- Train–test split

---

## 🧠 Baseline CNN Model (Without Augmentation)

### Architecture:
- Conv2D → MaxPooling
- Conv2D → MaxPooling
- Conv2D → MaxPooling
- Flatten → Dense → Softmax

### Observation:
- High training accuracy
- Poor test accuracy
- Clear **overfitting**

---

## ⚠️ Problem Identified
The model memorizes training images instead of learning robust visual patterns,
leading to poor generalization on test data.

---

## 🛠️ Data Augmentation Techniques Used

The following transformations are applied **randomly during training**:

- 🔄 Random Flip (Horizontal)
- 🔍 Random Zoom
- 🔁 Random Rotation
- 🎨 Random Contrast

These transformations generate **new image variations** without increasing
dataset size.

---

## 🧠 CNN Model with Data Augmentation

### Updated Architecture:
- Data Augmentation Layer
- Conv2D → MaxPooling
- Conv2D → MaxPooling
- Conv2D → MaxPooling
- Dropout (Regularization)
- Flatten → Dense → Softmax

---

## 🛠️ Training Configuration
- Optimizer: **Adam**
- Loss Function: **Sparse Categorical Crossentropy**
- Metric: **Accuracy**
- Epochs:
  - Without augmentation: 10
  - With augmentation: 5

---

## 📈 Results Comparison

| Model | Training Accuracy | Test Accuracy |
|-----|------------------|---------------|
| Without Augmentation | Very High | Low |
| With Augmentation | Balanced | **Improved & Stable** |

Data augmentation significantly reduces overfitting and improves test
performance.

---

## ▶️ Usage
1. 📥 Clone the repository  
2. 📓 Open the notebook in **Google Colab** or **Jupyter Notebook**  
3. ▶️ Run all cells to:
   - Train CNN without augmentation  
   - Observe overfitting  
   - Apply data augmentation  
   - Train improved CNN model  

---

## 🧠 Key Learnings
- Why CNNs overfit on small datasets
- How data augmentation improves generalization
- Importance of image transformations in real-world CV tasks
- How augmentation works as implicit regularization

---

## 📌 Conclusion
Data Augmentation is a critical technique in computer vision.
By creating diverse training samples, CNNs learn more robust features
and perform better on unseen data.

---

🚀 *Part of my Deep Learning mini projects focused on building robust
computer vision models using CNNs.*
