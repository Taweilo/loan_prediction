# Loan Prediction

## Introduction  
This project focuses on predicting loan defaults using machine learning models. We analyze the dataset, handle missing values, address class imbalance, and evaluate model performance to develop a reliable prediction system.

## Data Understanding  
1. **Irrelevant Features**: The `Application ID` is not needed for modeling.  
2. **Missing Data**: The features `person_emp_length` and `loan_int_rate` contain missing values.  
3. **Data Quality Issues**:  
   - `person_emp_length` and `person_age` above 100 years are considered anomalies.  
4. **Class Imbalance**:  
   - The dataset is highly imbalanced, with non-default cases being more than three times the default cases.  

## Data Preparation  
1. **Define Features and Target (`X, y`)**  
2. **Split Data**:  
   - Training Set: 40%  
   - Validation Set: 30%  
   - Test Set: 30%  
3. **Handle Imbalance**:  
   - Applied **undersampling** to balance the dataset.  

## Modeling  
We trained and compared three machine learning models:  
- **Logistic Regression**  
- **Decision Tree**  
- **XGBoost (XGB)**  

## Evaluation  
The models were evaluated using accuracy, AUC (Area Under Curve), and F1-score.  

| Model                | Accuracy | AUC  | F1   |
|----------------------|----------|------|------|
| Logistic Regression  | 0.81     | 0.86 | 0.63 |
| Decision Tree        | 0.90     | 0.90 | 0.77 |
| XGB Classifier       | 0.87     | 0.92 | 0.74 |

![Model Performance](https://github.com/user-attachments/assets/f6195a5b-a99d-48c6-9f00-4466e4c5eeb7)  

## Strategy Table  
This table shows the acceptance rate, the corresponding probability threshold, and the bad rate for different cutoff levels.  

| Acceptance Rate | Threshold | Bad Rate |
|-----------------|-----------|----------|
| 1.00            | 1.000     | 0.223    |
| 0.95            | 1.000     | 0.223    |
| 0.90            | 0.976     | 0.102    |
| 0.85            | 0.931     | 0.094    |
| 0.80            | 0.488     | 0.071    |
| 0.75            | 0.464     | 0.070    |
| 0.70            | 0.375     | 0.062    |
| 0.65            | 0.260     | 0.058    |
| 0.60            | 0.260     | 0.058    |
| 0.55            | 0.260     | 0.058    |
| 0.50            | 0.260     | 0.058    |
| 0.45            | 0.225     | 0.046    |
| 0.40            | 0.133     | 0.025    |
| 0.35            | 0.133     | 0.025    |
| 0.30            | 0.133     | 0.025    |
| 0.25            | 0.133     | 0.025    |
| 0.20            | 0.133     | 0.025    |
| 0.15            | 0.133     | 0.025    |
| 0.10            | 0.098     | 0.024    |
| 0.05            | 0.000     | 0.012    |

![Strategy Chart](https://github.com/user-attachments/assets/4ea5d41b-2d5c-4750-b685-997834ca4c3c)

- Profit matrix consulting the strategy table
- Used 0.4 acceptance rate
| pred_loan_status_0.4_acc | 0              | 1              |
|----------------------------|---------------|---------------|
| **true_loan_status**       |               |               |
| 0                          | $7,472,474.55  | $36,470,280.15 |
| 1                          | $191,847.87    | $12,393,372.42 |
