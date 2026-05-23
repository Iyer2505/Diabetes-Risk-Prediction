# Diabetes Risk Prediction Using Machine Learning

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Classification-green)
![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-yellow)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

---

## 📌 Project Overview

This project focuses on predicting diabetes risk using patient health indicators and machine learning classification models. The goal is to analyze important medical features such as glucose level, BMI, age, blood pressure, insulin, and diabetes pedigree function to understand their relationship with diabetes outcomes.

The project includes:

1. Data cleaning and exploratory data analysis  
2. Machine learning model training and evaluation  
3. Dashboard-ready dataset preparation  
4. Power BI dashboard planning and reporting  

This project is designed as an end-to-end healthcare analytics portfolio project, combining data analysis, classification modeling, model evaluation, and business intelligence reporting.

> **Healthcare Disclaimer:** This project is for educational and analytical purposes only. It is not intended for clinical diagnosis or medical decision-making.

---

## 🎯 Problem Statement

Diabetes is a chronic health condition that can be influenced by several patient health indicators. Early identification of diabetes risk can help support awareness and preventive care discussions.

This project answers the question:

> Can patient health measurements be used to classify diabetes risk using machine learning?

---

## 🧠 Project Objectives

The main objectives of this project are to:

- Analyze diabetes outcome distribution
- Identify invalid zero values in medical measurements
- Clean and prepare the dataset for machine learning
- Explore relationships between health indicators and diabetes outcome
- Build multiple classification models
- Compare model performance using healthcare-relevant metrics
- Identify important features influencing diabetes risk prediction
- Prepare dashboard-ready files for Power BI reporting

---

## 🗂️ Dataset Description

The dataset contains patient-level health measurements and a binary diabetes outcome variable.

### Target Variable

| Column | Description |
|---|---|
| `Outcome` | Target variable where `0 = No Diabetes` and `1 = Diabetes` |

### Feature Columns

| Column | Description |
|---|---|
| `Pregnancies` | Number of pregnancies |
| `Glucose` | Plasma glucose concentration |
| `BloodPressure` | Diastolic blood pressure |
| `SkinThickness` | Triceps skin fold thickness |
| `Insulin` | 2-hour serum insulin |
| `BMI` | Body Mass Index |
| `DiabetesPedigreeFunction` | Diabetes pedigree score |
| `Age` | Patient age |

---

## 🛠️ Tools & Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Jupyter Notebook
- Power BI

---

## 📂 Project Structure

```text
Diabetes-Risk-Prediction/
│
├── data/
│   ├── raw/
│   │   └── diabetes.csv
│   │
│   └── processed/
│       ├── diabetes_cleaned.csv
│       ├── outcome_summary.csv
│       ├── feature_summary_by_outcome.csv
│       ├── model_performance.csv
│       ├── diabetes_predictions.csv
│       ├── feature_importance.csv
│       ├── confusion_matrix.csv
│       └── risk_summary.csv
│
├── notebooks/
│   ├── 01_data_cleaning_eda.ipynb
│   └── 02_model_training_evaluation.ipynb
│
├── dashboard/
│   └── diabetes_risk_dashboard.pbix
│
├── images/
│   ├── outcome_distribution.png
│   ├── invalid_zero_values.png
│   ├── glucose_by_outcome.png
│   ├── bmi_by_outcome.png
│   ├── age_by_outcome.png
│   ├── correlation_heatmap.png
│   ├── model_comparison_roc_auc.png
│   ├── model_comparison_recall.png
│   ├── confusion_matrix.png
│   ├── roc_curve.png
│   ├── feature_importance.png
│   ├── prediction_probability_distribution.png
│   ├── dashboard_patient_overview.png
│   ├── dashboard_risk_factor_analysis.png
│   └── dashboard_model_performance.png
│
├── docs/
│   ├── POWER_BI_DASHBOARD_PLAN.md
│   ├── DAX_MEASURES.md
│   └── STEP_3_PROCESS.md
│
├── README.md
├── requirements.txt
└── .gitignore
```

---

## 🔍 Step 1: Data Cleaning and Exploratory Data Analysis

The first step focused on understanding and preparing the dataset.

### Key Tasks Completed

- Loaded the diabetes dataset
- Reviewed dataset shape and structure
- Checked for missing values
- Identified invalid zero values in medical columns
- Replaced invalid zeros with missing values
- Applied median imputation
- Created new categorical features
- Analyzed class balance
- Explored relationships between health indicators and diabetes outcome
- Exported cleaned dataset for machine learning

---

## 🧹 Data Cleaning

Although the dataset did not contain standard null values, several medical columns contained zero values that are not biologically realistic.

Invalid zero values were found in:

