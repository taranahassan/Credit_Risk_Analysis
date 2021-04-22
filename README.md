# Credit_Risk_Analysis

## Overview of the analysis: 
Credit card credit data has been acquired from LendingClub, a peer-to-peer lending service company, to assist in evaluating which machine learning methods/algorithms offer the best predictions for credit risk.  This analysis will be used to help FastLending, another peer-to-peer lending service, who would like to introduce machine learning methods to their loan application process.  They believe this would be more efficient in time and accuracy to identify good candidates for loans and therefore reduce the default rates.

## Results: 
After the data was cleaned and preprocessed Six machine learning models have been used to identify the balanced accuracy scores and the precision and recall scores.
<br>
### Resampling models
The first 4 models below are based on resampling data; 75% training set and 25% testing set.
<br>
  1.  Random Oversampling <br>
  In this algorithm, the minority class is selected randomly and added to the training set until both majority and minority classes are balanced
  ![randomoversampling_class_count](https://user-images.githubusercontent.com/75437852/115750002-af1efc80-a365-11eb-801a-e9568e0538e4.PNG)
  <br>
  The results were:
        - Balanced accuracy score at 0.66 - the average recall obtained on each class
        - Precision:
              High Risk of 0.01
              Low Risk of 1.00
        - Recall:
              High Risk of 0.74
              Low Risk of 0.58
  ![randomoversampling](https://user-images.githubusercontent.com/75437852/115748801-821e1a00-a364-11eb-9867-8392562a97a2.PNG)
  <br>
  2.  SMOTE 
  3.  Undersampling
  4.  SMOTEENN


Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all six machine learning models. Use screenshots of your outputs to support your results.

## Summary: 
Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. If you do not recommend any of the models, justify your reasoning.
