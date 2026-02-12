```markdown
# Heart Disease Risk Prediction — Project Report

## 1. Motivation
Cardiovascular disease remains one of the leading causes of death worldwide. Early screening and risk assessment tools can help identify patients who may benefit from further testing or preventative care.

This project explores how machine learning classification models can predict the presence of heart disease from structured clinical measurements.

---

## 2. Problem Statement
Given patient health attributes such as cholesterol levels, resting blood pressure, and exercise-induced angina, the goal is to predict whether a patient has heart disease.

This is formulated as a supervised binary classification problem:

- Target = 1 → Heart disease present  
- Target = 0 → No heart disease  

---

## 3. Dataset
The dataset contains 13 clinical features across approximately 1,000 patient records.

Examples of features include:

- Age and sex  
- Chest pain type  
- Maximum heart rate  
- Resting ECG results  
- Thalassemia condition  

The dataset required preprocessing because multiple categorical variables were stored as descriptive strings rather than numeric codes.

---

## 4. Data Preprocessing
Categorical variables were manually mapped into numerical encodings to ensure compatibility with machine learning models.

A notable preprocessing challenge involved the `thalassemia` feature. Standard heart disease datasets encode thalassemia using values:

- 3 = Normal  
- 6 = Fixed defect  
- 7 = Reversible defect  

However, the dataset also contained the value `"No"`, which does not correspond to a valid medical category. This value was treated as unknown/miscoded and removed during cleaning.

After preprocessing, the final dataset contained 1,018 valid samples.

---

## 5. Model and Training
A Logistic Regression classifier was trained as a baseline model due to its interpretability and common use in medical risk prediction.

The dataset was split into:

- 80% training data  
- 20% test data  

Stratified sampling ensured balanced target distribution across splits.

---

## 6. Results
Model performance was evaluated using accuracy:

- Training Accuracy: ~86.5%  
- Test Accuracy: ~82.4%  

The relatively small gap between training and test accuracy suggests the model generalizes reasonably well without severe overfitting.

---

## 7. Predictive System
A simple predictive system was implemented to allow new patient measurements to be entered into the model for classification.

This demonstrates how trained ML models can be integrated into decision-support workflows.

---

## 8. Limitations and Future Work
This project represents an educational prototype and has several limitations:

- The dataset is small and may not represent diverse patient populations.
- Accuracy alone is not sufficient for clinical evaluation; precision/recall and calibration should also be explored.
- Real-world medical AI systems require extensive validation, fairness analysis, and clinical oversight.

Future improvements could include:

- Training ensemble models (Random Forest, Gradient Boosting)
- Adding explainability tools such as SHAP
- Deploying the model through a Streamlit dashboard

---

## 9. Conclusion
This project demonstrates an end-to-end machine learning workflow for healthcare risk prediction, including preprocessing, model training, evaluation, and prototype prediction.

It also highlights the importance of careful feature encoding and responsible interpretation of medical machine learning results.
