# 🔁 Recurrent Neural Networks (RNN) – Conceptual Understanding

## 📌 Overview
This repository contains concise learning notes on **Recurrent Neural Networks (RNNs)**, focusing on why they were introduced, the limitations of earlier neural network models, and their practical use cases in Natural Language Processing (NLP).

The emphasis is on **conceptual clarity before implementation**.

---

## ❓ Why RNNs Were Introduced

Early neural network architectures struggled with **sequential and contextual data**.

### ❌ Limitations of Artificial Neural Networks (ANN)
- Treats input features as independent
- No understanding of sequence or order
- Cannot retain information from previous inputs
- Ineffective for language and time-series data

### ❌ Limitations of Convolutional Neural Networks (CNN)
- Designed mainly for spatial feature extraction
- Performs well on images but poorly on sequences
- No internal memory mechanism
- Processes each input independently during inference

---

## ✅ What RNN Solves

Recurrent Neural Networks introduce a **hidden state (memory)** that carries information forward across time steps.

Each prediction depends on:
- Current input
- Previous hidden state

This enables RNNs to learn **temporal dependencies** and **contextual relationships**.

---

## 🧠 Applications of RNN

RNNs are commonly used in:
- ✍️ Automatic sentence completion
- 🌍 Machine translation
- 🏷️ Named Entity Recognition (NER)
- 😊 Sentiment analysis
- 🎤 Speech recognition
- 📈 Time-series forecasting

---

## 🔑 Key Takeaway

ANN and CNN update weights during training but do not preserve information across inputs.  
RNNs address this limitation by introducing **memory**, making them suitable for sequential data.

---

## 🚀 Future Extensions
- Long Short-Term Memory (LSTM)
- Gated Recurrent Units (GRU)
- Vanishing gradient problem
- Comparison with Transformer architectures
