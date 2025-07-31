# Fraud_Detection_Project

This project focuses on building a machine learning model to detect fraudulent financial transactions from a synthetic dataset that mimics real-world payment data. The entire workflow, from data cleaning to final model evaluation and explanation, is documented in the accompanying Jupyter Notebook.

Dataset:
The dataset used is a synthetic financial dataset generated using PaySim. It is designed to simulate mobile money transactions with a focus on capturing fraudulent behavior. The data includes transaction types, amounts, and account balance information for both the originator and recipient of the transactions.

Project Workflow:
The project followed a structured machine learning pipeline:
1. Data Cleaning & Preprocessing: Handled missing values, analyzed outliers, checked for multi-collinearity, and prepared the data for modeling.
2. Exploratory Data Analysis (EDA): Investigated the data to uncover initial patterns. A key discovery was that fraudulent behavior was limited to TRANSFER and CASH_OUT transaction types.
3. Feature Engineering: Created new, powerful features based on domain logic to better capture fraudulent behavior. The most impactful engineered feature was isOrigAccountEmptied.
4. Model Building & Comparison: XGBoost
5. Model Evaluation: Assessed models using metrics appropriate for imbalanced datasets, including Precision, Recall, F1-Score, ROC AUC, and the Confusion Matrix.
6. Model Explanation: Used SHAP (SHapley Additive exPlanations) to understand the "why" behind the final model's predictions, confirming that it learned logical and explainable patterns.

# Key Findings
The analysis revealed that fraud is not predicted by simple features alone but by specific behavioral patterns:
The single most important predictor of fraud is when a transaction completely empties the originator's account.
This pattern is almost exclusively seen in TRANSFER and CASH_OUT transactions, which mimics the real-world criminal behavior of draining an account's funds.

# Final Model and Performance
The XGBoost Classifier was selected as the final and best-performing model. It provided the most effective balance between catching fraud and minimizing false alarms.
Recall (Fraud Detection Rate): 71%
Precision (Alert Accuracy): 80%
ROC AUC Score: 99.9%

# Tools and Libraries
Data Manipulation: pandas
Machine Learning: scikit-learn, XGBoost
Data Visualization: Matplotlib, Seaborn
Model Explainability: SHAP

📂 How to Use
Clone this repository to your local machine.
Ensure you have the necessary libraries installed. You can install them using pip:

pip install pandas scikit-learn xgboost lightgbm matplotlib seaborn shap
Open and run the Fraud_Detection_Project.ipynb notebook in a Jupyter environment. The notebook contains all the code and analysis steps from start to finish.