```text
Glucose
BloodPressure
SkinThickness
Insulin
BMI
```

These values were treated as missing data and replaced using median imputation.

### Why Median Imputation?

Median imputation was used because medical variables such as insulin, BMI, and skin thickness can be skewed and may contain outliers. The median is more robust than the mean in such cases.

---

## 🧬 Feature Engineering

Additional features were created to support analysis and dashboard reporting.

| Feature | Description |
|---|---|
| `glucose_category` | Groups glucose values into health-risk ranges |
| `bmi_category` | Groups BMI values into BMI categories |
| `age_group` | Groups patients into age bands |
| `risk_label` | Converts outcome values into readable labels |
| `outcome_label` | Dashboard-friendly diabetes outcome label |

---

## 📊 Exploratory Data Analysis

The EDA focused on understanding differences between diabetes-positive and non-diabetes patients.

### Key EDA Questions

1. What is the distribution of diabetes outcomes?
2. Which columns contain invalid medical values?
3. How does glucose differ between diabetes and non-diabetes patients?
4. How does BMI differ by diabetes outcome?
5. How does age relate to diabetes outcome?
6. Which features are most correlated with diabetes outcome?

---

## 📈 EDA Visualizations

### Diabetes Outcome Distribution

![Outcome Distribution](images/outcome_distribution.png)

### Invalid Zero Values Before Cleaning

![Invalid Zero Values](images/invalid_zero_values.png)

### Glucose Distribution by Outcome

![Glucose by Outcome](images/glucose_by_outcome.png)

### BMI Distribution by Outcome

![BMI by Outcome](images/bmi_by_outcome.png)

### Age Distribution by Outcome

![Age by Outcome](images/age_by_outcome.png)

### Correlation Heatmap

![Correlation Heatmap](images/correlation_heatmap.png)

---

## 🤖 Step 2: Machine Learning Model Training and Evaluation

The second step focused on building classification models to predict diabetes risk.

### Machine Learning Objective

> Predict whether a patient is likely to have diabetes based on available health indicators.

### Models Trained

The following models were compared:

1. Logistic Regression
2. K-Nearest Neighbors
3. Decision Tree
4. Random Forest
5. Gradient Boosting
6. Tuned Random Forest

---

## ⚙️ Modeling Approach

The modeling workflow included:

- Stratified train-test split
- Pipeline-based preprocessing
- Standard scaling where required
- Multiple model comparison
- Cross-validation
- Random Forest hyperparameter tuning
- Final model selection
- Feature importance analysis

### Why Stratified Splitting?

The dataset is moderately imbalanced, with more non-diabetes cases than diabetes cases. Stratified splitting preserves the same class distribution in both training and testing datasets.

### Why Pipelines?

Pipelines were used to prevent data leakage. Scaling was applied only within the training process and then applied to the test data through the pipeline.

---

## 📏 Evaluation Metrics

Because this is a healthcare-related classification project, accuracy alone is not enough.

The models were evaluated using:

| Metric | Meaning |
|---|---|
| Accuracy | Overall percentage of correct predictions |
| Precision | How many predicted diabetes cases were actually diabetes |
| Recall | How many actual diabetes cases were correctly detected |
| F1 Score | Balance between precision and recall |
| ROC-AUC | Model’s ability to separate diabetes and non-diabetes cases |
| Cross-Validated ROC-AUC | More reliable ROC-AUC using cross-validation |

For diabetes prediction, recall is especially important because missing a diabetes-risk patient may be more serious than a false positive.

---

## 🏆 Best Model

The best-performing model was:

```text
Gradient Boosting
```

### Model Performance

| Metric | Score |
|---|---:|
| Accuracy | 0.7597 |
| Precision | 0.6889 |
| Recall | 0.5741 |
| F1 Score | 0.6263 |
| ROC-AUC | 0.8315 |
| Cross-Validated ROC-AUC | 0.8148 |

The model achieved a strong ROC-AUC score, meaning it can reasonably distinguish between diabetes and non-diabetes cases using the available features.

---

## 📊 Machine Learning Visualizations

### Model Comparison by ROC-AUC

![Model Comparison ROC-AUC](images/model_comparison_roc_auc.png)

### Model Comparison by Recall

![Model Comparison Recall](images/model_comparison_recall.png)

### Confusion Matrix

![Confusion Matrix](images/confusion_matrix.png)

### ROC Curve

![ROC Curve](images/roc_curve.png)

### Feature Importance

![Feature Importance](images/feature_importance.png)

### Prediction Probability Distribution

![Prediction Probability Distribution](images/prediction_probability_distribution.png)

---

## 📊 Step 3: Dashboard Dataset Preparation

Dashboard-ready CSV files were prepared for Power BI reporting.

