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
    - The precision or positive predictive value (PPV) of the model is 0.01 for predicting high risk applications and 1.00 for predicting low risk applications.
    - The sensitivity or recall of the model is 0.71 for predicting high risk applications and 0.59 for predicting low risk applications.
    - The F1 score or harmonic mean of a true positive prediction is 0.02; The F1 score of a true negative prediction is 0.74.

photo

* Synthetic minority oversampling technique (SMOTE)

    - The balanced accuracy score is roughly 0.61.
    - The precision of the model is 0.01 for predicting high risk applications and 1.00 for predicting low risk applications.
    - The sensitivity of the model is 0.55 for predicting high risk applications and 0.67 for predicting low risk applications.
    - The F1 score of a true positive prediction is 0.02; The F1 score of a true negative prediction is 0.80.

photo

* Cluster centroid undersampling

    - The balanced accuracy score is roughly 0.54.
    - The precision of the model is 0.01 for predicting high risk applications and 1.00 for predicting low risk applications.
    - The sensitivity of the model is 0.65 for predicting high risk applications and 0.43 for predicting low risk applications.
    - The F1 score of a true positive prediction is 0.01; The F1 score of a true negative prediction is 0.60.

photo

* Sythetic minority oversampling technique edited nearest neighbors (SMOTEENN)

    - The balanced accuracy score is roughly 0.65.
    - The precision of the model is 0.01 for predicting high risk applications and 1.00 for predicting low risk applications.
    - The sensitivity of the model is 0.71 for predicting high risk applications and 0.59 for predicting low risk applications.
    - The F1 score of a true positive prediction is 0.02; The F1 score of a true negative prediction is 0.74.

photo

* Balanced radom forest classifier

    - The balanced accuracy score is roughly 0.68.
    - The precision of the model is 0.88 for predicting high risk applications and 1.00 for predicting low risk applications.
    - The sensitivity of the model is 0.37 for predicting high risk applications and 1.00 for predicting low risk applications.
    - The F1 score of a true positive prediction is 0.52; The F1 score of a true negative prediction is 1.00.

photo

* Easy ensemble classifier

    - The balanced accuracy score is roughly 0.93.
    - The precision of the model is 0.09 for predicting high risk applications and 1.00 for predicting low risk applications.
    - The sensitivity of the model is 0.92 for predicting high risk applications and 0.94 for predicting low risk applications.
    - The F1 score of a true positive prediction is 0.19; The F1 score of a true negative prediction is 0.97.

photo

---

## Summary
<!-- Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. If you do not recommend any of the models, justify your reasoning. -->

Due to the nature of this project, we desire a higher predictability for accurately predicted high-risk applications (true positives) over accurately predicted low-risk applications (true negatives). We also desire a higher predictability of low-risk applications falsely predicted as high-risk (false positive) over high-risk applications falsely predicted as low-risk (false negatives). Notice that re-sampling data with the various algorithms affected very little of the accuracy, precision, and recall of the logistic regression model. All three metrics 