# Week 4 — Final Summary

## Project
AI-Powered Soil Analytics System for Nutrient Assessment and Intelligent Crop Advisory

---

## 1. Structured ML

The cleaned soil-test dataset contains 146 records and six
required numeric soil parameters:

- Moisture
- pH
- Organic Matter
- Nitrogen
- Phosphorus
- Potassium

XGBoost regression models were developed for:

- Nitrogen
- Phosphorus
- Potassium

The models were evaluated using MAE, RMSE and R².

Hyperparameter tuning was performed using GridSearchCV with
5-fold cross-validation.

Final models were saved under:

models/xgboost/

---

## 2. Final XGBoost Test Performance

### Nitrogen

MAE: 0.0571
RMSE: 0.1256
R²: 0.4978

### Phosphorus

MAE: 35.8509
RMSE: 68.4390
R²: 0.4947

### Potassium

MAE: 227.4419
RMSE: 334.8574
R²: 0.0062

The results indicate that the models have different predictive
strengths, with nitrogen and phosphorus showing more useful
predictive performance than potassium on the held-out test set.

---

## 3. Explainable AI

### CNN — Grad-CAM

Grad-CAM was implemented for the ResNet-50 image classification
branch.

A high-confidence incorrect prediction was also inspected to
demonstrate model attention during an error case.

### XGBoost — SHAP

SHAP explanations were generated for the:

- Nitrogen model
- Phosphorus model
- Potassium model

These explanations show the contribution of structured soil-test
features to the model predictions.

---

## 4. Hybrid Analysis

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

The outputs are combined at the soil-assessment level rather than
mathematically averaging incompatible output types.

---

## 5. Soil Health Score

A final numerical soil-health score has not been assigned.

Reason:

The available project dataset and provided milestone material do
not specify validated nutrient-deficiency thresholds or a numerical
soil-health scoring formula.

Therefore, no arbitrary threshold or score has been introduced.

A validated scoring method can be added when the required
agronomic thresholds/rules are provided.

---

## 6. Models and Methods

### Image Analysis

ResNet-50 transfer learning

### Structured Analysis

XGBoost regression

### CNN Explainability

Grad-CAM

### Structured Model Explainability

SHAP

### Hybrid Analysis

ResNet-50 + XGBoost

---

## 7. Week 4 Deliverables

- Trained CNN model
- CNN evaluation results
- Confusion matrix
- Grad-CAM visualization
- XGBoost N model
- XGBoost P model
- XGBoost K model
- XGBoost evaluation results
- SHAP explanations
- Hybrid analysis function
- Hybrid analysis report

---

## 8. Conclusion

Week 4 machine-learning, explainability and hybrid-analysis
implementation has been completed based on the available project
data and milestone requirements.

The remaining soil-health scoring component requires validated
agronomic thresholds before a final numerical score can be
scientifically implemented.
