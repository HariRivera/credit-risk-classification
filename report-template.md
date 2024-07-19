# Module 12 Report Template

## Overview of the Analysis

In this analysis, we aimed to evaluate the creditworthiness of borrowers using historical lending data from a peer-to-peer lending services company. The purpose was to predict whether a loan is healthy (`0`) or high-risk (`1`) based on various financial information about the borrowers and their loans.

The dataset contained the following variables:
- `loan_size`: The size of the loan.
- `interest_rate`: The interest rate of the loan.
- `borrower_income`: The income of the borrower.
- `debt_to_income`: The debt-to-income ratio of the borrower.
- `num_of_accounts`: The number of accounts the borrower has.
- `derogatory_marks`: The number of derogatory marks on the borrower's credit report.
- `total_debt`: The total debt of the borrower.
- `loan_status`: The status of the loan (0 = healthy loan, 1 = high-risk loan).

Our target variable was `loan_status`, which indicates the health of the loan. Here is a basic overview of the target variable:

# Basic information about the target variable
value_counts = y.value_counts()
print(value_counts)

## Stages of the Machine Learning Process

### Data Preprocessing

- Read the data from `lending_data.csv`.
- Created the labels set (`y`) from the `loan_status` column.
- Created the features DataFrame (`X`) by excluding the `loan_status` column.

### Data Splitting

- Split the data into training and testing sets using `train_test_split`.

### Model Training

- Trained a Logistic Regression model using the training data (`X_train` and `y_train`).

### Model Evaluation

- Made predictions on the testing data (`X_test`).
- Evaluated the model’s performance using a confusion matrix and a classification report to obtain precision, recall, and F1-score for both classes (`0` and `1`).

## Results

* **Logistic Regression Model:**
    * **Accuracy:** 0.99
    * **Precision:** 
        - Class `0` (healthy loan): 1.00
        - Class `1` (high-risk loan): 0.84
    * **Recall:** 
        - Class `0` (healthy loan): 0.99
        - Class `1` (high-risk loan): 0.94
    * **F1-Score:**
        - Class `0` (healthy loan): 1.00
        - Class `1` (high-risk loan): 0.89

## Summary

The Logistic Regression model performs exceptionally well in predicting both healthy and high-risk loans. It achieves an overall accuracy of 99%, with very high precision and recall for healthy loans, and reasonably high precision and recall for high-risk loans.

* **Best Performing Model:** The Logistic Regression model is the best performing model based on the metrics obtained. It shows a perfect balance between precision and recall for healthy loans and good balance for high-risk loans.
* **Performance Dependence:** The performance of the model is generally robust, but it slightly varies when predicting high-risk loans due to the lower precision. However, since the recall for high-risk loans is high (0.94), the model effectively identifies most of the high-risk loans, which is crucial for minimizing potential defaults.

### Recommendation

Given the high accuracy, precision, and recall scores, I recommend using the Logistic Regression model for evaluating the creditworthiness of borrowers. Its performance in identifying high-risk loans (which is a critical aspect of loan approval processes) makes it a reliable model for this purpose.
