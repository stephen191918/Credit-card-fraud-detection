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

## Data Preprocessing
1. **Null Values Removal**: No missing values were found.
2. **Duplicate Removal**: Identified and removed duplicate records.
3. **Class Distribution**: The dataset is balanced with an equal number of fraudulent and non-fraudulent transactions.
4. **Outliers**: Not removed, as they may contain valuable fraud-related information.
5. **Dimensionality Reduction**: Not applied due to anonymized feature contributions.

## Model Development
The following models were implemented to classify fraudulent transactions:

### 1. K-Nearest Neighbors (KNN)
- Classified transactions based on the k-nearest points using Euclidean distance.
- Evaluated with k values: 5, 10, 20, and 100.
- Best k value: **5** with an accuracy of **93.49%**.

### 2. Decision Tree Classifier
- Used recursive binary splitting to divide the dataset.
- Applied Grid Search Cross-Validation for hyperparameter tuning.
- Best-performing model used **entropy criterion**.
- Achieved an accuracy of **99.83%** on the test set.

### 3. Ridge and Lasso Regression
- Utilized for feature selection and regularization.
- Identified important features influencing fraud detection, including **V14, V4, and V10**.

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

## How to Run
1. Clone the repository:
   ```sh
   git clone https://github.com/yourusername/credit-card-fraud-detection.git
   ```
2. Install dependencies:
   ```sh
   pip install -r requirements.txt
   ```
3. Run the preprocessing and model training script:
   ```sh
   python main.py
   ```
## References
- "2023 Credit Card Fraud Report." Security.Org, 31 Jan. 2023, www.security.org/digital-safety/credit-card-fraud-report/.
