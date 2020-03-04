# Credit Risk
## James Phalen

## jjp_credit_risk_resampling

1. The credit data was from the Lending Club.  It was first cleaned.  Columns with non-numeric data had to be identified and encoded using "get_dummies".
1. Loan_Status was chosen as the Y-variable since it is the binary result of the other features.
1. Naive Random Oversampling and Logistic Regression: setting the number of results - low risk and high risk- equal to the majority (51,352 each) and placed them into a logistic regression.  The result was a balanced accuracy score of 0.66127, high risk precision was 0.01 and recall was 0.66, which means that the model has many false positives, but the number of false negatives will have to be compared to the other models.  I will focus on high risk results because they are citical for a loan company to identify.
1. SMOTE Oversampling and Logistic Regression: setting the number of results of low and high risk equal to the majority, 51,352 each, using the SMOTE method based on the proximity of the points, the balanced accuracy score was 0.63769.  The overall results were close to the Naive Random Oversampling though they were not as strong, recall was in the low 0.60's and precision for high risk was 0.01, many false positives.
1. Cluster Centroids Undersampling and Logistic Regression: setting the high and low risk equal to eachother, but decreasing the quantity to the minority of 260 yielded a balanced accuracy score of 0.518859.  Recall levels were below 0.60 for both high and low risk and precision was 0.01 for high risk.  This mean there are still many false positves and the number of false negatives is increasing as well over the other methods.
1. Combination SMOTEENIN and Logistic Regression: this combined method set the high risk observations to 51,344 and low to 46,388.  The balanced accuracy score was 0.6365. High risk precision was 0.01 and recall was 0.74, the best of the methods.  There will be many false positives selected, but the amount of false negatives is the lowest, which means that the model is choosing high risk mostly, which means that there is less of a chance of a false negative.  This is good for a loan company who would want to identify high risk clients at all costs.

## jjp_credit_risk_ensemble

1. Random Oversampler:  The data was first oversampled, the high risk and low risk quantity match at 51,352 each.
1. Balanced Random Forest Classifier Model: this will add the weak learners together for the best model.  The balanced accuracy score was 0.8086, the precision for high risk was 0.05 and recall was 0.69.  Low risk scores were near perfect at 1.0 for precision and recall at 0.93.  This means that the mdoel is selecting high risk most of the time, even though incorrect.  The scores are inline with the Combination method above.
