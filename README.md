# 🧠 Medical Diagnostic Assistance System

A machine learning-powered tool for predicting diabetic foot complications based on tongue image-derived clinical indicators and lab data. This project utilizes **Random Forest** classifiers to perform binary classification on clinical data, with complete support for model interpretability and diagnostic visualization.

## 📌 Project Overview

This notebook builds a **diagnostic prediction model** using medical data provided in the "Diabetic Foot Tongue Image Database". It includes the full pipeline:

- Data cleaning and preprocessing
- Label construction based on hardness indicators
- Feature selection and train-test splitting
- Random Forest model training
- Model evaluation using ROC, confusion matrix, and classification metrics
- New patient prediction support
- Diagnostic result visualization
- SHAP/LIME interpretability (future extension)

## 🗂 Dataset

- 📁 `Diabetic Foot Tongue Image Database.xlsx`
- 40+ clinical and biochemical features per patient
- Ground truth label derived from "Hardness at the First Metatarsophalangeal Joint"
- Binary classification: `0 = Normal`, `1 = Abnormal`

> Note: Due to privacy constraints, raw images are not used. Only derived numerical features are modeled.

## ⚙️ Model Details

- Model: `RandomForestClassifier` from `sklearn`
- Label: Hardness >= 5 → Positive Case
- Features: All other numerical indicators excluding patient ID and label feature
- Evaluation:
  - Confusion Matrix
  - ROC Curve + AUC
  - Classification Report (Precision, Recall, F1-score)

## 📊 Visualization

- 🔷 Confusion matrix heatmap
- 🔶 ROC curve with AUC score
- 🟢 Distribution of predicted diagnoses
- 🟡 Classification metric heatmap

All charts are automatically saved as `.png` images during runtime.

## 🧪 New Patient Prediction

You can simulate prediction by modifying the `new_patient_data` dictionary:
```python
new_patient_data = {
    "Age": 60,
    "BMI": 24.5,
    ...
}
