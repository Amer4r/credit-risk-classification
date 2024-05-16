# Module 12 Report Template

## Overview of the Analysis
### The purpose of the analysis:
- The goal of this analysis is to create and assess machine learning models to evaluate borrowers' creditworthiness. By utilizing historical lending data from a peer-to-peer lending company, we aim to construct predictive models that can pinpoint loans with a high risk of default.

### Financial Data Info:
- The dataset for this analysis includes historical lending activity data, detailing information about borrowers and loan outcomes. We concentrate on the "loan_status" column, where a value of 0 represents a healthy loan and a value of 1 signifies a high risk. The predicted model will predict wether the borrower is a high risk to loan or not.

### Variable Information:
The dataset contains 77536 rows of information.
- X variable is the features which contains of 7 columns such as 'loan_size', 'borrower_income'.
- y variable: is the 'loan_status' column, where 0 represents healthy loans, and 1 represents high-risk loans. this variable is used as a label to determine the risk of the borrowers.

#### Machine Learning Process
Our analysis involved the following stages:

1. Data Preparation: Reading the data from the csv file and preparing the data to be trained and tested.
2. Data Splitting: Splitting the data it into training and testing sets.
3. Model Building: Training logistic regression models using the trained data.
4. Evaluation: Evaluationg model performance through metrics.

Method Used:
- We used logistic regression, a widely used classification algorithm to model credit risk. 
Logistic regression is used for its simplicity, interpretability, and effectiveness in binary classification problems. It provides clear probabilistic outputs, handles linearly separable data well, and allows for easy implementation and quick training, making it a reliable choice for predicting outcomes such as credit risk.

## Results

Using bulleted lists, describe the accuracy scores and the precision and recall scores of all machine learning models.

### Machine Learning Model 1: Logistic Regression with Original Data

- Accuracy: Model 1 achieved a high accuracy score of around 94%, demonstrating its effectiveness in classifying both healthy (0) and high-risk (1) loans.

- Precision and Recall: The precision for high-risk loans (1) is 0.89, indicating that 89% of the loans predicted as high-risk are correctly identified. The recall for high-risk loans is 0.87, meaning the model accurately detects 87% of all high-risk loans in the dataset. These values show the model is fairly good at identifying high-risk loans, though there is potential for improvement.

- Confusion Matrix: The confusion matrix shows that the model correctly predicted most healthy loans (true negatives: 18,679) with a few false negatives (67). It also correctly identified many high-risk loans (true positives: 558) but had some false positives (80).

## Summary

The Logistic Regression model performs well in predicting healthy loans. However, it misclassifies 10% of high-risk loans as healthy according to the test data. Although the training loans are all for amounts under $24,000, a defaulted loan, especially early on, could cost the company more than the interest earned from multiple healthy loans.

Additionally, there are relatively few high-risk loans in the dataset for the model to learn from compared to the number of healthy loans. Adding more high-risk loan data for training could potentially improve the model.

When classifying loans, preventing high-risk loans is crucial, as the financial loss from a single defaulted loan can outweigh the interest earned from a healthy loan.

If this model is only applied to loans under $24,000 and the historical ratio of healthy to risky loans matches the dataset (30 to 1), it might be appropriate. Otherwise, I wouldn't recommend it due to the increased risk. Additionally, the model provides binary outcomes (healthy/risky) without offering a probability score, which would enable a more nuanced review for borderline cases.
