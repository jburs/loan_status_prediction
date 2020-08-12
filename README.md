# loan_status_prediction
python, machine learning

A machine learning analysis was performed on a data set with information on low and high risk loans. 
The data was cleaned, and labelencoded for use with imblearn.ensemble EasyEnsembleClassifier, and imblearn.ensemble BalancedRandomForestClassifier. 


## Classifier Choice

Of the two sampling methods, BalancedRandomForestClassifier had an accuracy score of .673, while EasyEnsembleClassifier had the higher score of .905. Of the two methods, EasyEnsembleClassifier got 90.5% of its predictions correct for to the testing data.

Precision is a measuer of how reliable a positive classification is. Of the two models, both had a prediction of 1.0 for low risk loans, BalancedRandomForestClassifier had a precision of 0.83 for high risk loans, and EasyEnsembleClassifier had a precision of 0.14 for high risk loans. Therefore, BalancedRandomForestClassfier is far more accurate in iddentifying true high risk loans, and EasyEnsembleClassifier had a high number of high risk predictions which were actually low risk. 

Recall measures the sensitivity of the model to false negitaves. Of the two models, both had a recall of aproximately 1.0 for low risk predictions. For high risk predictions, the BalancedRandomForestClassifier had a recall of 0.35, and EasyEnsembleClassifier had a recakll of 0.84. The EasyEnsembleClassifier had far fewer false negatives than the BalancedRandomForestClassifier, and is more accurate at correctly predicting high risk loans. 
  
When predicting loan risk, it is important to correctly identift high risk loans by minimizing the number of false negatives (high risk identified as low risk) in order to minimize losses when the loans default. Therefore, Recall is the most important statistic as it is directly related to false negatives. The classifier best suited for this analysis, is the EasyEnsembleClassifier with a recall of 0.84. 


## Sampling Method


