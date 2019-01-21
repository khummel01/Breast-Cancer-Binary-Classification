# Breast-Cancer-Binary-Classification

[Data set taken from Kaggle](https://www.kaggle.com/uciml/breast-cancer-wisconsin-data)


## Abstract 

This report examines 569 breast masses using logistic regression methods. The primary goal is to determine what predictor variables are most effective at predicting the malignancy of a breast mass, as well as to see if there is a certain combination of predictor variables that most accurately predicts malignancy. The ten predictor variables were radius (mean of distances from center to points on the perimeter), texture (standard deviation of gray-scale values), perimeter, area, smoothness (local variation in radius lengths), compactness (perimeter^2/area – 1), concavity (severity of concave portions of the contour), symmetry, and fractal dimension (“coastline approximation”-1). We have thirty total predictor variables because the mean, standard error, and "worst" values were calculated for each of these ten variables. The worst value is the largest mean of the value for each predictor. The response variable was the diagnosis of malignant (represented by 1) or benign (represented by 0).

## Results

Our chosen final model contains six predictors: log.radius_worst, concavity_worst, smoothness_mean, log.texture_se, log.compactness_mean, and fractal_dimension_worst. The p-values of these predictors are 1.42e-13, 6.35e-05, 1.38e-05, 8.98e-05, 0.000479, and 0.152012 respectively. Log.radius_worst, concavity_worst, smoothness_mean, log.texture_se, log.compactness_mean are all significant to a false positive rate of $\alpha = .001$ while fractal_dimension_worst is not significant at all. 

**ROC curve using of final model using step-wise regression:**

![alt text](https://github.com/khummel01/Breast-Cancer-Binary-Classification/blob/master/images/roc_curve.png "ROC Curve")

The AUC value is for this model is 0.99352081. The ROC curve suggests the predictive ability of this model is better than random guessing, since the AUC (0.9935) is larger than 0.5. Our forward step-wise model with observation #69 removed can accurately distinguish between malignant and benign breast masses.

**Residuals of final model**:

![alt text](https://github.com/khummel01/Breast-Cancer-Binary-Classification/blob/master/images/residuals.png "Residuals")


## Conclusion

This analysis shows that the probability of a breast mass being malignant or benign can be accurately predicted from the log(worst radius), worst concavity, mean concavity, log(standard error of texture), log(mean compactness), and worst fractal dimension measurments of a digitalized image of a breast mass. The odds of a breast mass being malignant increases the most with each additional unit of log(radius worst) where each additional 0.15 unit of log(radius worst) increases the odds of a breast mass being malignant by approximately 58.1 times. The least influential factor is worst fractal dimension where each additional 0.015 unit increase in this predictor only increases the odds of a breast mass being malignant by 1.93 times. With an AUC value of 0.9935208, our model can accurately predict whether or not a breast mass is malignant or benign 99.25% of the time given this data set. These results could be used in the medical field to help predict whether or not a patient has breast cancer. 

## Follow-up Questions
1. Is this dataset representative of all types of breast cancers?

2. Is the scope of this data set large enough to conclude on the predictative abilities of each predictor variable?

3. Would other categorical factors such as patient's age, socio-economic status, and history of breast cancer in the family improve our model?

4. Would our model be able to predict with even higher accuracy the malignancy of a breast mass if it was trained on a much larger data set?