### Dashboard Files Created

| File | Purpose |
|---|---|
| `fact_patients.csv` | Main patient-level dashboard dataset |
| `outcome_summary.csv` | Diabetes outcome summary |
| `age_group_summary.csv` | Age-group-level summary |
| `glucose_summary.csv` | Glucose category summary |
| `bmi_summary.csv` | BMI category summary |
| `model_performance.csv` | Machine learning model comparison |
| `diabetes_predictions.csv` | Model prediction output |
| `feature_importance.csv` | Feature importance values |
| `confusion_matrix.csv` | Confusion matrix output |
| `risk_summary.csv` | Predicted risk group summary |

---

## 📊 Step 4: Power BI Dashboard

A Power BI dashboard was planned and built to present patient risk patterns and model performance.

### Dashboard Pages

The dashboard contains three main pages:

1. Patient Risk Overview
2. Risk Factor Analysis
3. Model Performance & Prediction Insights

---

## 🖼️ Dashboard Preview

### Patient Risk Overview

![Patient Risk Overview](images/dashboard_patient_overview.png)

### Risk Factor Analysis

![Risk Factor Analysis](images/dashboard_risk_factor_analysis.png)

### Model Performance

![Model Performance](images/dashboard_model_performance.png)

---

## 💡 Key Insights

- Patients with diabetes generally have higher glucose levels.
- BMI is higher on average among diabetes-positive patients.
- Age and pregnancies show noticeable differences between diabetes and non-diabetes groups.
- Glucose is one of the strongest indicators associated with diabetes outcome.
- The dataset is moderately imbalanced, so accuracy alone is not sufficient for model evaluation.
- Gradient Boosting achieved the strongest ROC-AUC score among the tested models.
- Feature importance helps explain which patient health indicators contribute most to prediction.

---

## 🚀 Business / Analytical Recommendations

Based on the analysis:

- Use recall, F1-score, and ROC-AUC when evaluating healthcare classification models.
- Treat model predictions as analytical support, not as medical diagnosis.
- Use feature importance to understand which health indicators are most influential.
- Improve future models with larger, more diverse, and clinically validated datasets.
- Add additional health variables such as cholesterol, lifestyle factors, family history, and medication data for better prediction quality.

---

## ⚠️ Project Limitations

This project has several limitations:

- The dataset is relatively small.
- The dataset may not represent all populations.
- Some medical values were missing and required imputation.
- Important clinical variables are not included.
- The model is not clinically validated.
- Prediction results should not be used for real medical decisions.

---

## ▶️ How to Run This Project

### 1. Clone the Repository

```bash
git clone https://github.com/bhargavimv27/Diabetes-Risk-Prediction.git
cd Diabetes-Risk-Prediction
```

### 2. Create a Virtual Environment

```bash
python -m venv venv
```

### 3. Activate the Virtual Environment

For Windows:

```bash
venv\\Scripts\\activate
```

For macOS/Linux:

```bash
source venv/bin/activate
```

### 4. Install Dependencies

```bash
pip install -r requirements.txt
```

### 5. Run the Notebooks

```bash
jupyter notebook
```

Run the notebooks in this order:

```text
notebooks/01_data_cleaning_eda.ipynb
notebooks/02_model_training_evaluation.ipynb
```

### 6. Open the Power BI Dashboard

Open the Power BI file:

```text
dashboard/diabetes_risk_dashboard.pbix
```

If needed, update the data source paths in Power BI to point to:

```text
data/processed/
```

---

## 📦 Requirements

Create a `requirements.txt` file with:

```text
pandas
numpy
matplotlib
scikit-learn
jupyter
notebook
```

Install requirements using:

```bash
pip install -r requirements.txt
```

---

## 🔮 Future Improvements

Future improvements can include:

- Add more clinical features
- Use larger and more diverse datasets
- Try additional algorithms such as XGBoost or LightGBM
- Tune decision thresholds to improve recall
- Add SHAP explainability
- Deploy the model using Streamlit
- Publish the Power BI dashboard online
- Validate the model with external healthcare datasets

---

## ✅ Project Status

Completed:

- Data cleaning
- Invalid zero-value handling
- Exploratory data analysis
- Feature engineering
- Machine learning model training
- Model comparison
- Cross-validation
- Feature importance
- Dashboard-ready CSV preparation
- Power BI dashboard planning
- GitHub-ready documentation

---

## 👤 Author

**Bhargavi Marghashayam Venkatesh**

GitHub: [@bhargavimv27](https://github.com/bhargavimv27)

---

## ⚠️ Final Disclaimer

This project is for educational and analytical purposes only. It is not intended to diagnose diabetes, recommend treatment, or replace professional medical advice.
