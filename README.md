# Credit_Risk_Analysis

## Overview of the analysis: 
Credit card credit data has been acquired from LendingClub, a peer-to-peer lending service company, to assist in evaluating which machine learning methods/algorithms offer the best predictions for credit risk.  This analysis will be used to help FastLending, another peer-to-peer lending service, who would like to introduce machine learning methods to their loan application process.  They believe this would be more efficient in time and accuracy to identify good candidates for loans and therefore reduce the default rates.
<br>
<br>
## Results: 
After the data was cleaned and preprocessed Six machine learning models have been used to identify the balanced accuracy scores and the precision and recall scores. <br>
<br>
### Resampling Algorithms
The first 4 models below are based on resampling data.
<br>
1.  **Random Oversampling:**  In this algorithm, the minority class is selected randomly and added to the training set until both majority and minority classes are balanced. <br> 

![randomoversampling_class_count](https://user-images.githubusercontent.com/75437852/115762647-b21fea00-a371-11eb-81c0-4571054fa0bd.PNG) <br>
  
The results were:
  * Balanced accuracy score at 0.66 - the average recall obtained on each class
  * Precision:  High Risk of 0.01 and Low Risk of 1.00
  * Recall:  High Risk of 0.74 and Low Risk of 0.58

![randomoversampling](https://user-images.githubusercontent.com/75437852/115762686-bb10bb80-a371-11eb-825f-3b3b9b850827.PNG)<br>
  <br>
  <br>
2.  **SMOTE:**  This oversampling method is by creating synthetic points for the minority class based on the values of the neighboring instances.  As per the image below, the classes are balanced.<br>

![smote_class_count](https://user-images.githubusercontent.com/75437852/115762714-c2d06000-a371-11eb-805a-515f90ccbf64.PNG)<br>

The results were:
  * Balanced accuracy score slightly better than previous model - 0.65
  * Precision:  High Risk of 0.01 and Low Risk of 1.00
  * Recall:  High Risk of 0.62 and Low Risk of 0.68


![smote](https://user-images.githubusercontent.com/75437852/115767462-2e68fc00-a377-11eb-8acd-722ca7032ba4.PNG)<br>
<br>
<br>
3.  **Cluster Centroid:**  The Cluster Centroid model is the opposite of the SMOTE model where the majority class is minimized (undersampled) to match the minority class by synthesizing points to match neighboring values.  This method balances both classes as well. <br>

![undersampling_class_count](https://user-images.githubusercontent.com/75437852/115775996-991f3500-a381-11eb-802d-188a6355a41c.PNG)<br>

The results were:<br>
  * Balanced accuracy score lower than both the oversampling models at 0.54
  * Precision:  High Risk of 0.01 and Low Risk of 1.00
  * Recall:  High Risk of 0.69 and Low Risk of 0.40

              
![undersampling](https://user-images.githubusercontent.com/75437852/115776355-059a3400-a382-11eb-831e-2228356dbf63.PNG)<br>
<br>
<br>
4.  **SMOTEEN:**  In this algorithm, both the SMOTE concept and undersampling are combined.  After the SMOTE technique is completed, the outliers from each class are dropped.  Again resulting in a balanced set of classes.<br>

![smoteen_class_count](https://user-images.githubusercontent.com/75437852/115777398-39c22480-a383-11eb-9eea-3fa6b90431f4.PNG)<br>

The results were:<br>
  * Balanced accuracy score better at 0.68
  * Precision:  High Risk of 0.01 and Low Risk of 1.00
  * Recall:  High Risk of 0.77 and Low Risk of 0.59

              
![smoteen](https://user-images.githubusercontent.com/75437852/115784672-721a3080-a38c-11eb-9a72-827ac067a380.PNG)<br>
<br>
<br>
### Ensemble Algorithms
The last 2 models are based on ensemble classifiers.
<br>
<br>
5.  **Balanced Random Forest Classifier:**  For this classifier, this model is able to provide a final predicition based on multiple predictions of smaller scale, each with a part of the data.  It randomly under_samples each bootstrap sample. <br>

The results are:<br>
  * Balanced accuracy score of 0.74
  * Precision:  High Risk of 0.03 and Low Risk of 1.00
  * Recall:  High Risk of 0.52 and Low Risk of 0.95

              
![forest](https://user-images.githubusercontent.com/75437852/115803785-95a2a280-a3af-11eb-9dd2-9293dc76fffe.PNG)<br>
    <br>
    <br>
6.  **Easy Ensemble AdaBoost Classifier:**  In this model, the weak learners are combined into a strong learner.  Each model is then trained on any errors from the previous model. <br>

The results are:
  * Balanced accuracy score of 0.93
  * Precision:  High Risk of 0.09 and Low Risk of 1.00
  * Recall:  High Risk of 0.92 and Low Risk of 0.94<br>

![booster](https://user-images.githubusercontent.com/75437852/115803808-9e937400-a3af-11eb-9366-eeeae3f51186.PNG)<br>
<br>

## Summary: 
In order to identify the best possible model to predict credit risk, the average F1 scores would need to be reviewed.  The F1 score would be more useful then the accuracy score since there is such an uneven class distribution.  For this analysis, we will focus on the F1 high risk score particularly since we want to establish the high risk candidates accurately.<br>
In all the resampling algorithms, Cluster Centroid was the least optimal in predicting credit risk with an accuracy score of 0.54 and F1 high risk score of 0.01.  So far the highest F1 score within the resampling models is the SMOTE method at 0.81, accuracy score at 0.65 and a low F1 high risk score of 0.02.<br>
There was not much of a difference in the F1 scores and accuracy scores between the Random Over Sampling and the SMOTEEN; both models faired moderately in predicting credit risk, however looking individually at the F1 high score, both models were low in predicting the high risk applicants.  <br>
<br>
Between the two ensemble learners, both models had a good F1 score, though the accuracy score for the balanced random forest classifier was lower at 0.73.  
To analyze further; when focusing on the F1 high risk score individually, the high risk is quite low but the low risk precision is at its best.  This means the model wasn't optimal in predicting the high credit risk candidates.  But when looking at the recall scores, both high risk and low risk scores are high.  That means the model predicting both high and low risk was labeled correctly. <br>
Thus far, none of the models are optimal to analyze high risk candidates.<br>
