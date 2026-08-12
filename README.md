# Fraud Detection System

A machine learning-based fraud detection system for financial transactions. This project analyzes transaction patterns to identify potentially fraudulent activities using logistic regression with balanced class weights.



## Features

* Data Analysis: Comprehensive exploratory data analysis (EDA) of transaction data
* Fraud Detection: Machine learning model to predict fraudulent transactions
* Interactive Web App: Streamlit-based user interface for real-time predictions
* Feature Engineering: Custom features like balance differences to improve detection
* Visualization: Data visualization using matplotlib and seaborn



## Run It

**Prerequisites**
pip install pandas numpy matplotlib seaborn scikit-learn streamlit joblib

**Start the Web App**
streamlit run fraud_detection.py

**Run the Analysis Notebook**
Open `analysis_model.ipynb` in Jupyter Lab or Jupyter Notebook to explore the data and model training process.



## Files

* `analysis_model.ipynb` - Complete data analysis, preprocessing, and model training pipeline
* `fraud_detection.py` - Streamlit web application for real-time fraud predictions
* `fraud_detection_pipline.pkl` - Trained machine learning model pipeline
* `AIML Dataset.csv` - Transaction dataset (not included, needs to be added)



## Model Overview

The system uses a logistic regression classifier with the following features:

* Transaction Features: Amount, transaction type
* Balance Features: Sender and receiver balances (old and new)
* Engineered Features: Balance differences for both sender and receiver

**Model Performance**

* Accuracy: 94.5%
* Recall (Fraud): 94% - Successfully identifies 94% of fraudulent transactions
* Precision (Fraud): 2% - Due to extreme class imbalance (0.13% fraud rate)



## Data Processing

The pipeline includes:

1. Feature Engineering: Creating balance difference features
2. Preprocessing: Standard scaling for numerical features, one-hot encoding for categorical variables
3. Class Balancing: Using `class_weight="balanced"` to handle imbalanced data



## Web Application Features

* User-friendly interface for entering transaction details
* Real-time fraud prediction
* Visual feedback with color-coded results (red for fraud, green for legitimate)
* Support for all transaction types (PAYMENT, TRANSFER, CASH_OUT, DEPOSIT)



## Dataset Notes

The dataset contains approximately 6.36 million transactions with the following characteristics:

* Fraud Rate: Only 0.13% of transactions are fraudulent
* Fraud Types: Fraud only occurs in CASH_OUT and TRANSFER transactions
* Features: Step (time), transaction type, amount, sender/receiver balances, fraud flags



## Requirements

* Python 3.7+
* pandas
* numpy
* matplotlib
* seaborn
* scikit-learn
* streamlit
* joblib



## Notes

* The model achieves high recall for fraud detection but low precision due to the extreme class imbalance
* This system focuses on catching as many fraudulent transactions as possible (recall) even at the cost of false positives
* The web app uses the trained pipeline without requiring additional model training



## Built While Learning

This project was developed while learning:

* Handling imbalanced datasets in machine learning
* Building end-to-end ML pipelines with scikit-learn
* Creating interactive web applications with Streamlit
* Feature engineering for financial transaction data
* Model evaluation with imbalanced classification metrics
