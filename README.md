# Credit_Risk_Analysis
## Overview of Analysis
In this project, we were tasked with using machine learning algorithms to build a model to predict a potential customer's credit risk. A list of over 115,000 customers was provided which contained many fields of information such as their loan amount, interest rate, income, home ownership as well as thier loan status (low or high risk). Using the models we built, our aim is to predict the loan status of the customers using the other information provided. If the model is succesful in predicting the known customers loan statuses, it may be useful in predicting the loan status of future customers. 

# Sampling Techniques
| Sampling Technique | Balanced Accuracy Score |
| --- | --- |
| Oversampling | 0.62 |
| SMOTE Oversampling | 0.63 |
| Undersampling - Cluster Centroids | 0.51 |
| SMOTEENN | 0.63 |

# Ensemble Learning
| Ensemble Learner | Balanced Accuracy Score |
| --- | --- |
| Balanced Random Forest Classifier | 0.65 |
