# *Credit-Risk-Assestment*

## Introduction

Credit risk refers to the probability of loss due to a borrower's failure to make payments on any type of debt. Credit risk management is the practice of mitigating losses by understanding the adequacy of a bank's capital and loan loss reserves at any given time. This is a process that has long been a challenge for financial institutions.

Although it's impossible to know exactly who will default on obligations, properly assessing and managing credit risk can lessen the severity of a loss. Interest payments from the borrower or issuer of a debt obligation are the lender's or investor's reward for assuming credit risk.

Some of the key takeaways for credit risk are:

* Credit risk is the possibility of a loss a lender takes on due to the possibility of a borrower not paying back a loan.
* Consumer credit risk can be measured by five parameters: credit history, capacity to repay, capital, the loan's conditions, and associated collateral. These are more commonly known as the 5 Cs.
* Consumers posing a higher credit risk usually end up paying higher interest rates on loans.

## Why XGBoost?

First, let's explain what XGBoost is. XGBoost stands for Extreme Gradient Boosting. It is a scalable distributed gradient-boosted decision tree machine learning library used for regression, classification, and ranking problems. It provides parallel tree boosting.

We can argue that Gradient Boosting Decision Trees (GBDT) is a decision tree ensemble algorithm similar to random forest for classification and regression. Ensemble learning algorithms combine multiple machine learning algorithms to obtain a better model. The term "gradient boosting" comes from the idea of improving a single weak model by combining it with a number of other weak models to generate a collectively strong model. Gradient boosting is an extension of boosting where the process of additively generating weak models is formalized as a gradient descent algorithm over an objective function. Gradient boosting sets targeted outcomes for the next model in an effort to minimize errors. Targeted outcomes for each case are based on the gradient error with respect to the prediction.

GBDTs iteratively train an ensemble of shallow decision trees, with each iteration using the error residuals of the previous model to fit the next model. The final prediction is a weighted sum of all the tree predictions. Random forest "bagging" minimizes the variance and overfitting, while GBDT "boosting" minimizes the bias and underfitting.

XGBoost is a scalable and highly accurate implementation of gradient boosting that pushes the limits of computing power for boosted algorithms. It is built largely for energizing machine learning model performance and computational speed. With XGBoost, trees are built in parallel instead of sequentially like GBDT. It follows a level-wise strategy, scanning across gradient values and using the partial sums to evaluate the quality of splits at every possible split in the training set.


## The data
For this proyect we are using a dataset from kaggle [Credit Risk Dataset](https://www.kaggle.com/datasets/laotse/credit-risk-dataset).

In this file we have 32581 rows and 12 columns. Each columns represent a frature:

| Feature Name              | Desciption             |
| ------------------------- | ---------------------- |
| persons_age               | Age                    |
| person_income             | Annual income          |
| peron_home_ownership      | Home ownership         |
| persin_emp_lenght         | Employment length      |
| loan_intent               | Loan intent            |
| loan_grade                | Loan grade             |
| loan_amnt                 | Loan amount            |
| loan_int_rate             | Interest rate          |
| loan_status               | Loan status            |
| loan_percent_income       | Percent income         | 
| cb_person_default_on_file | Historical default     |
| cd_person_cred_hist_lengt | Credist history length |


In our dataset, we have identified a few features that are not useful for our analysis. To streamline our analysis, the first step we take is to remove these columns, namely "person_home_ownership," "loan_intent," "loan_grade," and "cb_person_default_on_file." We then replace these features with dummy variables using a specific procedure. This results in a total of 26 features for our analysis. The image below illustrates the importance of each of these features during the training of our model.


![Feature importance](https://user-images.githubusercontent.com/86662665/227045482-2ffa1ce7-1687-40b6-8b08-9488eef58a62.png)

Next we show the ROC curve. An ROC (Receiver Operating Characteristic) curve is a graphical representation of the performance of a binary classification model.

It shows the trade-off between the true positive rate (TPR) and the false positive rate (FPR) for different thresholds used by the model. The TPR, also known as sensitivity or recall, is the proportion of positive samples correctly classified as positive. The FPR is the proportion of negative samples incorrectly classified as positive.

An ROC curve plots the TPR on the y-axis and the FPR on the x-axis. The curve shows how the TPR and FPR change as the classification threshold is varied. The closer the curve is to the top-left corner of the plot, the better the performance of the model, as it indicates a higher TPR and lower FPR for all possible thresholds.

![ROC curve](https://user-images.githubusercontent.com/86662665/227044310-e0384e51-d741-4f7b-8c08-27b82f2f0862.png)

Finally the clasification report of the XGBoost model shows an accuracy of 93%, and here is a table that shows a [classification score](https://medium.com/analytics-vidhya/accuracy-vs-f1-score-6258237beca2):

| Acurracy               |   0.93%  |
|------------------------|----------|

|   | Precision | Recall | f1-score | 
|---|-----------|--------|----------|
| 0 |   0.93    |  0.99  |   0.96   |
| 1 |   0.96    |  0.70  |   0.81   |



