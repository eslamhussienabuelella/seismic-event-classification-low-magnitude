## Models Performance Summary

The table below summarises the performance of all evaluated machine learning
classifiers on the held-out test set. Due to strong class imbalance, **Macro-F1**
and **Weighted-F1** scores are prioritised over accuracy.

| Model | Accuracy | Weighted Precision | Weighted Recall | Weighted F1 | Macro Precision | Macro Recall | Macro F1 |
|------|----------|-------------------|----------------|------------|-----------------|--------------|----------|
| KNN | 0.9934 | 0.9929 | 0.9934 | 0.9932 | 0.7716 | 0.7737 | 0.7724 |
| Radius NN | 0.9876 | 0.9871 | 0.9876 | 0.9863 | 0.8083 | 0.6033 | 0.6532 |
| LDA | 0.9415 | 0.9592 | 0.9415 | 0.9487 | 0.4586 | 0.6751 | 0.5153 |
| Logistic Regression | 0.9909 | 0.9941 | 0.9909 | 0.9922	0.7695 | 0.8734 | 0.7914 |
| SVM | 0.9939 | 0.9944 | 0.9939 | 0.9941 | 0.8359 | 0.8706 | 0.8521 |
| Random Forest | 0.9985 | 0.9985 | 0.9985 | 0.9984 | 0.9960 | 0.8747 | 0.9196 |


**Key observations**

- Random Forest achieved the strongest overall performance, with the highest
  Macro-F1 and Weighted-F1 scores, indicating robust detection of minority classes.
- Support Vector Machine (SVM) showed competitive performance and substantially
  improved minority-class recall compared to linear models.
- Accuracy alone is misleading due to the dominance of earthquake events;
  Macro-F1 provides a more informative comparison across models.
