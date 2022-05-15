# Module 12 Report Template

## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

* Explain the purpose of the analysis.
We have a dataset of historical lending activity from a peer-to-peer lending services company and we need to build a model to accurately classify the loans as healthy or high risk loans and predict the high risk loans. We want to minimize the cost associated with incorrect classification of loans and maximize the profit associated with the approving maximum healthy loans.
    
* Explain what financial information the data was on, and what you needed to predict.
The dataset has two classes of data - healthy and high risk loans.The dataset has also more details about the previous loans including the loan size, interest rate, borrower income, debt to income, number of accounts, derogatory marks and total debt. We need to use this information to identify healthy vs high risk loans.

* Provide basic information about the variables you were trying to predict (e.g., `value_counts`).
Credit Risk is imbalanced with healthy loans easily outnumbering risk loans - There are 75036 healthy loans and 2500 high risk loans in the data sets. We split the data into training and testing sets. The training sets has 58162 total loans with 56271 (96.77%) Healthy Loans and 1881 (3.23%) High Risk Loans.

* Describe the stages of the machine learning process you went through as part of this analysis. Briefly touch on any methods you used (e.g., `LogisticRegression`, or any resampling method).
Machine Learning Model 1: We build a Logistic Regression model that can identify the creditworthiness of borrowers using this imbalanced training data to predict the high risk loans.
Machine Learning Model 2: We build another Logistic Regression model using the resampled training data to predict high risk loans.


## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:

Logistic Regression with imbalance in training data.
Accuracy: 0.95 (95% accurate in predicting loans)
Precision for Healthy Loans: 1.00 (almost 100% accurate in the healthy loans predictions)
Recall for Healthy Loans: 0.99 (99% accurate in predicting healthy loans as healthy)
Precision for High Risk Loans: 0.85 (85% accurate in the high risk loans predictions)
Recall for High Risk Loans: 0.91 (91% accurate in predicting high risk loans as high risk)



* Machine Learning Model 2:
Logistic Regression that oversamples high risk loan data before training data.
Accuracy: 0.99 (99% accurate in predicting loans)
Precision for Healthy Loans: 1.00 (almost 100% accurate in the healthy loans prediction)
Recall for Healthy Loans: 0.99 (99% accurate in predicting healthy loans as healthy)
Precision for High Risk Loans: 0.84 (84% accurate in the high risk loans prediction)
Recall for High Risk Loans: 0.99 (99% accurate in predicting high risk loans as high risk))

## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
* Does performance depend on the problem we are trying to solve?

Machine Learning Model 2 performs better than the Machine Learning Model 1 overall and especially in terms of improved high risk loan prediction and it is recommened that Model 2 should be used for classifying the loans.

Machine Learning Model 2 improved the Machine Learning Model 1's accuracy of 95% to 99% primarily through better prediction of high risk loans.

The Precision and Recall for the Healthy Loans is the same for both the models.

We lose slightly on the precision for High Risk Loans (85% for Model 1 vs 84% for Model 2). So, model 2 has 1% more chance of wrongly predicting healthy loans as high risk loans. This can force the lending service to scrutinize the high risk loans to identify if they may actually be healthy. If they do so, there is a small penalty or cost associated with the extra processing of loans predicted as high risk loans. Otherwise, we have an opportunity cost of not approving healthy loans.

The recall for High Risk Loans improves from 91% (Model 1) to 99% (Model 2). So, with Model 2, 99% of the actual high risk loans are predicted accurately and only 1% of the actual high risk loans are classified as healthy loans. The risk and associated cost of default is reduced significantly.

Overall Model 2's 8% more likelihood of accurately predicting high risk loans as high risk far outweighs its 1% more chance of wrongly predicting health loans as high risk. The cost of default associated with approving high risk loans far outweights the loss of potential profit associated with not approving health loans. Therefore, Model 2 performs much better than the Model 1.