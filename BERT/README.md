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
