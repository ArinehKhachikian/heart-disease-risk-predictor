# Heart Disease Risk Prediction with Logistic Regression

## Overview
This project builds a machine learning model to predict the likelihood of heart disease based on patient clinical measurements such as age, cholesterol, blood pressure, and exercise-induced angina.

The goal is to explore how supervised learning models can support early risk screening in healthcare and to practice building an end-to-end machine learning pipeline on structured medical data.

---

## Dataset
- Source: Heart Disease Dataset (UCI-style dataset via Kaggle)
- Samples: 1,018 patients after preprocessing
- Features: 13 clinical attributes including:
  - Age, sex
  - Chest pain type
  - Resting blood pressure
  - Cholesterol
  - Maximum heart rate
  - Thalassemia status
- Target variable:
  - `1` = Heart disease present  
  - `0` = No heart disease  

---

## Methods

### Data Preprocessing
Several features were stored as descriptive text values rather than numeric codes.  
To prepare the dataset for modeling, categorical variables were manually mapped into numerical encodings, including:

- Sex (Male/Female)
- Chest pain categories
- ECG results
- Exercise-induced angina
- Thalassemia status

#### Handling Invalid Values
The `thalassemia` column contained the value `"No"`, which is not part of the standard medical encoding (3, 6, 7).  
This value was treated as unknown/miscoded and handled during preprocessing.

---

## Model
A **Logistic Regression** classifier was trained as a baseline medical risk prediction model.

Steps included:

- Train/test split (80/20) with stratification
- Model training using scikit-learn
- Evaluation on both training and test sets

---

## Results

| Metric | Score |
|--------|-------|
| Training Accuracy | ~86.5% |
| Test Accuracy | ~82.4% |

The model generalizes reasonably well and demonstrates the ability of simple interpretable classifiers to perform risk prediction on clinical tabular data.

---

## Predictive System Demo
The notebook includes a simple prediction system where new patient feature inputs can be passed into the trained model to output:

- Heart disease risk classification (0 or 1)

Example:

```python
input_data = (41,0,1,130,204,0,0,172,0,1.4,2,0,2)
prediction = model.predict(input_data_reshaped)
