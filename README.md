# credit-risk-classification

## Overview of the Credit Risk Analysis

The purpose of the credit risk analysis was to train a supervised learning model on lending a dataset from a peer-to-peer lending services company and evaluate the model in order to determine the model's efficacy for identifying the creditworthiness of borrowers. Loan information (loan amount, loan interest rate, borrower income, borrower's debt to income ratio, the number of accounts the borrower has open, derogatory marks on the borrower's account, and borrower's total debt) was fed into the model and the model was trained to predict the status of the loan (healthy or high-risk). 

Value counts of the original target data showed that the target data was very unbalanced (healthy (0) - 75036), high-risk (1) - 2500). The dataset was split into testing data and training data. A Sci-kit learn logistic regression model was trained on the training data, then fed the testing data to predict whether a loan was healthy (0) or high-risk (1). The predictions were then compared to the testing data to determine the accuracy, precision, and recall of the model. For comparison, the data was then oversampled the imbalanced-learn RandomOverSampler to generate a resampled dataset (0 - 56271, 1 - 56271) and the process was repeated with the resampled data.  

## Results

* Machine Learning Model 1 (Original Data):
  * Description of Model 1 Accuracy, Precision, and Recall scores.
  * The logistic regression model predicted healthy loans with perfect precision (100% of the loans the model predicted were healthy were actually healthy), extremely high recall (out of all the loans that were healthy, the model predicted that outcome for 99% of those loans), and a perfect F1-score (being equal to 1, the model actually predicts if the loan is healthy.)
  * For high-risk loans, the precision was high (85% of the loans the model predicted were high-risk were actually high-risk), the recall was high (out of all the loans that were high-risk, the model predicted that outcome for 91% of those loans), and the F1-score was also high (0.88 is close to 1 indicating that model does a good job predicting if the loan is high-risk).
  * The balanced accuracy score for the model is 95% which is very high.

* Machine Learning Model 2 (Resampled Data):
  * Description of Model 2 Accuracy, Precision, and Recall scores.
  * The logistic regression model fit with oversampled data predicted healthy loans with perfect precision (100% of the loans the model predicted were healthy were actually healthy), extremely high recall (out of all the loans that were healthy, the model predicted that outcome for 99% of those loans), and a perfect F1-score (a score of 1, the model actually predicts if the loan is healthy.)
  * For high-risk loans, the precision was high (84% of the loans the model predicted were high-risk were actually high-risk), the recall was high (out of all the loans that were high-risk, the model predicted that outcome for 99% of those loans), and the F1-score was also high (0.91 is close to 1 indicating that model does a good job predicting if the loan is high-risk).
  * The balanced accuracy score for the model is 99% which is very high.
  * An equally balanced data set lends itself to a high degree of accuracy when used in a logistic regression model.

## Summary

Overall, resampled model has higher accuracy, precision, and recall than the model trained on the original dataset, but because the oversampling duplicated minority data (1 - high-risk), there is a risk that the model is overfit to the training data and should be evaluated on another dataset. That being said, we recommend utilizing the resampled model due to it's higher accuracy predicting high-risk loans, which are a liability to the company and more important to accurately predict.
