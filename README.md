# FraudGuard-Credit-Card-Transaction-Anomaly-Detection
I tackled a real-world fintech challenge: detecting fraudulent credit card transactions in an extremely imbalanced dataset where traditional rule-based systems fail missing sophisticated fraud (false negatives) while incorrectly flagging legitimate customers (false positives).

🛡️ FraudGuard: Credit Card Transaction Anomaly Detection

 📌 Project Overview

FraudGuard is a machine learning–based credit card fraud detection system i developed as a capstone project after completing the Machine Learning Scientist track with AI Community Africa*. The project addresses the limitations of traditional rule-based fraud systems by leveraging advanced machine learning techniques to accurately detect fraudulent transactions while minimizing false alerts that negatively impact customer experience.

 🎯 Problem Statement

The Credit card fraud detection presents two major challenges:

1. Extreme class imbalance (fraud transactions account for ~0.17% of all data)
2. Asymmetric error costs, where missed fraud (false negatives) leads to financial loss, while false alarms (false positives) frustrate legitimate customers

The objective of this project was to build a fraud detection model that maximizes precision* (to reduce false positives) while maintaining strong recall* (to catch fraud), making accuracy an unsuitable evaluation metric.

📊 Dataset

Source:Industry-standard credit card fraud dataset from kaggle (`creditcard.csv`)
Description: Transactions made by European cardholders in September 2013
Features:

V1–V28: PCA-transformed features for confidentiality
Time: Seconds elapsed between transactions
Amount: Transaction value

Target Variable:
Class = 1: Fraudulent transaction
Class = 0: Genuine transaction

🧠 Solution Approach

1. Data Preprocessing

Standardization of Time and Amount
Separation of features and target variable
Stratified train-test split to preserve class distribution

2. Handling Class Imbalance

Avoided naive oversampling
Used class-weighted learning to reflect real-world fraud costs

3. Model Selection

Applied XGBoost, a high-performance tree-based ensemble model well-suited for tabular and imbalanced data
Tuned hyperparameters to reduce overfitting and improve class separation

 4. Metric-Driven Evaluation

Focused on Precision, Recall, and Precision–Recall curves
Avoided accuracy due to dataset imbalance

 🔄 Two-Stage Fraud Detection Architecture

To balance recall and precision effectively, I Implemented a two-stage detection system:

🔹 Stage 1: High-Recall Detector

Broad screening model with a low decision threshold
Designed to catch nearly all fraudulent transactions
Accepts higher false positives

🔹 Stage 2: High-Precision Filter
 
 Applied only to transactions flagged by Stage 1
 Uses a stricter threshold and stronger regularization
 Filters out false alarms and confirms high-confidence fraud

This architecture mirrors real-world fintech fraud pipelines and significantly improves usability in production environments.


 📈 Results

High precision achieved, reducing unnecessary customer alerts
 Strong recall maintained, minimizing missed fraud
 Improved balance between fraud prevention and customer experience
 Scalable and deployment-ready design


 🛠️ Tech stacks Used

Python
Pandas, NumPy
scikit-learn
XGBoost
Matplotlib / Evaluation Metrics

 🚀 Key Learnings

Precision–Recall tradeoffs are critical in real-world ML systems
Decision thresholds are business tools, not fixed constants
Two-stage architectures significantly outperform single-model systems in fraud detection
Model evaluation must align with business risk, not just statistical performance

🏁 Conclusion

FraudGuard demonstrates how end-to-end machine learning—combined with business-aware decision-making—can replace rigid rule-based systems with adaptive, scalable, and customer-friendly fraud detection solutions.

