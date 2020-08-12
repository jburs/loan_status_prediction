# loan_status_prediction
python, machine learning

A machine learning analysis was performed on a data set with information on low and high risk loans. 
The data was cleaned, and labelencoded for use with imblearn.ensemble EasyEnsembleClassifier, and imblearn.ensemble BalancedRandomForestClassifier. 


## Classifier Choice

Of the two sampling methods, BalancedRandomForestClassifier had an accuracy score of .673, while EasyEnsembleClassifier had the higher score of .905. Of the two methods, EasyEnsembleClassifier got 90.5% of its predictions correct for to the testing data. Accuracy is not the most important identifier as the dataset is heavily skewed towards low risk loans, 68470 data points compared to 347 high risk data points. due to the very large sample number difference, accuracy is mostly a representation of the nubmer of currect low risk predictions, instead of the model as a whole. 

Precision is a measuer of how reliable a positive classification is. Of the two models, both had a prediction of 1.0 for low risk loans, BalancedRandomForestClassifier had a precision of 0.83 for high risk loans, and EasyEnsembleClassifier had a precision of 0.14 for high risk loans. Therefore, BalancedRandomForestClassfier is far more accurate in iddentifying true high risk loans, and EasyEnsembleClassifier had a high number of high risk predictions which were actually low risk. 

Recall measures the sensitivity of the model to false negitaves. Of the two models, both had a recall of aproximately 1.0 for low risk predictions. For high risk predictions, the BalancedRandomForestClassifier had a recall of 0.35, and EasyEnsembleClassifier had a recakll of 0.84. The EasyEnsembleClassifier had far fewer false negatives than the BalancedRandomForestClassifier, and is more accurate at correctly predicting high risk loans. 
  
When predicting loan risk, it is important to correctly identift high risk loans by minimizing the number of false negatives (high risk identified as low risk) in order to minimize losses when the loans default. Therefore, Recall is the most important statistic as it is directly related to false negatives. The classifier best suited for this analysis, is the EasyEnsembleClassifier with a recall of 0.84. 


## Sampling Method

The dataset is heavily skewed towards Low risk, 68470 data points compared to 347 high risk data points. Four sampling methods were tested to fix the imbalance; RandomOverSampler, SMOTE oversampler, ClusterCentroids undersampling, and a combination of over and undersampling SMOTEENN. These sampling methods were each tested with LogisticRegression classifier and the same random_state. 

As mentioned previously, recall is the most imporntant statistic to minimize losses caused by high risk loans being calssified as low risk and defaulting. Of the four sampling methods, they each had a similar accuracy of aprox 0.68, except for clustercentroids undersampling which had a lower accuracy of 0.54.  All of the sampling methods had the same precision, 0.01 for high risk, and 1.00 for low risk. Low risk recall: RandomOverSampler 0.61, SMOTE 0.65, ClusterCentroids 0.68, SMOTEENN 0.58. High risk recall: RandomOverSampler 0.71, SMOTE 0.65, ClusterCentroids 0.68, SMOTEENN 0.73. 

Of the two recall values, high risk recall is the most valuable since it is a measure of true positives and fewset false negatives. Minimizing false negatives will minimiz the number of high risk calssified as low risk, and minimize loss from those loans defaulting. Therefore, the best samplind method is SMOTEENN, the combination of over and undersampling, as it has the highest recall for high risk loans. 




