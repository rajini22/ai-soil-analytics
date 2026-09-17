# Milestone 2 — Final Report

## AI-Powered Soil Analytics System

Generated: 2026-09-04 16:10:50

---

## Week 3 — CNN Soil Image Analysis

### Model

ResNet-50 transfer-learning based image analysis was implemented
for seven soil classes:

- Alluvial Soil
- Arid Soil
- Black Soil
- Laterite Soil
- Mountain Soil
- Red Soil
- Yellow Soil

### Dataset

Training images: 794

Validation images: 171

Test images: 174

### Test Performance

Accuracy: 88.51%

Weighted Precision: 88.23%

Weighted Recall: 88.51%

Weighted F1-score: 88.03%

A confusion matrix and incorrect-prediction analysis were completed.

The saved CNN classifier is:

models/cnn/resnet50_soil_classifier.keras

---

## Week 4 — Structured ML

The cleaned soil-test dataset contains 146 records.

The structured parameters are:

- Moisture
- pH
- Organic Matter
- Nitrogen
- Phosphorus
- Potassium

XGBoost regression models were developed for nitrogen,
phosphorus and potassium.

### Final Test Results

#### Nitrogen

MAE: 0.0571

RMSE: 0.1256

R²: 0.4978

#### Phosphorus

MAE: 35.8509

RMSE: 68.4390

R²: 0.4947

#### Potassium

MAE: 227.4419

RMSE: 334.8574

R²: 0.0062

Hyperparameter tuning was performed using GridSearchCV.

The final models were saved under:

models/xgboost/

---

## Explainable AI

### Grad-CAM

Grad-CAM was implemented for the ResNet-50 image-analysis branch.

The visualization identifies image regions contributing to the
CNN prediction, including an incorrect high-confidence prediction.

### SHAP

SHAP explanations were generated for the nitrogen, phosphorus
and potassium XGBoost models.

---

## Hybrid Soil Analysis

The hybrid system combines:

ResNet-50 image analysis

+

XGBoost structured soil-test analysis

The image branch provides:

- Soil class
- CNN confidence

The structured branch provides:

- Nitrogen prediction
- Phosphorus prediction
- Potassium prediction

The combined system also produces a project-level relative
soil-health score.

---

## Hybrid Validation

Number of real records tested: 10

Image accuracy on this small integration test: 20.00%

Average relative soil-health score: 18.16/100

The detailed results are available in:

reports/hybrid/final_hybrid_soil_assessment.csv

Important limitation:

The available image dataset and structured soil-test dataset do
not provide a verified one-to-one correspondence between individual
images and individual soil-test samples. Therefore, this validation
demonstrates pipeline integration rather than scientifically paired
multimodal accuracy.

---

## Soil-Health Score

The implemented score is a project-level relative score based on
the six parameters available in the cleaned dataset.

It compares parameter values with the observed ranges in the
project dataset.

It is NOT an official Soil Health Card score and should not be
interpreted as a validated agronomic percentage of soil health.

---

## Final Models and Methods

- ResNet-50 — soil image analysis
- Dense classifier head — soil classification
- XGBoost — N/P/K regression
- Grad-CAM — CNN explainability
- SHAP — structured-model explainability
- Hybrid ResNet-50 + XGBoost — combined soil assessment
- Relative soil-health scoring — project-level assessment

---

## Milestone 2 Deliverables

✓ CNN model

✓ CNN evaluation

✓ Confusion matrix

✓ Incorrect prediction analysis

✓ Grad-CAM

✓ XGBoost nitrogen model

✓ XGBoost phosphorus model

✓ XGBoost potassium model

✓ XGBoost evaluation

✓ Hyperparameter tuning

✓ SHAP explanations

✓ Hybrid analysis

✓ Hybrid validation

✓ Soil-health scoring implementation

✓ Final Milestone 2 report

---

## Conclusion

The machine-learning, explainability and hybrid-analysis components
specified for Milestone 2 have been implemented using the available
project data.

The system combines visual soil classification with structured
soil-test analysis and provides a project-level relative soil-health
assessment.

The absence of paired image/soil-test records and validated
soil-health thresholds is documented as a project limitation.
