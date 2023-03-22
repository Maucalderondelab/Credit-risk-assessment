# *Credit-Risk-Assestment*

## Introduction

Credit risk refers to the propability of loss due to a borrower's failure to make payments on any type of debt. Credit rist managment is the practice of mitigating losses by understanding the adequacy of a bank's capital and loan loss reserves at any given time, this is a process that has log been a challenge for financial institutions.

Although it's impossible to know exactly who will default on obligations, properly assessing and managing credit risk can lessen the severity of a loss. Interest payments from the borrower or issuer of a debt obligation are lender's or investor's reward for assuming credit risk.

Some of the key takeaways for credit risk are:

Credit risk is the possibility of lossing a lender takes on due to the possibility of a borrower not paying back a loan.

Consumer credit risk can be measured by five patameters: Credit history, capacity to repay, capital, the loan's conditions and associated collateral. These are more kwnown as the 5 Cs.

Consumers posing higher credit risk usually end up paying higher interest rates on loans.

## Why XGBoost?

First lets explain what is XGBoost. XGBoos stands for Extreme Gradiente Boosting, this is a scalable distributed gradient boosted decision tree machine learning library. It provides parallel tree boosting and is used for regression, classification and ranking problems.

So we can argue that a Gradient Boosting Decision Trees(GBDT) is a decision tree ensemble algorithm similar to random forest, for classification and regression. Ensemnle learning algorithms combine multiple machine learning algoriths to obtain a better model. The termn "gradient boosting" comes from the idea of improving a single weak model buy combining it with a number of other weak models in order to generate a collectively strong model. Gradient boosting is an extension of boosting where the process of additively generating weak models is formalized as gradient decent algorithm over an objetive weak models is formalized as gradient descent algorithm over an objective function. Gradient boosting sets targeted outcomes for the next model in an effort to minimize errors. Targeted outcomes for each case are based on the gradient error whit respect to the prediction.

GBDTs iteratively train an ensemble of shallow decision trees, with each iteration using the error residuals of the previous model to fit the next model.

## The data
For this proyect we are using a dataset from kaggle [Credit Risk Dataset](https://www.kaggle.com/datasets/laotse/credit-risk-dataset).

In this file we have 12 columns but only 9 contain usefull information:

1. Persons Age
2. Person Income
3. Home-Ownership
4. Person emp lenght
5. Loan intent
6. Loan grade
7. Loan amount
8. Loan interest rate
9. Loan status
10. Loan percent income
11. CB person default on file
12. CB person credit history lenght

