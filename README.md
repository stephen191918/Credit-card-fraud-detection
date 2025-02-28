# Credit-card-fraud-detection

## Overview
This project focuses on detecting credit card fraud using machine learning techniques. The dataset used, "Credit Card Fraud Detection Dataset 2023" from Kaggle, contains real-world transaction records, including both legitimate and fraudulent transactions. The goal is to analyze patterns in fraudulent transactions and develop machine learning models to enhance fraud detection mechanisms.

## Key Questions
1. What are the prevalent characteristics of fraudulent transactions in the dataset?
2. Can machine learning algorithms effectively distinguish between legitimate and fraudulent transactions?

## Dataset
The dataset consists of 550,000 transaction records with the following features:
- **ID**: Unique identifier for each transaction.
- **V1 - V28**: Anonymized numerical attributes representing transaction details.
- **Amount**: Transaction amount.
- **Class**: Binary label indicating fraudulent (1) or non-fraudulent (0) transactions.

![features](https://github.com/user-attachments/assets/e7e60b7a-4c02-4789-931f-e87deddfa153)


## Data Preprocessing
1. **Null Values Removal**: No missing values were found.

![remove null](https://github.com/user-attachments/assets/497322ca-456a-49d2-ac27-6be68148bf38)

2. **Duplicate Removal**: Identified and removed duplicate records.

![remove duplicates](https://github.com/user-attachments/assets/bea2efb3-fe68-4a57-a25e-a953ae03efcd)

3. **Class Distribution**: The dataset is balanced with an equal number of fraudulent and non-fraudulent transactions.
4. **Outliers**: Not removed, as they may contain valuable fraud-related information.
5. **Dimensionality Reduction**: Not applied due to anonymized feature contributions.

## Model Development
The following models were implemented to classify fraudulent transactions:

### 1. K-Nearest Neighbors (KNN)
- Classified transactions based on the k-nearest points using Euclidean distance.
- Evaluated with k values: 5, 10, 20, and 100.
- Best k value: **5** with an accuracy of **93.49%**.

![knn](https://github.com/user-attachments/assets/099a5973-61c9-4d6e-85f9-babfe984b11d)

![knn accuracy](https://github.com/user-attachments/assets/afeda739-514b-4722-9108-49e71ca480c4)


### 2. Decision Tree Classifier
- Used recursive binary splitting to divide the dataset.
- Applied Grid Search Cross-Validation for hyperparameter tuning.
- Best-performing model used **entropy criterion**.
- Achieved an accuracy of **99.83%** on the test set.

![tree parameter](https://github.com/user-attachments/assets/80ed9a1b-5142-468c-a318-d1050aab61fc)

![tree](https://github.com/user-attachments/assets/fa211634-b2c9-4fd1-bb95-f6eecb8cea57)

![tree plot](https://github.com/user-attachments/assets/9fb90017-384c-45d9-bef1-3d923ee7184f)


### 3. Ridge and Lasso Regression
- Utilized for feature selection and regularization.
- Identified important features influencing fraud detection, including **V14, V4, and V10**.
![ridge lasso plot](https://github.com/user-attachments/assets/afdb1734-0d58-449c-90e0-0cf8873ed9c2)
![feature importance](https://github.com/user-attachments/assets/70391b73-89c3-442f-b523-e014ee8ddc08)

## Results
- **KNN Classifier**: Highest accuracy obtained with **k=5** at **93.49%**.
- **Decision Tree Classifier**: Achieved a test accuracy of **99.83%**.
- **Feature Importance**: Features **V14, V4, and V10** showed strong correlations with fraud.
- **Confusion Matrix Analysis**:
  - **True Positives (Legit-Legit)**: 85,312
  - **True Negatives (Fraud-Fraud)**: 84,995
  - **False Positives (Fraud-Legit)**: 198
  - **False Negatives (Legit-Fraud)**: 84

## Conclusion
- The **Decision Tree Classifier** outperformed KNN with **99.83%** accuracy.
- Feature importance analysis suggests a focus on **V14, V4, and V10** for further fraud detection improvements.
- The model can be used to **automate fraud detection**, **reduce manual review time**, and **enhance financial security**.

## Future Improvements
- Explore deep learning models for improved fraud detection.
- Implement real-time fraud detection strategies.
- Further investigate feature engineering techniques to enhance model interpretability.

## References
- "2023 Credit Card Fraud Report." Security.Org, 31 Jan. 2023, www.security.org/digital-safety/credit-card-fraud-report/.
