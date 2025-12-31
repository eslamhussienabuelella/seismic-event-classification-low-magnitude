# Seismic Event Classification of Low-Magnitude Events (M1–4)

## Overview
This project benchmarks classical machine learning algorithms for the automatic classification of **low-magnitude seismic events (M1–4)** using metadata from the USGS Earthquake Catalogue. Low-magnitude events exhibit overlapping characteristics that make manual catalogue maintenance time-consuming and prone to bias.

The goal is to identify **robust, interpretable, and operationally reliable** machine learning models capable of handling **severe class imbalance** in real seismic catalogues.

---

## Motivation
Accurate seismic catalogues are essential for:
- seismic hazard assessment
- early-warning systems
- large-scale geophysical research

As monitoring systems improve, the volume of detected low-magnitude events increases, making manual classification unsustainable. Automated, explainable ML solutions are therefore critical for maintaining catalogue consistency.

---

## Dataset (High-Level)
- **Source:** USGS Earthquake Catalogue
- **Time window:** 1 Aug 2025 – 20 Nov 2025
- **Magnitude range:** 1.0 – 4.0
- **Samples:** 19,958 events
- **Classes:** Earthquake, Quarry Blast, Explosion, Mining Explosion, Icequake, Other

⚠️ Raw data is not included in this repository.
See `data/README.md` for the full schema, preprocessing decisions, and the USGS query to reproduce the dataset.


---

## Methodology
- Feature engineering from spatial, temporal, and uncertainty attributes
- One-hot encoding for categorical variables
- Stratified **60 / 20 / 20** train-validation-test split
- Cost-sensitive learning to address class imbalance
- Model selection via **GridSearchCV** using weighted F1-score

### Models Evaluated
- K-Nearest Neighbours (KNN)
- Radius Nearest Neighbours (RNN)
- Logistic Regression
- Linear Discriminant Analysis (LDA)
- Support Vector Machine (SVM, RBF kernel)
- Random Forest

---

## Evaluation Strategy
Due to extreme class imbalance, **accuracy alone is misleading**.
Models are compared using:
- **Weighted F1-score**
- **Macro F1-score**
- **Confusion matrices**

This ensures fair evaluation of minority seismic event types.

---

## Key Results
- **Random Forest** achieved the strongest overall performance, with the highest
  Macro-F1 and Weighted-F1 scores.
- **SVM** showed competitive performance, particularly in minority-class detection.
- Linear and instance-based models performed well on the majority of classes but struggled with rare events.

A full comparison table is available in `results/results_metrics_summary.md`.

---

## Interpretability
Random Forest feature importance analysis highlights:
- depth
- latitude
- longitude
- magnitude
- uncertainty measures (depthError, dmin)

These findings align with known physical distinctions between natural and anthropogenic seismic sources.

---

## Repository Structure

Repository Structure  
├── data/        # Dataset documentation  
├── notebooks/   # End-to-end ML pipeline  
├── results/     # Tables, figures, and evaluation summaries  
├── requirements.txt  # Project requirements
└── README.md    # Project overview


---


```markdown
## Reproducibility
All preprocessing, modelling, and evaluation steps are fully documented in:
`notebooks/seismic_ml_pipeline_git_clean.ipynb`



---

## Author
**Eslam Abuelella**  
MSc Data Science – Coventry University  

