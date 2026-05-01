# 🌍 Lightweight Semantic SDG Classifier (MVP)

## 📌 Overview

This project is a lightweight prototype that classifies project descriptions into **UN Sustainable Development Goals (SDGs)** using semantic similarity.

Instead of training a heavy machine learning model, it uses transformer-based embeddings to match input text with SDG descriptions.

---

## 🚀 Features

* Uses sentence embeddings for semantic understanding
* Returns Top-3 SDG predictions
* Fast and low-compute approach
* Works without labeled training data

---

## 🧠 Approach

1. Convert SDG descriptions into embeddings
2. Convert input text into embedding
3. Compute cosine similarity
4. Return most similar SDGs

---

## 📊 Example

**Input:**
"A mobile app for rural healthcare access"

**Output:**
SDG 3 – Good Health and Well-being

---

## ⚠️ Limitations

* Uses short SDG descriptions (can reduce accuracy)
* No multi-label classification yet
* No domain-specific fine-tuning

---

## 🔮 Future Improvements

* Use real-world datasets (DPG registry)
* Add multi-label classification
* Deploy as API or web app

---

## 🛠️ Tech Stack

* Python
* Sentence Transformers
* Scikit-learn

---

## 📎 Notebook

Run the project here:
https://colab.research.google.com/drive/10J4LzjF8ETYLUDO_eSFAKiXGpR8Ngg65#scrollTo=x16FTL9SRT73

---

## 🎯 Purpose

This project was built as a **proof-of-concept** for SDG classification systems and demonstrates how low-compute NLP techniques can be applied to real-world problems.

