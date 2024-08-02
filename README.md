# Fraud Detection in Online Transactions

This project aims to detect fraudulent online transactions using anomaly detection techniques. Given the extremely low ratio of fraudulent transactions (less than 0.00005), traditional classification algorithms are prone to overfitting. To address this, we employ oversampling and undersampling methods to balance the dataset.

## Table of Contents

- [Overview](#overview)
- [Techniques Used](#techniques-used)
- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Overview

Fraud detection in online transactions is a critical task due to the potential financial losses and security issues involved. The challenge lies in the significant imbalance between fraudulent and non-fraudulent transactions. This project focuses on using anomaly detection techniques, such as oversampling and undersampling, to create a balanced dataset suitable for effective fraud detection.

## Techniques Used

1. **Oversampling**: Techniques like SMOTE (Synthetic Minority Over-sampling Technique) to generate synthetic samples for the minority class (fraudulent transactions).
2. **Undersampling**: Reducing the number of samples in the majority class (non-fraudulent transactions) to balance the dataset.
3. **Anomaly Detection Algorithms**: Applying algorithms that are robust to imbalanced datasets for detecting fraud.

## Installation

To get started with this project, clone the repository and install the required dependencies.

```bash
git clone https://github.com/yourusername/fraud-detection.git
cd fraud-detection
pip install -r requirements.txt
```
# Usage
1. Preprocess the dataset to handle missing values and perform feature scaling.
2. Apply oversampling and undersampling techniques to balance the dataset.
3. Train anomaly detection algorithms on the balanced dataset.
4. Evaluate the model's performance using appropriate metrics.
   
Example usage:
```python
from imblearn.over_sampling import SMOTE
from sklearn.model_selection import train_test_split
from sklearn.ensemble import IsolationForest
from sklearn.metrics import classification_report

# Load and preprocess the data
# X, Y should be your features and target variable

# Apply SMOTE to balance the dataset
smote = SMOTE()
X_resample, Y_resample = smote.fit_resample(X, Y)

# Split the dataset
X_train, X_test, Y_train, Y_test = train_test_split(X_resample, Y_resample, test_size=0.2, random_state=42)

# Train the model
model = IsolationForest()
model.fit(X_train, Y_train)

# Predict and evaluate
Y_pred = model.predict(X_test)
print(classification_report(Y_test, Y_pred))
```
# Contributing
Contributions are welcome! Please fork the repository and submit a pull request with your improvements.
