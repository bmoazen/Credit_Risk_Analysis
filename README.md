# Credit_Risk_Analysis
## Overview of Analysis
In this project, we were tasked with using machine learning algorithms to build a model to predict a potential customer's credit risk. A list of over 115,000 customers was provided which contained many fields of information such as their loan amount, interest rate, income, home ownership as well as their loan status (issued, low or high risk). Using the models we built, our aim is to predict the loan status of the low- and high-risk customers using the other information provided. If the model is succesful in predicting the known customers loan statuses, it may be useful in predicting the loan status of future customers. 

# Sampling Techniques <br/>
The data we were given had a large imbalance between the number of high-risk customers (347) and low-risk customers (over 68K). Since the machine learning algorithms use a training set taken as a subset of the overall data, the likelihood of having the high-risk customers picked as part of the training set was very low compared to low-risk customers. For this reason, different sampling methods which take this imbalance into account were utilized. These sampling techniques use stratification to assure equal representation of the two clusters (low- and high-risk) in the training set.
<br />
The four sampling techniques utilized were:<br />
- Oversampling
- Synthetic Minority Oversampling Technique (SMOTE)
- Undersampling (Cluster Centroids)
- Synthetic Minority Oversampling Technique with Edited Nearest Neighbor (SMOTEENN)<br/> combines over- and under-sampling using SMOTE and Edited Nearest Neighbors

<br/>
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
