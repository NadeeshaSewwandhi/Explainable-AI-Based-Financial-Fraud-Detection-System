# Explainable-AI-Based-Financial-Fraud-Detection-System


# Project Overview

This project focuses on developing an end-to-end machine learning-based financial fraud detection system for identifying fraudulent transactions within highly imbalanced transaction data. The project addresses the challenges associated with fraud detection, particularly the significantly smaller number of fraudulent transactions compared with legitimate transactions.

The system incorporates data preprocessing, class-imbalance handling, machine learning model development, threshold optimization, model evaluation, explainable AI, and web-based deployment for interactive fraud-risk assessment.

# Data Preprocessing

The raw transaction data was processed to prepare it for machine learning. The preprocessing workflow included:

Handling missing values
Identifying numerical and categorical features
Encoding categorical variables
Scaling numerical features
Removing unnecessary or identifier-related information where appropriate
Splitting the dataset into training and testing subsets

A ColumnTransformer was used to apply different preprocessing techniques to numerical and categorical features. Numerical variables were standardized using StandardScaler, while categorical variables were transformed using OneHotEncoder.

# Handling Class Imbalance

A major challenge in the project was the highly imbalanced nature of the fraud dataset, where legitimate transactions significantly outnumbered fraudulent transactions.

To address this problem, Synthetic Minority Over-sampling Technique (SMOTE) was incorporated into the model development process. SMOTE generates synthetic samples for the minority class, helping the model learn patterns associated with fraudulent transactions rather than being biased toward the majority class.

This approach improved the model's ability to identify fraudulent transactions.

# Model Development

Multiple machine learning approaches were considered and evaluated, including:

Logistic Regression with SMOTE
XGBoost with SMOTE

The models were compared based on their ability to correctly identify fraudulent transactions while minimizing false positives.

XGBoost was selected as the final model due to its stronger classification performance and ability to capture complex, non-linear relationships within transaction data.


# Threshold Optimization

Since fraud detection is a highly sensitive classification problem, the default classification threshold was further optimized.

A threshold of 0.99 was applied to the final XGBoost model to improve the precision of fraud predictions. This helped reduce the number of legitimate transactions incorrectly classified as fraudulent while maintaining a reasonable level of fraud detection.

The final model achieved:

Precision: 79.84%
Recall: 68.28%
F1-score: 73.61%
ROC-AUC: 99.02%
PR-AUC: 75.92%
