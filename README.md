# Soft Tissue Sarcoma Recurrence Prediction

## Overview

This project develops and evaluates machine learning models for predicting recurrence status in patients with **Soft Tissue Sarcoma (STS)**.

The analysis uses clinical and tumour-related patient information and applies a complete machine learning workflow, including data preprocessing, exploratory analysis, model training, evaluation, and model comparison.

The project was developed using **Python in Google Colab**.

> **Note:** This project is for educational and research purposes only. The predictions produced by the models should not be interpreted as medical advice or used for clinical decision-making.

---

## Project Objectives

The main objectives of this project are to:

* Explore clinical and tumour-related characteristics associated with STS recurrence.
* Prepare and preprocess the dataset for machine learning.
* Convert the recurrence outcome into a binary classification target.
* Train multiple machine learning classification models.
* Compare model performance using appropriate evaluation metrics.
* Visualise model performance using confusion matrices.
* Identify a suitable model for predicting recurrence status.

---

## Dataset

The dataset used in this project is the **Soft Tissue Sarcoma Dataset**, obtained from Kaggle.
The dataset contains clinical and tumour-related information used to investigate recurrence status using machine learning classification techniques.
The processed dataset contains **500 patient records** and the following variables:

* Sex
* Age
* Grade
* Histological type
* Site of primary STS
* Treatment
* Status

The target variable is **Status**, representing:

* `0` = No recurrence
* `1` = Recurrence

Patient identifiers and other non-feature columns were removed during preprocessing.

 
---

## Data Preprocessing

The notebook performs several preprocessing steps before model development:

1. Loads the Soft Tissue Sarcoma dataset using Pandas.
2. Removes non-feature columns such as Patient ID where present.
3. Creates a binary `Status` target from the original status information.
4. Encodes categorical variables using `LabelEncoder`.
5. Standardises the `Age` variable using `StandardScaler`.
6. Produces a processed dataset ready for machine learning.

---

## Exploratory Data Analysis

Exploratory analysis was performed to understand the characteristics of the dataset.

Visualisations include:

* Distribution of tumour grade
* Distribution of histological subtypes
* Analysis of recurrence status
* Clinical and tumour-related feature distributions

The notebook also converts encoded variables back to human-readable categories for visualisation where appropriate.

---

## Machine Learning Models

Three classification models were developed and compared:

### 1. Logistic Regression

A baseline classification model used to estimate the probability of recurrence based on the available patient and tumour characteristics.

### 2. Random Forest

An ensemble learning method that combines multiple decision trees to produce a classification prediction.

### 3. XGBoost

A gradient boosting algorithm used to build a powerful classification model by sequentially improving the prediction errors of previous models.

---

## Model Evaluation

The models were evaluated using:

* **Accuracy**
* **Area Under the Precision-Recall Curve (AUPRC)**
* **Matthews Correlation Coefficient (MCC)**
* **Confusion matrices**

AUPRC and MCC are particularly useful metrics for evaluating classification performance where class balance may be an important consideration.

---

## Results

The models achieved the following results in the notebook:

| Model               | Accuracy |     AUPRC |       MCC |
| ------------------- | -------: | --------: | --------: |
| **XGBoost**         | **0.83** |     0.858 | **0.664** |
| Logistic Regression |     0.82 |     0.873 |     0.640 |
| Random Forest       |     0.77 | **0.878** |     0.543 |

The results show that **XGBoost achieved the highest accuracy and MCC**, while **Random Forest achieved the highest AUPRC**.

Based on the combination of accuracy and MCC, XGBoost produced the strongest overall classification performance in this analysis.

---

## Visualisations

The project generates model evaluation visualisations, including:

* Confusion matrices for the different classification models
* Tumour grade distributions
* Histological subtype distributions
* Other exploratory visualisations included in the notebook

The notebook also saves the model comparison results as:

`results_table.csv`

and the confusion matrices as:

`confusion_matrices.png`

---

## Technologies Used

* **Python**
* **Google Colab**
* **Pandas**
* **NumPy**
* **Scikit-learn**
* **Matplotlib**
* **Seaborn**
* **XGBoost**
* **SHAP**

---

## Project Workflow

```text
Raw Dataset
     ↓
Data Loading
     ↓
Data Cleaning & Preprocessing
     ↓
Categorical Encoding
     ↓
Feature Scaling
     ↓
Exploratory Data Analysis
     ↓
Train Machine Learning Models
     ↓
Model Evaluation
     ↓
Compare Results
     ↓
Select Best Performing Model
```

---


## Key Findings

* The dataset contains **500 patient records** after preprocessing.
* Recurrence was formulated as a binary classification problem.
* Three machine learning approaches were compared.
* **XGBoost achieved the highest accuracy (83%)**.
* **XGBoost achieved the highest MCC (0.664)**.
* **Random Forest achieved the highest AUPRC (0.878)**.
* Model performance was assessed using multiple metrics rather than accuracy alone.

---

## Limitations

This project has several important limitations:

* The dataset contains a relatively small number of patient records.
* The analysis is based on the variables available in the dataset.
* Model performance may not generalise to other patient populations or healthcare settings.
* The results have not been externally validated on an independent clinical dataset.
* Machine learning predictions should not be interpreted as clinical recommendations.

---

## Future Improvements

Potential future development could include:

* Testing the models on an independent external dataset.
* Hyperparameter tuning.
* Cross-validation and more robust model comparison.
* Feature importance and explainability analysis using SHAP.
* Addressing potential class imbalance.
* Comparing additional machine learning algorithms.
* Improving clinical interpretability of model predictions.
* Investigating whether additional clinical variables improve predictive performance.

---


