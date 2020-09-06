# Supervised_ML

The task for this module is to implement supervised machine learning models and resampling techniques to assess the credit risk using data from LendingClub; a peer-to-peer lending service. A logistic regression model with standard parameters and different resampling techniques are used to address the imbalance of the data where the number of high risk loans is significantly lower than the number of low risk loans.

### Prediction Results

##### Random Oversampling

Balanced Accuracy Score: 0.65

Confusion Matrix:
| --- | P. High | P. Low |
| --- | --- | --- |
| T. High | 70 | 31 |
| T. Low  | 6711 | 10393 |

Classification Imbalanced Report:
| --- | pre | red | f1 | sup |
| --- | --- | --- | --- | --- |
| High Risk | 0.01 | 0.69 | 0.02 | 202 |
| Low Risk | 1.00  | 0.61 | 0.76 | 17104 |

##### SMOTE Oversampling

Balanced Accuracy Score: 0.66

Confusion Matrix:
| --- | P. High | P. Low |
| --- | --- | --- |
| T. High | 64 | 37 |
| T. Low  | 5291 | 11813 |

Classification Imbalanced Report:
| --- | pre | red | f1 | sup |
| --- | --- | --- | --- | --- |
| High Risk | 0.01 | 0.69 | 0.02 | 202 |
| Low Risk | 1.00 | 0.69 | 0.82 | 17104 |

##### Cluster Centroids Undersampling

Balanced Accuracy Score: 0.66

Confusion Matrix:
| --- | P. High | P. Low |
| --- | --- | --- |
| T. High | 64 | 37 |
| T. Low  | 5291 | 11813 |

Classification Imbalanced Report:
| --- | pre | red | f1 | sup |
| --- | --- | --- | --- | --- |
| High Risk | 0.01 | 0.63 | 0.02 | 101 |
| Low Risk | 1.00 | 0.69 | 0.82 | 17104 |

##### Combination (Over and Under) Sampling

Balanced Accuracy Score: 0.66

Confusion Matrix:
| --- | P. High | P. Low |
| --- | --- | --- |
| T. High | 64 | 37 |
| T. Low  | 5291 | 11813 |

Classification Imbalanced Report:
| --- | pre | red | f1 | sup |
| --- | --- | --- | --- | --- |
| High Risk | 0.01 | 0.63 | 0.02 | 101 |
| Low Risk | 1.00 | 0.69 | 0.82 | 17104 |

### Analysis

It is important to note that it is must be decided whether it is more valuable to have high precision or high sensitivity of the model. That is to say should loans be given to the most number of low risk loaners and some to high risk loaners, or identify the maximum number of high risk loaners and decline many low risk loaners in the process.

In the models, all models had small precision for high risk loans. This was approximated at about 1%. This means that all models are returning a large number of false positives, or low risk loans being sorted as high risk loans. The models are also all returning a high precision for low risk loans, at about 100%. Thus sensitivity needs to be compared.

Random Oversampling has the highest sensitivity to high risk loans. This model predicted about 70 our of 101 high risk loans. However, the sensitivity for low risk loans was not great as the number of false positives were large. The number of true negatives were also high. This suggests that the Random Oversampling model would be best of all four models, but still does not produce very satisfying results.

SMOTE oversampling, SMOTEEN and Centroid Culsters, however, did show the highest number of true negatives at 11827 low out of 17104 total. These models had a higher sensativites toe the low risk loans. While the the sensitivity to the high risk loans is lower than for Random Oversampling, it may still be worthwhile to go with these models as they give a balance result of true positives and true negatives.

Thus, none of these models work very well as they are all fairly poor in predicting the results. I would recommend possibly deriving information from each model to get rough idea of when can be expected instead of purely relying on an individual model.
