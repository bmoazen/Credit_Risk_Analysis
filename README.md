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
Shown below is a table of the balanced accuracy, precision, and recall scores for logistic regression models using training data taken by each sampling technique where HR is "high-risk" and LR is "low-risk"

| Sampling Technique | Balanced Accuracy | Precision | Recall | Link to Classification Report |
| --- | --- | --- | --- | --- |
| Oversampling | 0.62 | HR 0.01 <br> LR 1.00 | HR 0.59 <br> LR 0.65 | [oversampling_cr](./Results/oversampling_cr.PNG) |
| SMOTE Oversampling | 0.63 | HR 0.01 <br> LR 1.00 | HR 0.62 <br> LR 0.65 | [smote_cr](./Results/smote_cr.PNG) |
| Undersampling | 0.51 | HR 0.01 <br> LR 0.99 | HR 0.59 <br> LR 0.42 | [undersampling_cr](./Results/undersampling_cr.PNG) |
| SMOTEENN | 0.63 | HR 0.01 <br> LR 1.00 | HR 0.62 <br> LR 0.65 | [smoteen_cr](./Results/smoteenn_cr.PNG) |

# Ensemble Learning
Ensemble learning uses several models together to boost the overall predictive power of the final model. Beginning with an initial model, a second model is then developed incorporating the errors of the first model.
| Ensemble Learner | Balanced Accuracy | Precision | Recall |
| --- | --- | --- | --- |
| Balanced Random Forest Classifier | 0.65 | HR 0.57 <br> LR 1.00 | HR 0.3 <br> LR 1.00 |

# Summary
In deciding which model to use, it is important to remember that there are almost 200 times more low-risk customers in the data set as there are high-risk.  While a high-risk customer may default on a loan, costing the company money, that money may be "made up" given a sufficient number of loans that are fully paid back. For this reason, it may be much more important to be able to accurately identify potential customers who would be low-risk, rather than making sure that potential high-risk customers are identified correctly. The recall statistic answers the question: what proportion of actual positives were identified correctly? From the above tables, we can see that the Balanced Random Forest Classifier has, by far, the highest recall statistic for the low-risk predictions. It accurately identifies all of the low-risk customers, thus giving the company a great chance of predicting if a potential customer would be low-risk. Futhermore, the other models have recall scores at 65% percent or lower - meaning 35 percent or more of actual low-risk customers will be misidentified as high-risk. That has the potential of mistankingly turning thousands of customers away. 
