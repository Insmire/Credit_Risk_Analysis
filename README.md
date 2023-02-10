## Overview

The purpose of this project is to utilize supervised machine learning to assist Fast Lending, a company that offers peer-to-peer lending service, to predict credit risk using the company's 2019 first-quarter data. This data contains 86 variables, including features and the target, and a total of 68,817 applications. 

I begin by converting all qualitative data to numerical data before splitting the dataset into training and testing sets. Applications tend to have an imbalance of quantity between high- and low-risk loans. Thus to reduce bias created by the weight of low-risk loans, I re-sample the data via various algorithms including the naive random over-sampling algorithm, synthetic minority over-sampling technique (SMOTE) algorithm, cluster centroids under-sampling algorithm, and synthetic minority over-sampling technique edited nearest neighbors (SMOTEENN) combination sampling algorithm, before fitting the re-sampled data to a logistic regression model. I also fit the dataset to two other models, balanced random forest classifier and easy ensemble classifier. Lastly, I employ the evaluation metrics, balanced accuracy score, confusion matrix, and imbalanced classification report, to determine the performance of each algorithm or model.

---

## Results
<!-- Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all six machine learning models. Use screenshots of your outputs to support your results. -->

<!-- put results into a table for all algorithms? check bootcamp reviewer notes to confirm my interpretation of numbers are correct first
| |
| |
| | -->

* Naive random over-sampling algorithm with logistic regression model

    - The balanced accuracy score is roughly 0.64.
    - The precision, or positive predictive value (PPV), of the model is 0.01 and the sensitivity, or recall, of the model is 0.69 for predicting high-risk applications.
    - The precision is 1.00 and the sensitivity is 0.59 for predicting low-risk applications.
    - The F1 score or harmonic mean of a high-risk prediction is 0.02; the F1 score of a low-risk prediction is 0.74.

![naive_random_oversampling_eval_metrics](https://user-images.githubusercontent.com/96349090/166645538-2bba12a9-c08f-4814-b1ce-00386786e81b.png)


* Synthetic minority over-sampling technique (SMOTE) algorithm with logistic regression model

    - The balanced accuracy score is roughly 0.66.
    - The precision is 0.01 and the sensitivity is 0.63 for predicting high-risk applications.
    - The precision is 1.00 and the sensitivity is 0.69 for predicting low-risk applications.
    - The F1 score of a high-risk prediction is 0.02; the F1 score of a low-risk prediction is 0.82.

![smote_oversampling_eval_metrics](https://user-images.githubusercontent.com/96349090/166645584-6e9f5139-13b4-41b9-a97b-b1363fd4fd6a.png)


* Cluster centroids under-sampling algorithm with logistic regression model

    - The balanced accuracy score is roughly 0.54.
    - The precision is 0.01 and the sensitivity is 0.69 for predicting high-risk applications.
    - The precision is 1.00 and the sensitivity is 0.40 for predicting low-risk applications.
    - The F1 score of a high-risk prediction is 0.01; the F1 score of a low-risk prediction is 0.57.

![cluster_centroids_undersampling_eval_metrics](https://user-images.githubusercontent.com/96349090/166645646-25065783-76ad-430a-9490-7d0e2f7b7778.png)


* Synthetic minority over-sampling technique edited nearest neighbors (SMOTEENN) algorithm with logistic regression model

    - The balanced accuracy score is roughly 0.67.
    - The precision is 0.01 and the sensitivity is 0.76 for predicting high-risk applications.
    - The precision is 1.00 and the sensitivity is 0.59 for predicting low-risk applications.
    - The F1 score of a high-risk prediction is 0.02; the F1 score of a low-risk prediction is 0.74.

![smoteenn_combination_sampling_eval_metrics](https://user-images.githubusercontent.com/96349090/166645697-72c90ab6-7bbc-4db0-91e9-5712b71b9568.png)


* Balanced radom forest classifier model

    - The balanced accuracy score is roughly 0.68.
    - The precision is 0.88 and the sensitivity is 0.37 for predicting high-risk applications.
    - The precision is 1.00 and the sensitivity is 1.00 for predicting low-risk applications.
    - The F1 score of a high-risk prediction is 0.52; the F1 score of a low-risk prediction is 1.00.

![random_forest_eval_metrics](https://user-images.githubusercontent.com/96349090/166645752-c9767b81-8597-48cb-9a8f-dd1d915cc38f.png)


* Easy ensemble classifier model

    - The balanced accuracy score is roughly 0.93.
    - The precision is 0.09 and the sensitivity is 0.92 for predicting high-risk applications.
    - The precision is 1.00 and the sensitivity is 0.94 for predicting low-risk applications.
    - The F1 score of a high-risk prediction is 0.16; the F1 score of a low-risk prediction is 0.97.

![easy_ensemble_eval_metrics](https://user-images.githubusercontent.com/96349090/166645796-b76ad771-34e2-4667-8c4f-d64c1a01aa5a.png)


---

## Summary
<!-- Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. If you do not recommend any of the models, justify your reasoning. -->

Due to the nature of this project, I desire a higher accuracy for correctly predicted high-risk applications (true positives) over correctly predicted low-risk applications (true negatives). I also desire a higher predictability of low-risk applications falsely predicted as high-risk (false positives) over high-risk applications falsely predicted as low-risk (false negatives). This implies that even if I desire both values to be low in quantity, I would favor a model with high sensitivity over one with high precision when predicting high-risk applications. 

Notice that based on their evaluation metrics, re-sampling data with the various algorithms affected very little the performance of the logistic regression model. The balanced accuracy scores of all four algorithms are below 0.7, meaning they are also below the general minimum of 0.8. Interestingly, to predict high-risk applications, the precisions are all 0.01 while sensitivities are between 0.65 and 0.8. The balanced random forest classifier also observed a suboptimal accuracy of 0.68, with a precision of 0.88 and sensitivity of 0.37 for predicting high-risk applications. 

In comparison, the easy ensemble classifier obtains an astounding accuracy of 0.93, a low precision of 0.09, and a high sensitivity of 0.92 for predicting high-risk applications. Therefore I recommend at this point that the company employ the easy ensemble classifier to best predict high-risk applications while being cognizant of the possibility of overfitting. Overfitting may be detected and reduced by either [obtaining more training data or lowering model capacity](https://towardsdatascience.com/handling-overfitting-in-deep-learning-models-c760ee047c6e#:~:text=We%20can%20identify%20overfitting%20by,fit%20for%20the%20training%20data.).

---

## Resources

Data Source (file too large for upload):

    LoanStats_2019Q1.csv

Software:

    imbalanced-learn version 0.7.0
    Jupyter Notebook version 1.0.0
    NumPy version 1.20.3
    Pandas
    Python  3.7.11
    SciPy version 1.7.1
    Scikit-learn version 0.24.2
    
---

### Contact

Email: show.wang94@gmail.com

LinkedIn: [https://www.linkedin.com/in/s-k-wang](https://www.linkedin.com/in/s-k-wang)
