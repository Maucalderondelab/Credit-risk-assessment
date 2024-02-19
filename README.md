# *Credit Risk*

## Introduction
Credit risk refers to the probability of loss due to a borrower's failure to repay any type of debt. Credit risk management is the practice of mitigating losses by assessing the adequacy of a bank's capital and loan reserves at any given time. This process has long been a challenge for financial institutions.

While it's impossible to predict exactly who will default on their obligations, proper assessment and management of credit risk can significantly reduce the severity of losses. The interest payments received from the borrower or issuer of a debt obligation represent the compensation investors earn for taking on credit risk.

While traditional methods heavily rely on the 5 Cs for credit risk assessment, which encompass *Character* (credit history), *Capacity* (income and debt), *Capital* (assets and net worth), *Collateral* (assets pledged as security), and *Conditions* (loan terms and economic environment), they can often be static and fail to capture the nuances of individual borrowers. Advancements in machine learning, particularly with robust and flexible models like XGBoost, offer exciting possibilities for more accurate and dynamic risk evaluation.

## Why XGBoost?

XGBoost stands for Extreme Gradient Boosting, a machine learning method specializing in both regression and classification tasks. It builds upon the concept of Gradient Boosting Decision Trees (GBDT), which are similar to Random Forests in their use of multiple decision trees for prediction. However, XGBoost takes GBDT to the next level by implementing several key enhancements:

* **Scalability :** Handles large datasets on multiple machines.
* **Performance :** Achieves higher accuracy by focusing on optimizing splitting criteria and minimizing the loss function.
* **Regularization:** Built-in regularization techniques prevent overfitting and improve model generalizability
* ## The data
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

## Identifying Outliers with Local Outlier Factor (LOF)
Before diving into dataset analysis, it's crucial to identify any potential outliers that might skew our analysis. To accomplish this, we'll implement the Local Outlier Factor (LOF), an unsupervised anomaly detection technique used to identify outliers and anomalies in a dataset. It measures the local deviation of the density of a given sample with respect to its neighbors. It's local in that the anomaly score depends on how isolated the object is with respect to the surrounding neighborhood. More precisely, locality is determined by k-nearest neighbors, whose distance is used to estimate the local density. By comparing the local density of a sample to the local densities of its neighbors, one can identify samples that have substantially lower density than their neighbors. These are considered outliers.
[https://scikit-learn.org/stable/modules/generated/sklearn.neighbors.LocalOutlierFactor.html]()

## One-Hot Encoding
This technique is crucial as it enables our machine learning algorithms to effectively utilize categorical data, which would otherwise be incompatible. It also ensures that the algorithms do not assign arbitrary numerical values to categories, which could lead to misinterpretations.

In our code, one-hot encoding is applied to the categorical variables in the dataset before training our machine learning models. This preprocessing step ensures that our models can accurately learn from and make predictions based on the categorical data present in the dataset.

![Data Distributton](https://github.com/Maucalderondelab/Credit-Risk-Assestment/blob/master/data-distribution.png)


![Feature importande](https://github.com/Maucalderondelab/Credit-Risk-Assestment/blob/master/Feature%20Importance.png)

![AUC-ROC](https://github.com/Maucalderondelab/Credit-Risk-Assestment/blob/master/Roc%20curve.png)

![Classification score](https://github.com/Maucalderondelab/Credit-Risk-Assestment/blob/master/Train%20and%20Validation%20Log%20Loss.png)


