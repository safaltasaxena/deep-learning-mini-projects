# 🧠 Word Embedding using Keras – Sentiment Classification

📌 A simple Deep Learning mini project demonstrating how **word embeddings**
are learned and used for **binary sentiment classification** on text data.

---

## 📖 About

Understanding text numerically is a key challenge in NLP. This project shows how:

* Text is converted into numeric form using **one-hot encoding**
* Sequences are standardized using **padding**
* A neural network learns **word embeddings automatically**

The goal is to classify short reviews as:

* 👍 Positive
* 👎 Negative

---

## 📊 Dataset

A small custom dataset of **10 text samples**:

### Positive Reviews:

* "nice food"
* "amazing resturant"
* "too good"
* "just loved it"
* "will go again"

### Negative Reviews:

* "horrible food"
* "never go there"
* "poor service"
* "poor quality"
* "needs improvement"

Labels:

* `1 → Positive`
* `0 → Negative`

---

## 🧹 Data Preprocessing

### 1️⃣ One-Hot Encoding

Each word is mapped to an integer index using:

```python
one_hot(text, vocab_size)
```

* Vocabulary size: **30**
* Words are assigned **random indices**

---

### 2️⃣ Sequence Padding

Since sentences have different lengths:

```python
pad_sequences(sequences, maxlen=3, padding='post')
```

* All sequences are converted to length **3**
* Padding added at the **end**

---

## 🧠 Model Architecture

A simple neural network using Keras:

* **Input Layer**
* **Embedding Layer**

  * Converts word indices → dense vectors
* **Flatten Layer**
* **Dense Layer (Sigmoid)**

### Architecture Flow:

```
Input → Embedding → Flatten → Dense → Output
```

---

## ⚙️ Model Configuration

* Optimizer: **Adam**
* Loss Function: **Binary Crossentropy**
* Metric: **Accuracy**
* Epochs: **50**

---

## 🧪 Training

Model is trained on the padded dataset:

```python
model.fit(X, y, epochs=50, verbose=0)
```

---

## 📈 Evaluation

```python
loss, accuracy = model.evaluate(X, y)
```

Since the dataset is very small:

* Model achieves **high accuracy**
* But may **overfit easily**

---

## 🔍 Understanding Embeddings

After training, embeddings are extracted:

```python
weights = model.get_layer('embeddings').get_weights()[0]
```

* `weights` shape → `(vocab_size, embedding_dim)`
* Each row represents a **word vector**

Example:

```python
weights[8]
weights[20]
```

These vectors capture **semantic meaning** learned during training.

---

## 🧠 Key Learnings

* How text is converted into numeric format
* Importance of **padding** in NLP models
* Role of **Embedding layers** in learning word representations
* Difference between:

  * One-hot encoding (sparse)
  * Embeddings (dense & meaningful)
* Basics of **sentiment classification**

---

## ⚠️ Limitations

* Very small dataset → not realistic
* One-hot encoding assigns **random indices**
* Model may **overfit**
* No train-test split

---

## 🚀 Future Improvements

* Use larger datasets (e.g., IMDB)
* Apply **pretrained embeddings** (Word2Vec, GloVe)
* Add:

  * LSTM / GRU
  * Dropout (regularization)
* Perform proper **train-test split**

---

## ▶️ Usage

1. 📥 Install dependencies:

```bash
pip install tensorflow numpy
```

2. ▶️ Run the script in:

* Jupyter Notebook
* Google Colab

3. 📊 Observe:

* Encoded sequences
* Model summary
* Accuracy
* Learned embeddings

---

## 📌 Conclusion

This project demonstrates the **foundation of NLP in Deep Learning**.

Instead of manually designing features, the model **learns word meanings automatically**
through embeddings, making it a powerful approach for text-based tasks.

---

🚀 *Part of my Deep Learning journey exploring NLP fundamentals and embeddings.*
