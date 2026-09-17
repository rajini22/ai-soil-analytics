# Week 4 — Hybrid Soil Analysis Report

## 1. Objective

This module combines:

- ResNet-50 image-based soil classification
- XGBoost structured soil-test analysis
- Explainable AI outputs from Grad-CAM and SHAP

The purpose is to provide a combined soil assessment using both
visual soil information and structured soil-test parameters.

---

## 2. Image-Based Analysis

**Actual Image Class:** Alluvial_Soil

**Predicted Soil Class:** Black_Soil

**CNN Confidence:** 0.9994

The ResNet-50 model provides the visual soil-class prediction.

---

## 3. Structured Soil-Test Analysis

### Input Parameters

| Parameter | Value |
|---|---:|
| Moisture | 15.4947 |
| pH | 7.6500 |
| Organic Matter | 1.7200 |
| Nitrogen | 0.1040 |
| Phosphorus | 23.9000 |
| Potassium | 314.0000 |

### XGBoost Predictions

| Nutrient | Input Value | XGBoost Prediction |
|---|---:|---:|
| Nitrogen | 0.1040 | 0.0982 |
| Phosphorus | 23.9000 | 23.8050 |
| Potassium | 314.0000 | 336.1294 |

---

## 4. Hybrid Assessment

The hybrid system combines the outputs at the assessment level:

**Image branch:**

ResNet-50 → Soil Class + CNN Confidence

**Structured branch:**

XGBoost → Nitrogen + Phosphorus + Potassium predictions

**Combined output:**

Visual Soil Classification + Quantitative Nutrient Analysis

This approach avoids treating soil-class predictions and nutrient
regression values as the same type of output.

---

## 5. Confidence Handling

The CNN confidence is reported directly with the predicted soil class.

The XGBoost models provide continuous nutrient predictions.
Their reliability is represented separately through the model
evaluation metrics rather than by treating regression output as
classification probability.

---

## 6. Soil Health Score

**Status: Pending validated scoring thresholds.**

The available project dataset does not provide validated nutrient
deficiency classes or a soil-health scoring formula. Therefore, an
arbitrary threshold-based health score has not been introduced.

A final soil-health score should be implemented only after validated
thresholds/rules are supplied by the project/mentor or an appropriate
agronomic reference is formally selected.

---

## 7. Explainable AI

### CNN

Grad-CAM was implemented to visualize image regions contributing
to the CNN prediction.

### Structured ML

SHAP was implemented to explain the contribution of structured
soil-test features to the XGBoost predictions.

---

## 8. Models Used

- ResNet-50 — image feature extraction and soil classification
- Dense neural-network classifier — classification head
- XGBoost — structured N/P/K regression
- Grad-CAM — CNN explanation
- SHAP — XGBoost explanation

---

## 9. Sample Information

**Sample ID:** 1

**Crop:** MAIZE

**Image:** C:\Users\RAJINI\OneDrive\Desktop\AI-Soil-Analytics\data\images\split\test\Alluvial_Soil\103.png

**Report Generated:** 2026-09-04 16:01:19

---

## 10. Conclusion

The ResNet-50 and XGBoost branches have been successfully integrated
into a hybrid soil-analysis pipeline.

The system can currently provide:

1. Visual soil classification
2. CNN confidence
3. Quantitative N/P/K predictions
4. Grad-CAM visual explanation
5. SHAP feature explanations

Soil-health scoring remains pending validated agronomic thresholds.
