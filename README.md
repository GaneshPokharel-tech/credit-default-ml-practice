# Credit Card Default Prediction (End-to-End ML Project)

## Overview
This project builds an end-to-end machine learning pipeline to predict whether a credit card customer will default on payment next month.  
The focus is on **real-world ML practices** such as handling imbalanced data, preventing data leakage, and business-driven evaluation.

---

## Problem Statement
Predict **default payment next month (Yes/No)** using customer demographic and financial history data.  
This is a **binary classification** problem with a **class imbalance**, commonly seen in banking and credit risk systems.

---

## Dataset
- Rows: 30,000
- Columns: 25
- Target Variable: `default payment next month`
- Class Distribution:
  - Non-default (0): ~78%
  - Default (1): ~22%

---

## Project Structure
```
credit-card-default/
│
├── 01_eda_credit_default.ipynb
├── 02_data_cleaning.ipynb
├── 03_feature_engineering.ipynb
├── 04_modeling.ipynb
│
├── processed_credit_card_clients.csv
├── requirements.txt
└── README.md
```

---

## Workflow Summary

### 1. Exploratory Data Analysis (EDA)
- Identified class imbalance in target variable
- Classified features into categorical, ordinal, and numerical types
- Confirmed no missing values

> Accuracy alone is misleading for this dataset.

---

### 2. Data Cleaning
- Fixed invalid category values (merged instead of dropped)
- Removed non-informative ID column
- Saved cleaned dataset as a reusable CSV

---

### 3. Feature Engineering
- One-Hot Encoding for categorical variables
- Standard scaling for numerical variables
- **Train–test split performed before encoding and scaling** to prevent data leakage

---

### 4. Modeling
- Model: Logistic Regression
- Class imbalance handled using `class_weight='balanced'`
- Manual preprocessing used for learning clarity (no pipeline)

---

## Evaluation
- Confusion Matrix
- Precision, Recall, F1-score

Key result:
- Recall (Default = 1): ~62%
- Accuracy: ~68%

> Recall was prioritized to minimize false negatives (missed defaulters).

---

## Business Interpretation
- **False Negative**: Approving a loan to a defaulter (high financial risk)
- **False Positive**: Rejecting a good customer (opportunity cost)

The model is evaluated from a **risk management perspective**, not just accuracy.

---

## Tech Stack
- Python
- Pandas, NumPy
- Scikit-learn
- Jupyter Notebook

---

## How to Run
1. Clone the repository
2. Install dependencies from `requirements.txt`
3. Run notebooks in order:
   - `01_eda_credit_default.ipynb`
   - `02_data_cleaning.ipynb`
   - `03_feature_engineering.ipynb`
   - `04_modeling.ipynb`

---

## Key Learnings
- Handling imbalanced datasets
- Preventing data leakage
- Manual feature engineering for better understanding
- Business-oriented model evaluation

---
## 🚀 Future Improvements
- Threshold tuning
- Class-weight optimization
- Tree-based models
- ROC-AUC and PR-AUC evaluation

## 👤 Author
Ganesh Pokharel  
Aspiring Data Scientist | Machine Learning Learner

⭐ Feel free to star the repository if you find it useful!
