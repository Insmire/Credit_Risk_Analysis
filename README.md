## Overview

The purpose of this project is to predict credit card risk using 2019 first quarter data. Past records indicate that credit card applications have a quantify imbalance in low-risk to high-risk loans. In order to reduce bias created from the weight of low-risk loans, we resample the data utilizing the naive random oversampling algorithm, synthetic minority oversampling technique (SMOTE) algorithm, cluster centroid undersamling algorithm, and synthetic minority oversampling technique edited nearest neighbors (SMOTEENN) combination sampling algorithm prior to fitting the resampled features and target to a logistic regression model. We further utilize machine learning models balanced random forest classifier and easy ensemble classifier to predict credit risk. Lastly we determine the performance of the model sampled by various approach with the evaluation metrics balanced accuracy score, confusion matrix, and imbalanced classification report.

---

## Resources

Data Source:

    LoanStats_2019Q1.csv

Software:

    imbalanced-learn version 0.7.0
    Jupyter Notebook version 1.0.0
    NumPy version 1.20.3
    Python  3.7.11
    SciPy version 1.7.1
    Scikit-learn version 0.24.2

---

## Results
<!-- Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all six machine learning models. Use screenshots of your outputs to support your results. -->

* Naive random oversampling

    - The balanced accuracy score is roughly 0.65.
    - The precision or positive predictive value (PPV) of the model is 0.01 for predicting high-risk applications and 1.00 for predicting low-risk applications.
    - The sensitivity or recall of the model is 0.71 for predicting high-risk applications and 0.59 for predicting low-risk applications.
    - The F1 score or harmonic mean of a high-risk prediction is 0.02; The F1 score of a low-risk prediction is 0.74.

![naive_random_oversample_eval_metrics](https://user-images.githubusercontent.com/96349090/166248191-46c1a8fa-4246-4fb1-884b-919d2af4dd62.png)


* Synthetic minority oversampling technique (SMOTE)

    - The balanced accuracy score is roughly 0.61.
    - The precision of the model is 0.01 for predicting high-risk applications and 1.00 for predicting low-risk applications.
    - The sensitivity of the model is 0.55 for predicting high-risk applications and 0.67 for predicting low-risk applications.
    - The F1 score of a high-risk prediction is 0.02; The F1 score of a low-risk prediction is 0.80.

![smote_eval_metrics](https://user-images.githubusercontent.com/96349090/166248228-5b87aab3-1138-45c1-b749-085bce777200.png)


* Cluster centroid undersampling

    - The balanced accuracy score is roughly 0.54.
    - The precision of the model is 0.01 for predicting high-risk applications and 1.00 for predicting low-risk applications.
    - The sensitivity of the model is 0.65 for predicting high-risk applications and 0.43 for predicting low-risk applications.
    - The F1 score of a high-risk prediction is 0.01; The F1 score of a low-risk prediction is 0.60.

![cluster_centroids_eval_metrics](https://user-images.githubusercontent.com/96349090/166248089-317a52d8-e29b-436f-b200-a462f1dc0825.png)


* Sythetic minority oversampling technique edited nearest neighbors (SMOTEENN)

    - The balanced accuracy score is roughly 0.65.
    - The precision of the model is 0.01 for predicting high-risk applications and 1.00 for predicting low-risk applications.
    - The sensitivity of the model is 0.71 for predicting high-risk applications and 0.59 for predicting low-risk applications.
    - The F1 score of a high-risk prediction is 0.02; The F1 score of a low-risk prediction is 0.74.

![smoteenn_eval_metrics](https://user-images.githubusercontent.com/96349090/166248257-928abafc-9923-4496-8d80-19f869c71fc9.png)


* Balanced radom forest classifier

    - The balanced accuracy score is roughly 0.68.
    - The precision of the model is 0.88 for predicting high-risk applications and 1.00 for predicting low-risk applications.
    - The sensitivity of the model is 0.37 for predicting high-risk applications and 1.00 for predicting low-risk applications.
    - The F1 score of a high-risk prediction is 0.52; The F1 score of a low-risk prediction is 1.00.

![balanced_random_forest_eval_metrics](https://user-images.githubusercontent.com/96349090/166248037-f176589a-d027-4bcf-bfa3-91592ce8a02b.png)


* Easy ensemble classifier

    - The balanced accuracy score is roughly 0.93.
    - The precision of the model is 0.09 for predicting high-risk applications and 1.00 for predicting low-risk applications.
    - The sensitivity of the model is 0.92 for predicting high-risk applications and 0.94 for predicting low-risk applications.
    - The F1 score of a high-risk prediction is 0.19; The F1 score of a low-risk prediction is 0.97.

![easy_ensemble_eval_metrics](https://user-images.githubusercontent.com/96349090/166248154-5410e40b-f6fe-4014-9a92-df7a1ce20215.png)


---

## Summary
<!-- Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. If you do not recommend any of the models, justify your reasoning. -->

Due to the nature of this project, we desire a higher predictability for accurately predicted high-risk applications (true positives) over accurately predicted low-risk applications (true negatives). We also desire a higher predictability of low-risk applications falsely predicted as high-risk (false positive) over high-risk applications falsely predicted as low-risk (false negatives). This implies that we would favor a model with high precision as opposed to high sensitivity. Notice that re-sampling data with the various algorithms affected very little of the accuracy, precision, and recall of the logistic regression model. The balanced accuracy scores of all four algorithms are below 0.7. Furthermore the precision is low while sensitivity is high. Comparatively, the balanced random forest classifier observed a precision even though its accuracy is below 0.7. The easy ensemble classifier shows a low precision of 0.09 and a high accuracy of 0.93. After examining the various approach, we recommend another machine learning model to obtain the desired metrics.
