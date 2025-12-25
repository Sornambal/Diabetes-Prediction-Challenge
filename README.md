# 📊 Diabetes Prediction Challenge (Kaggle Playground S5E12)

This repository contains a **high-performance machine learning solution** developed for the **Diabetes Prediction Challenge**, part of the **Kaggle Playground Series – Season 5, Episode 12**.

The goal of the competition is to **predict the probability that a patient will be diagnosed with diabetes**, evaluated using the **ROC–AUC** metric.

---

## 🏆 Competition Overview

- **Competition Name:** Diabetes Prediction Challenge  
- **Series:** Kaggle Playground Series (Season 5, Episode 12)  
- **Evaluation Metric:** Area Under the ROC Curve (AUC)  
- **Problem Type:** Binary classification (probability prediction)  
- **Dataset Type:** Synthetic tabular dataset  

📌 **Dataset Link:**  
https://www.kaggle.com/competitions/playground-series-s5e12/data

---

## 🚀 Solution Highlights

- ✅ **LightGBM-based model** optimized for tabular data
- ✅ **Ordinal Encoding** for categorical features
- ✅ **Stratified K-Fold Cross-Validation (10 folds)** for stability
- ✅ **Early stopping** to prevent overfitting
- ✅ Tuned for **Public Leaderboard performance**

This approach follows techniques commonly used by **top Kaggle competitors** in the Playground Series.

---

## 🧠 Modeling Approach

### 1. Data Preprocessing
- Removed rows with missing target values (`diagnosed_diabetes`)
- Separated features and target variable
- Identified categorical and numerical columns

### 2. Categorical Feature Handling
- Used **Ordinal Encoding**
- Encoder trained on **combined train + test data** to avoid unseen categories during inference

### 3. Model Used
- **LightGBM Classifier**
- Key hyperparameters:
  - `n_estimators = 5000`
  - `learning_rate = 0.01`
  - `num_leaves = 96`
  - Strong regularization (`reg_alpha`, `reg_lambda`)
- Early stopping with validation AUC

### 4. Cross-Validation Strategy
- **10-fold StratifiedKFold**
- Ensures class balance across folds
- Final predictions averaged across all folds

---

## 📈 Performance

- **Validation Metric:** ROC–AUC  
- **Mean CV AUC:** ~0.72+ (may vary slightly per run)  
- Designed to be **robust to leaderboard shake-ups**

> ⚠️ Public leaderboard uses only ~20% of test data; final rankings may differ.

---

## 📂 Repository Structure

```text
├── train.csv                  # Kaggle training dataset
├── test.csv                   # Kaggle test dataset
├── submission.csv             # Generated submission file
├── diabetes_prediction.py     # Model training & inference code
└── README.md                  # Project documentation
