## Overview

The purpose of this project is to utilize supervised machine learning to assist Fast Lending, a company that offers peer-to-peer lending service, to predict credit risk using the company's 2019 first quarter data. To this end, we begin by converting all qualitative data to numberical data before splitting the dataset for training and testing. Applications have a tendency to have an imbalance of high- and low-risk loans. So to reduce bias created from the weight of low-risk loans, we resample the data via various algorithms including the naive random oversampling algorithm, synthetic minority oversampling technique (SMOTE) algorithm, cluster centroids undersamling algorithm, and synthetic minority oversampling technique edited nearest neighbors (SMOTEENN) combination sampling algorithm prior to fitting the resampled data to a logistic regression model. Furthermore we fit the dataset to two other models, balanced random forest classifier and easy ensemble classifier to predict credit risk. Lastly we determine the performance of the model sampled by various approach with the evaluation metrics balanced accuracy score, confusion matrix, and imbalanced classification report.

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

![naive_random_oversampling_eval_metrics](https://user-images.githubusercontent.com/96349090/166645538-2bba12a9-c08f-4814-b1ce-00386786e81b.png)


* Synthetic minority oversampling technique (SMOTE)

    - The balanced accuracy score is roughly 0.61.
    - The precision of the model is 0.01 for predicting high-risk applications and 1.00 for predicting low-risk applications.
    - The sensitivity of the model is 0.55 for predicting high-risk applications and 0.67 for predicting low-risk applications.
    - The F1 score of a high-risk prediction is 0.02; The F1 score of a low-risk prediction is 0.80.

![smote_oversampling_eval_metrics](https://user-images.githubusercontent.com/96349090/166645584-6e9f5139-13b4-41b9-a97b-b1363fd4fd6a.png)


* Cluster centroids undersampling

    - The balanced accuracy score is roughly 0.54.
    - The precision of the model is 0.01 for predicting high-risk applications and 1.00 for predicting low-risk applications.
    - The sensitivity of the model is 0.65 for predicting high-risk applications and 0.43 for predicting low-risk applications.
    - The F1 score of a high-risk prediction is 0.01; The F1 score of a low-risk prediction is 0.60.

![cluster_centroids_undersampling_eval_metrics](https://user-images.githubusercontent.com/96349090/166645646-25065783-76ad-430a-9490-7d0e2f7b7778.png)


* Sythetic minority oversampling technique edited nearest neighbors (SMOTEENN)

    - The balanced accuracy score is roughly 0.65.
    - The precision of the model is 0.01 for predicting high-risk applications and 1.00 for predicting low-risk applications.
    - The sensitivity of the model is 0.71 for predicting high-risk applications and 0.59 for predicting low-risk applications.
    - The F1 score of a high-risk prediction is 0.02; The F1 score of a low-risk prediction is 0.74.

![smoteenn_combination_sampling_eval_metrics](https://user-images.githubusercontent.com/96349090/166645697-72c90ab6-7bbc-4db0-91e9-5712b71b9568.png)


* Balanced radom forest classifier

    - The balanced accuracy score is roughly 0.68.
    - The precision of the model is 0.88 for predicting high-risk applications and 1.00 for predicting low-risk applications.
    - The sensitivity of the model is 0.37 for predicting high-risk applications and 1.00 for predicting low-risk applications.
    - The F1 score of a high-risk prediction is 0.52; The F1 score of a low-risk prediction is 1.00.

![random_forest_eval_metrics](https://user-images.githubusercontent.com/96349090/166645752-c9767b81-8597-48cb-9a8f-dd1d915cc38f.png)


* Easy ensemble classifier

    - The balanced accuracy score is roughly 0.93.
    - The precision of the model is 0.09 for predicting high-risk applications and 1.00 for predicting low-risk applications.
    - The sensitivity of the model is 0.92 for predicting high-risk applications and 0.94 for predicting low-risk applications.
    - The F1 score of a high-risk prediction is 0.19; The F1 score of a low-risk prediction is 0.97.

![easy_ensemble_eval_metrics](https://user-images.githubusercontent.com/96349090/166645796-b76ad771-34e2-4667-8c4f-d64c1a01aa5a.png)


---

## Summary
<!-- Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. If you do not recommend any of the models, justify your reasoning. -->

Due to the nature of this project, we desire a higher predictability for accurately predicted high-risk applications (true positives) over accurately predicted low-risk applications (true negatives). We also desire a higher predictability of low-risk applications falsely predicted as high-risk (false positive) over high-risk applications falsely predicted as low-risk (false negatives). This implies that we would favor a model with high precision as opposed to high sensitivity. Notice that re-sampling data with the various algorithms affected very little of the accuracy, precision, and recall of the logistic regression model. The balanced accuracy scores of all four algorithms are below 0.7. Furthermore the precision is low while sensitivity is high. Comparatively, the balanced random forest classifier observed a precision even though its accuracy is below 0.7. The easy ensemble classifier shows a low precision of 0.09 and a high accuracy of 0.93. After examining the various approach, we recommend another machine learning model to obtain the desired metrics.
