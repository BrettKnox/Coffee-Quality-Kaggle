# Defect Prediction in Arabica Coffee Beans

## Overview
This project develops machine learning models to predict whether a batch of Arabica coffee beans is **defective** or **non-defective** using quality metrics, origin data, and physical attributes.

The goal was to identify key drivers of defects and build a classifier with strong predictive performance (target: AUROC ≥ 0.8).

---

## Dataset
- Source: Coffee Quality Institute (scraped)
- ~200+ batches
- 40+ attributes
- Binary target: `Defect` vs `No Defect`
- Features include:
  - Quality scores
  - Physical measurements
  - Origin metadata
  - Processing variables

---

## Data Preprocessing
- Removed redundant fields
- Cleaned inconsistent strings
- Merged categorical defect types
- Removed features with excessive missing values
- Encoded categorical variables
- Feature selection via information gain ranking

---

## Models Implemented
- **K-Nearest Neighbors (KNN)**
- **Support Vector Machine (SVM)**
- **Random Forest**
- **AdaBoost**
- Baseline models:
  - Majority class baseline
  - Single-attribute baseline

---

## Validation Strategy
- 10-fold cross-validation
- Hyperparameter tuning:
  - KNN: k range
  - SVM: margin parameter
  - AdaBoost: learning rate & estimators
  - Random Forest: random seed variation
- Performance metrics:
  - **AUROC** (primary metric)
  - **AUPRC**

---

## Results
- **AdaBoost achieved the best overall performance** on the test set.
- Most important predictive features:
  - Total defect count
  - Number of bags
  - Altitude
  - Moisture content

---

## Key Insights
- Quality-related attributes strongly correlate with defect presence.
- Origin and production features improve predictive power.
- Ensemble methods outperform simpler baselines.

---

## Future Work
- Improve handling of missing values
- Expand feature engineering using production metadata
- Compare against interpretable models (e.g., logistic regression)
