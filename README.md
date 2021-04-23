# Credit_Risk_Analysis

## Overview of the analysis: 
Credit card credit data has been acquired from LendingClub, a peer-to-peer lending service company, to assist in evaluating which machine learning methods/algorithms offer the best predictions for credit risk.  This analysis will be used to help FastLending, another peer-to-peer lending service, who would like to introduce machine learning methods to their loan application process.  They believe this would be more efficient in time and accuracy to identify good candidates for loans and therefore reduce the default rates.

## Results: 
After the data was cleaned and preprocessed Six machine learning models have been used to identify the balanced accuracy scores and the precision and recall scores.
<br>
### Resampling Algorithms
The first 4 models below are based on resampling data.
<br>
  1.  Random Oversampling <br>
  In this algorithm, the minority class is selected randomly and added to the training set until both majority and minority classes are balanced. <br>
  <br>
  ![randomoversampling_class_count](https://user-images.githubusercontent.com/75437852/115762647-b21fea00-a371-11eb-81c0-4571054fa0bd.PNG)
  <br>
  The results were:
        - Balanced accuracy score at 0.66 - the average recall obtained on each class
        - Precision:
              High Risk of 0.01
              Low Risk of 1.00
        - Recall:
              High Risk of 0.74
              Low Risk of 0.58
              <br>
  ![randomoversampling](https://user-images.githubusercontent.com/75437852/115762686-bb10bb80-a371-11eb-825f-3b3b9b850827.PNG)
  <br>
  2.  SMOTE <br>
  This oversampling method is by creating synthetic points for the minority class based on the values of the neighboring instances.  As per the image below, the classes are balanced.<br>
  <br>
  ![smote_class_count](https://user-images.githubusercontent.com/75437852/115762714-c2d06000-a371-11eb-805a-515f90ccbf64.PNG)
<br>
  The results were:
        - Balanced accuracy score slightly better than previous model - 0.65
        - Precision:
              High Risk of 0.01
              Low Risk of 1.00
        - Recall:
              High Risk of 0.62
              Low Risk of 0.68
              <br>
  ![smote](https://user-images.githubusercontent.com/75437852/115767462-2e68fc00-a377-11eb-8acd-722ca7032ba4.PNG)
<br>
  3.  Cluster Centroid <br>
  The Cluster Centroid model is the opposite of the SMOTE model where the majority class is minimized (undersampled) to match the minority class by synthesizing points to match neighboring values.  This method balances both classes as well. <br.
  <br>
  ![undersampling_class_count](https://user-images.githubusercontent.com/75437852/115775996-991f3500-a381-11eb-802d-188a6355a41c.PNG)
<br>
  The results were:
        - Balanced accuracy score lower than both the oversampling models at 0.54
        - Precision:
              High Risk of 0.01
              Low Risk of 1.00
        - Recall:
              High Risk of 0.69
              Low Risk of 0.40
              <br>
   ![undersampling](https://user-images.githubusercontent.com/75437852/115776355-059a3400-a382-11eb-831e-2228356dbf63.PNG)
<br>  
  4.  SMOTEENN <br>
  In this algorithm, both the SMOTE concept and undersampling are combined.  After the SMOTE technique is completed, the outliers from each class are dropped.  Again resulting in a balanced set of classes.<br>
  <br>
![smoteen_class_count](https://user-images.githubusercontent.com/75437852/115777398-39c22480-a383-11eb-9eea-3fa6b90431f4.PNG)
<br>
  The results were:
        - Balanced accuracy score better at 0.68
        - Precision:
              High Risk of 0.01
              Low Risk of 1.00
        - Recall:
              High Risk of 0.77
              Low Risk of 0.59
              <br>
 ![smoteen](https://user-images.githubusercontent.com/75437852/115784672-721a3080-a38c-11eb-9a72-827ac067a380.PNG)
<br>
              <br>
### Ensemble Algorithms
The last 2 models are based on ensemble classifiers.
<br>
  5.  Balanced Random Forest Classifier <br>
  For this classifier, this model is able to provide a final predicition based on multiple predictions of smaller scale, each with a part of the data.  It randomly under_samples each bootstrap sample. <br>
  <br>
  The results are:
        - Balanced accuracy score of 0.74
        - Precision:
              High Risk of 0.06
              Low Risk of 1.00
        - Recall:
              High Risk of 0.52
              Low Risk of 0.95
              <br>
  ![forest](https://user-images.githubusercontent.com/75437852/115784610-5b73d980-a38c-11eb-8b18-a3db1a435e22.PNG)
    <br>
  6.  Easy Ensemble AdaBoost Classifier <br>
  In this model, the weak learners are combined into a strong learner.  Each model is then trained on any errors from the previous model. <br>
  <br>
  The results are:
        - Balanced accuracy score of 0.93
        - Precision:
              High Risk of 0.09
              Low Risk of 1.00
        - Recall:
              High Risk of 0.92
              Low Risk of 0.94

## Summary: 
In order to identify the best possible model to predict credit risk, the average F1 scores would need to be reviewed.  The F1 score would be more useful then the accuracy score since there is such an uneven class distribution.  <br>
In all the resampling algorithms, Cluster Centroid was the least optimal in predicting credit risk with an accuracy score of 0.54 and F1 score of 0.56.  So far the highest F1 score within the resampling models as the SMOTE method at 0.81, however looking at the accuracy score it is moderate at 0.65. <br>
There was not much of a difference in the F1 scores and accuracy scores between the Random Over Sampling and the SMOTEEN; both models faired moderately in predicting credit risk.  <br>
All resampling models precision scores were the same.
<br>
<br>
Between the two ensemble learners, both models had a good F1 score, though the accuracy score for the balanced random forest classifier was lower at 0.73.<br>
Thus far, looking at the weighted F1 scores, the Easy Ensemble AdaBoost Classifier had the highest score of 0.97 accuracy of prediction for each class.  Keeping in mind the balanced accuracy score is also high at 0.93.<br>
Though to analyze further; when focusing on the precision score individually, the high risk is quite low but the low risk precision is at its best.  This means the model wasn't optimal in predicting the high credit risk candidates.  But when looking at the recall scores, both high risk and low risk scores are high.  That means the model predicting both high and low risk was labeled correctly.

