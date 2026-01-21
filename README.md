Credit Card Default Prediction (End-to-End ML Project)
🔍 Problem Statement

Predict whether a credit card customer will default next month using historical financial and demographic data.
This is a binary classification problem with imbalanced classes, common in real-world banking systems.

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

Workflow & Key Decisions
1️⃣ Exploratory Data Analysis (EDA)

Dataset size: 30,000 rows × 25 columns

Target variable is imbalanced (~22% default)

Features include:

Categorical (SEX, EDUCATION, MARRIAGE)

Ordinal (PAY_0 to PAY_6)

Numerical (LIMIT_BAL, BILL_AMT*, PAY_AMT*)

➡️ Insight: Accuracy alone is misleading for this dataset.

2️⃣ Data Cleaning

No missing values

Invalid category values corrected (merged, not dropped → avoids data loss)

ID column removed (non-informative)

➡️ Cleaned data saved as reusable CSV.

3️⃣ Feature Engineering

One-Hot Encoding for categorical variables

Standard scaling for numerical features

Train–Test split done before encoding/scaling to prevent data leakage

➡️ Feature-engineered data kept model-dependent.

4️⃣ Modeling

Model used: Logistic Regression

Handled class imbalance using:

class_weight='balanced'

Evaluation based on:

Confusion Matrix

Precision, Recall, F1-score

➡️ Business focus:

Recall prioritized to reduce False Negatives (missed defaulters)

📈 Results Summary

Accuracy: ~68%

Recall (Default class): ~62%

Demonstrates trade-off between precision and recall in financial risk modeling

🏦 Business Interpretation

False Negative (FN) → High risk (loan approved to defaulter)

False Positive (FP) → Opportunity cost (good customer rejected)

➡️ Model optimized to minimize financial loss, not maximize accuracy.

🛠️ Tech Stack

Python

Pandas, NumPy

Scikit-learn

Jupyter Notebook

🚀 How to Run

Clone the repository

Install dependencies

Run notebooks in order:

01_eda_credit_default.ipynb → 04_modeling.ipynb

🎯 Key Learning Outcomes

Real-world ML workflow

Handling imbalanced datasets

Preventing data leakage

Business-driven model evaluation

⭐ If you found this useful, feel free to star the repo!
