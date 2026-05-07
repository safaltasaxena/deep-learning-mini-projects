# 🧠 Word2Vec using Gensim – Amazon Reviews

📌 A Deep Learning / NLP mini project demonstrating how to train a **Word2Vec model**
on real-world data and explore **semantic relationships between words**.

---

## 📖 About

This project focuses on learning **word representations (embeddings)** using the
Word2Vec algorithm on a large dataset of Amazon product reviews.

Instead of manually defining relationships between words, the model **learns meaning from context**.

Key ideas:

* Words used in similar contexts → similar vectors
* Semantic relationships can be discovered mathematically

---

## 📊 Dataset

Dataset used: **Amazon Reviews – Cell Phones & Accessories**

* Source: Stanford SNAP dataset
* Format: JSON (line-by-line)
* Contains:

  * Review text
  * Ratings
  * Metadata

Example:

```python
df.reviewText[0]
```

---

## 🧹 Data Preprocessing

### 1️⃣ Text Cleaning & Tokenization

Using Gensim:

```python
gensim.utils.simple_preprocess(text)
```

* Converts text → lowercase
* Removes punctuation
* Tokenizes into words

---

### 2️⃣ Apply on Full Dataset

```python
review_text = df.reviewText.apply(gensim.utils.simple_preprocess)
```

Now each review becomes:

```
["this", "product", "is", "good"]
```

---

## 🧠 Word2Vec Model

### Model Initialization:

```python
model = gensim.models.Word2Vec(
    window=10,
    min_count=2,
    workers=4,
)
```

### Parameters Explained:

* **window=10** → context size (words before & after)
* **min_count=2** → ignore rare words
* **workers=4** → parallel processing

---

## ⚙️ Training Process

### 1️⃣ Build Vocabulary:

```python
model.build_vocab(review_text)
```

### 2️⃣ Train Model:

```python
model.train(
    review_text,
    total_examples=model.corpus_count,
    epochs=model.epochs
)
```

---

## 💾 Save Model

```python
model.save("word2vec.model")
```

---

## 🔍 Exploring Word Embeddings

### 🔹 Similar Words

```python
model.wv.most_similar("bad")
```

👉 Finds words with similar meaning to **"bad"**

---

### 🔹 Word Similarity

```python
model.wv.similarity(w1="cheap", w2="inexpensive")
```

👉 High similarity → similar meaning

```python
model.wv.similarity(w1="great", w2="expensive")
```

👉 Lower similarity → different meaning

---

## 📈 What the Model Learns

* Semantic relationships
* Contextual similarity
* Hidden linguistic patterns

Example:

* "cheap" ≈ "inexpensive"
* "bad" ≈ "terrible"

---

## 🧠 Key Learnings

* How Word2Vec learns embeddings from raw text
* Importance of **context window**
* Difference between:

  * One-hot encoding ❌
  * Word embeddings ✅
* How to measure:

  * Word similarity
  * Semantic closeness

---

## ⚠️ Common Issues

* Typo in installation:

```bash
pip install python-levenshtein
```

(not `pyhton-levenshtein` ❌)

* Large dataset → needs time & RAM
* Rare words ignored due to `min_count`

---

## 🚀 Future Improvements

* Use:

  * CBOW vs Skip-gram comparison
* Visualize embeddings (t-SNE)
* Try pretrained models (Google News vectors)
* Build downstream tasks:

  * Sentiment classification
  * Recommendation systems

---

## ▶️ Usage

1. 📥 Install dependencies:

```bash
pip install gensim pandas python-levenshtein
```

2. 📂 Upload dataset in Colab:

```python
from google.colab import files
files.upload()
```

3. ▶️ Run all cells to:

* Preprocess text
* Train Word2Vec
* Explore similarities

---

## 📌 Conclusion

This project shows how machines can **understand language mathematically**.

Word2Vec transforms words into vectors where:

* Distance = meaning
* Similar words → closer in space

This is a foundational concept behind modern NLP systems.

---

🚀 *Part of my NLP journey exploring word embeddings and representation learning.*
