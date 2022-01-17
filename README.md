## Overview of Analysis
In this project, we were tasked with using machine learning algorithms to build a model to predict a potential customer's credit risk. A list of over 115,000 customers was provided which contained many fields of information such as their loan amount, interest rate, income, home ownership as well as their loan status (issued, low or high risk). Using the models we built, our aim is to predict the loan status of the low- and high-risk customers using the other information provided. If the model is succesful in predicting the known customers loan statuses, it may be useful in predicting the loan status of future customers. 

# Sampling Techniques <br/>
The data we were given had a large imbalance between the number of high-risk customers (347) and low-risk customers (over 68K). Since the machine learning algorithms use a training set taken as a subset of the overall data, the likelihood of having the high-risk customers picked as part of the training set was very low compared to low-risk customers. For this reason, different sampling methods which take this imbalance into account were utilized. These sampling techniques use stratification to assure equal representation of the two clusters (low- and high-risk) in the training set.
<br />
The four sampling techniques utilized were:
- Oversampling<br/> supplements the training data set with copies of the unrepresented class (in this case low-risk)
 - Synthetic Minority Oversampling Technique (SMOTE)<br />SMOTE creates "synthetic data" which selects data points from the underrepresented class, then uses lines between them to create additional points for sampling
- Undersampling (Cluster Centroids)<br /> creates "clusters" using averages of nearby points of the over-represented class, essentially reducing their influence in the model
- Synthetic Minority Oversampling Technique with Edited Nearest Neighbor (SMOTEENN)<br/> combines over- and under-sampling using SMOTE and Edited Nearest Neighbors (ENN)
<br />
Shown below is a table of the balanced accuracy scores for logistic regression models using training data taken by each sampling technique where HR is "high-risk" and LR is "low-risk"

| Sampling Technique | Balanced Accuracy | Precision | Recall |
| --- | --- | --- | --- |
| Oversampling | 0.62 | HR 0.01 <br> LR 1.00 | HR 0.59 <br> LR 0.65 |
| SMOTE Oversampling | 0.63 | HR 0.01 <br> LR 1.00 | HR 0.62 <br> LR 0.65 |
| Undersampling | 0.51 | HR 0.01 <br> LR 0.99 | HR 0.59 <br> LR 0.42 |
| SMOTEENN | 0.63 | HR 0.01 <br> LR 1.00 | HR 0.62 <br> LR 0.65 |

# Ensemble Learning
| Ensemble Learner | Balanced Accuracy Score |
| --- | --- |
| Balanced Random Forest Classifier | 0.65 |
| Undersampling - Cluster Centroids | 0.51 ||
