# 🧠 BERT NLP Project – Spam vs Ham Email Classification

📌 A Deep Learning / NLP mini project demonstrating how to use **BERT (Bidirectional Encoder Representations from Transformers)** to classify emails as **Spam or Not Spam (Ham)**.

---

## 📖 About

This project uses a pretrained BERT model from TensorFlow Hub to perform text classification.

Instead of training from scratch, we leverage **transfer learning** to understand context and meaning in emails.

Key ideas:

* Use pretrained language models (BERT)
* Fine-tune for classification
* Capture contextual meaning of words

---

## 📊 Dataset

Dataset used: **Spam Email Dataset (Kaggle)**

* Contains:

  * `Category` → spam / ham
  * `Message` → email text

Example:

```python
df.head()
```

---

## ⚖️ Handling Class Imbalance

Original distribution:

* Ham → 4825
* Spam → 747

👉 Dataset is imbalanced

### ✅ Solution: Downsampling

```python
df_ham_downsampled = df_ham.sample(df_spam.shape[0])
df_balanced = pd.concat([df_ham_downsampled, df_spam])
```

Balanced dataset:

```
spam = 747
ham  = 747
```

---

## 🧹 Data Preprocessing

### 1️⃣ Label Encoding

```python
df_balanced['spam'] = df_balanced['Category'].apply(
    lambda x: 1 if x == 'spam' else 0
)
```

---

### 2️⃣ Train-Test Split

```python
from sklearn.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(
    df_balanced['Message'],
    df_balanced['spam'],
    stratify=df_balanced['spam']
)
```

---

## 🤖 BERT Model (TF Hub)

```python
bert_preprocess = hub.KerasLayer(
    "https://tfhub.dev/tensorflow/bert_en_uncased_preprocess/3"
)

bert_encoder = hub.KerasLayer(
    "https://tfhub.dev/tensorflow/bert_en_uncased_L-12_H-768_A-12/4"
)
```

---

## 🧠 Model Architecture

```python
text_input = tf.keras.layers.Input(shape=(), dtype=tf.string, name='text')

preprocessed_text = bert_preprocess(text_input)
outputs = bert_encoder(preprocessed_text)

l = tf.keras.layers.Dropout(0.1)(outputs['pooled_output'])
l = tf.keras.layers.Dense(1, activation='sigmoid')(l)

model = tf.keras.Model(inputs=text_input, outputs=l)
```

---

## ⚙️ Compilation

```python
model.compile(
    optimizer='adam',
    loss='binary_crossentropy',
    metrics=['accuracy', 'Precision', 'Recall']
)
```

---

## 🚀 Training

```python
model.fit(X_train, y_train, epochs=10)
```

---

## 📈 Evaluation

```python
model.evaluate(X_test, y_test)
```

---

## 🔍 Predictions

```python
model.predict([
    "Win $5000 now!",
    "Hey, are you coming tomorrow?"
])
```

---

## 🧪 Embedding Exploration

```python
get_sentence_embeding([
    "banana",
    "grapes"
])
```

👉 Use cosine similarity to compare semantic meaning.

---

## 🧠 Key Learnings

* How BERT handles NLP tasks
* Importance of transfer learning
* Contextual embeddings vs traditional NLP
* Handling class imbalance

---

## ⚠️ Common Issues

### ❌ TensorFlow / TensorFlow Text mismatch

```bash
pip install tensorflow==2.19.0 tensorflow-text==2.19.0 tensorflow-hub
```

👉 Restart runtime after installation.

---

### ❌ KerasTensor Error

Cause:

* Missing or incompatible `tensorflow-text`

Fix:

```python
import tensorflow_text as text
```

---

## 🚀 Future Improvements

* Fine-tune BERT (`trainable=True`)
* Try Hugging Face Transformers
* Use larger datasets
* Deploy model as API

---

## ▶️ Usage

### 1️⃣ Install dependencies

```bash
pip install tensorflow tensorflow-text tensorflow-hub pandas scikit-learn
```

---

### 2️⃣ Upload dataset (Colab)

```python
from google.colab import files
files.upload()
```

---

### 3️⃣ Run notebook

* Load data
* Train model
* Evaluate performance

---

## 📌 Conclusion

This project demonstrates how modern NLP models like BERT can understand language context and perform classification effectively.

👉 BERT learns meaning automatically without manual feature engineering.

---

🚀 *Part of my NLP journey exploring transformers and real-world text classification.*
