# Credit Risk Analysis Report
By: Kiana Navarre

## Overview of the Analysis
The following analysis was performed using a dataset of historical lending activity from a peer-to-peer lending services company with the intention of building a model to identify the creditworthiness of future prospective borrowers. The dataset included the following information for both healthy loans (loan status = 0) and high-risk loans (loan status = 1):
  * loan size
  * interest rate 
  * borrower income
  * debt to income ratio 
  * number of accounts
  * number of derogatory marks 
  * total debt

The dataset includes a total of 75,036 records for healthy loans and 2,500 records for high-risk loans. 

## Procedure
To begin the analysis, the data was split into training and testing datasets using `train_test_split`. Two separate logistic regression models were then created using the `LogisticRegression` model from SKLearn. Machine Learning Model 1 uses a logistic regression model fitted with the original training data, whereas Machine Learning Model 2 uses a logistic regression model fitted with random oversampled training data.  The performance for both models was then evaluated by calculating the overall accuacy score of the model, generating a confusion matrix, and analyzing the classification report. 

## Results
The results for both models are as follows: 

Machine Learning Model 1: 
  *  Balanced Accuracy Score: 0.95
  * Precision Scores
    * Healthy Loans: 1.00
    * High-Risk Loans: 0.85
  * Recall Scores
    * Healthy Loans: 0.99
    * High Risk Loans: 0.91
  * F1 Scores: 
    * Healthy Loans: 1.00
    * High Risk Loans: 0.88

Machine Learning Model 2:
  *  Balanced Accuracy Score: 0.99
  * Precision Scores
    * Healthy Loans: 1.00
    * High-Risk Loans: 0.84
  * Recall Scores
    * Healthy Loans: 0.99
    * High Risk Loans: 0.99
  * F1 Scores: 
    * Healthy Loans: 1.00
    * High Risk Loans: 0.91

## Summary
The data shows that both of the models perfom relatively well.  The logistic regression model fitted with oversampled data predicts healthy loans ('0') with a precision rate of 100% and an F1 score of 1.  For high-risk loans ('1') it predicts with a precision rate of 84% and an F1 score of 0.91.  Although the precision rate for high-risk loans drops by 1% when the model is fitted with oversampled data, the F1 score increases from 0.88 to 0.91.  Thus the logistic regression model fitted with the oversampled data performs better, especially when determing high-risk loans.  

As the purpose of this model was to predict the creditworthiness of future prospective borrowers, accurately determining if a customer would be in the high-risk loan category is arguably more important as these customers are considered more likely to default on their loans.  Therefore, because Machine Learning Model 2 does a better job at predicting high-risk loans, I'd recommend the use of this model moving forward.  
