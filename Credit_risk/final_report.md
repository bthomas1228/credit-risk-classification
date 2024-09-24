# Module 20 Report 

## Overview of the Analysis

Following is a description of the analysis completed for the machine learning model used in this Challenge 20:

* The purpose of the analysis was to train and evaluate a model based on historical lending activity data in order to build a model that can identify (predict) a if a borrower is likely to default on their loan.
* The financial dataset included data points describing historical lending activity and included loan details such as the interest rate and loan size as well as information about the borrower including income, debt to income ratio, number of accounts, derogatory marks, total debt and the outcome of the loan (healthy vs defaulted).
* Based on historical lending activity including the parameters associated with indiviudals that carried healthy loans and the traits of individuals that defaulted, the goal was to predict who in the future would be high or low risk to default on their loan (variables = healthy/non-likely to default and high-risk/defaulters).
* The stages of the machine learning process that were used as part of this analysis included reading in the lending activity as a csv file into a Pandas dataframe using python. The data set was then separated into two variables: y = the labels (loan status - if a borrower carried a healthy loan or defaulted as 0 or 1) and x = all the other borrower data as the features. The data was then split into training and testing datasets using train_test_split and a random state of 1. A logistic regression model was fit using the training data (X_train and y_train). A prediction was made using the testing data and saved. The model's performance was evaluated by generating a confusion matrix (to generate true and false positives and negatives) and a classifiation report.


## Results

Following is a description of accuracy scores and the precision and recall scores for the machine learning model.
* Accuracy: how often did the model "get it right" or predict the correct outcome; in this case accuracy was 99% suggesting the model predicts loan status correction almost 100% of the time
* Precision was high for both variables. Of the loans predicted to be healthy, 100% were actually healthy and of the loans predicted to default, 87% actually did. 
* Recall (sensitivity) scores were also high with both variables. Out of all the actual healthy loans issued, the model predicted this outcome 100% of the time whereas out of all the defaulted loans issued, the model correctly predicted this 89% of the time. 
* The f1-scores for both healthy and at-risk variables were high at 100% and 88% respectively.
* Overall because precision, recall and f1-scores were all high in both variables, the model performs well.


## Summary

Out of all the loans predicted to be healthy, 100% actually were healthy (precision). Out of all the actual healthy loans, the model predicted this outcome 100% of the time (recall/sensitivity). The f1-score for predicting a healthy loan is 1 (perfect score) suggesting this model does a great job of predicting if a loan will be healthy. In total there were 18759 healthy loans.

Out of all the loans predicted to be high-risk, 87% were actually high risk (precision). Out of all the actual high-risk (defaulted) loans, the model predicted this 89% of the time (recall/sensitivity). The f1-score for predicting a high-risk (defaulted) loan was 88% which is high but not as high as the predictive performance for healthy loans. There were only 625 high-risk (defaulted) loans.

All of this suggests the model performs well overall in both categories, supported by an accuracy of 99% (the model got it right almost all the time). The model performs a little better at predicting healthy loans than high-risk loans given the precision, recall and f1-score differences. However, this could be do to sample size given that there were only 625 loans issued that ended updefaulting to 18759 healthy loans issued. The difference in sample size could skew the performance metrics.

Model performance could be improved if more people defaulted on their loans because there would be more people to include in the training data set for that variable. The total n for this dataset was 625 which was far less than the borrowers who maintained healthy lending practices (n=18759). But this is also the goal of the model - to predict defaulters before issuing the loan. So, the problem we are trying to solve is depedent on the problem persisting in order to obtain data to improve the model. 

In general, the performance metrics associated with the model were quite good, even for the targeted borrower group (defaulters), enough to recommend the model for use by banks/lenders as it held an overall accuracy of 99% which is tough to beat. There is a low chance of lending to an individual who will default who is not idenitified by the model.


