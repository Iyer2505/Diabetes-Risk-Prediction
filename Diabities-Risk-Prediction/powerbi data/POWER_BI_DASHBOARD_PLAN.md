# Power BI Dashboard Plan

## Dashboard Title

```text
Diabetes Risk Prediction Dashboard
```

## Dashboard Goal

Build a professional healthcare analytics dashboard that explains diabetes risk patterns, patient health indicators, and machine learning model performance.

> Disclaimer: This dashboard is for educational and analytical purposes only. It is not intended for clinical diagnosis or medical decision-making.

---

## Data Files to Import

Import these CSV files into Power BI:

```text
fact_patients.csv
outcome_summary.csv
age_group_summary.csv
glucose_summary.csv
bmi_summary.csv
model_performance.csv
diabetes_predictions.csv
feature_importance.csv
confusion_matrix.csv
risk_summary.csv
```

Use `fact_patients.csv` as the main table.

---

## Recommended Dashboard Pages

Create 3 pages:

```text
1. Patient Risk Overview
2. Risk Factor Analysis
3. Model Performance & Prediction Insights
```

---

# Page 1: Patient Risk Overview

## Purpose

Give a high-level overview of patient distribution and key health indicators.

## KPI Cards

Use card visuals for:

```text
Total Patients
Diabetes Positive Patients
Diabetes Positive Rate
Average Glucose
Average BMI
Average Age
```

## Main Visuals

### 1. Outcome Distribution

Visual type:

```text
Donut chart
```

Fields:

```text
Legend: outcome_label
Values: Count of patient_id
```

Title:

```text
Diabetes Outcome Distribution
```

### 2. Average Glucose by Outcome

Visual type:

```text
Clustered column chart
```

Fields:

```text
X-axis: outcome_label
Y-axis: Average Glucose
```

Title:

```text
Average Glucose by Diabetes Outcome
```

### 3. Average BMI by Outcome

Visual type:

```text
Clustered column chart
```

Fields:

```text
X-axis: outcome_label
Y-axis: Average BMI
```

Title:

```text
Average BMI by Diabetes Outcome
```

### 4. Patient Count by Age Group

Visual type:

```text
Stacked column chart
```

Fields:

```text
X-axis: age_group
Y-axis: Count of patient_id
Legend: outcome_label
```

Title:

```text
Patient Distribution by Age Group
```

## Slicers

Add slicers for:

```text
age_group
bmi_category
glucose_category
outcome_label
```

---

# Page 2: Risk Factor Analysis

## Purpose

Explore how health indicators differ between diabetes and non-diabetes patients.

## Visuals

### 1. Glucose Category by Outcome

Visual type:

```text
Stacked bar chart
```

Fields:

```text
Y-axis: glucose_category
X-axis: Count of patient_id
Legend: outcome_label
```

Title:

```text
Glucose Category Distribution by Outcome
```

### 2. BMI Category by Outcome

Visual type:

```text
Stacked bar chart
```

Fields:

```text
Y-axis: bmi_category
X-axis: Count of patient_id
Legend: outcome_label
```

Title:

```text
BMI Category Distribution by Outcome
```

### 3. Glucose vs BMI

Visual type:

```text
Scatter chart
```

Fields:

```text
X-axis: Glucose
Y-axis: BMI
Legend: outcome_label
Size: Age
```

Title:

```text
Glucose vs BMI by Diabetes Outcome
```

### 4. Age vs Glucose

Visual type:

```text
Scatter chart
```

Fields:

```text
X-axis: Age
Y-axis: Glucose
Legend: outcome_label
Size: BMI
```

Title:

```text
Age vs Glucose by Diabetes Outcome
```

### 5. Feature Summary Table

Visual type:

```text
Table
```

Fields:

```text
outcome_label
Average Glucose
Average BMI
Average Age
Average Blood Pressure
Average Insulin
```

Title:

```text
Average Health Indicators by Outcome
```

---

# Page 3: Model Performance & Prediction Insights

## Purpose

Explain the machine learning results and model prediction behavior.

## KPI Cards

Use card visuals for:

```text
Best Model
Best ROC-AUC
Best Recall
Best F1 Score
Prediction Accuracy
Average Diabetes Probability
```

For Best Model, you can use a table card or manually add a text box with the best model from `model_performance.csv`.

## Visuals

### 1. Model Performance Comparison

Visual type:

```text
Clustered bar chart
```

Fields:

```text
Y-axis: model
X-axis: roc_auc
```

Title:

```text
Model Comparison by ROC-AUC
```

### 2. Model Recall Comparison

Visual type:

```text
Clustered bar chart
```

Fields:

```text
Y-axis: model
X-axis: recall
```

Title:

```text
Model Comparison by Recall
```

### 3. Feature Importance

Visual type:

```text
Bar chart
```

Fields:

```text
Y-axis: feature
X-axis: importance
```

Sort descending by importance.

Title:

```text
Top Diabetes Risk Prediction Factors
```

### 4. Prediction Probability by Actual Outcome

Visual type:

```text
Histogram or column chart
```

Fields:

```text
X-axis: diabetes_probability
Legend: actual_label
```

Title:

```text
Predicted Diabetes Probability Distribution
```

### 5. Risk Group Summary

Visual type:

```text
Column chart
```

Fields:

```text
X-axis: risk_group
Y-axis: patient_count
```

Title:

```text
Patients by Predicted Risk Group
```

---

## Design Style

Use a professional healthcare analytics style:

```text
Background: White or very light grey
Primary color: Deep blue
Accent color: Teal or soft green
Warning color: Orange or red only for high-risk labels
Font: Segoe UI
```

## Layout Recommendation

```text
Top row: title and slicers
Second row: KPI cards
Middle row: main visuals
Bottom row: detailed tables or supporting visuals
```

Keep spacing consistent and avoid overcrowding the page.

---

## Export Screenshots for GitHub

After creating the Power BI dashboard, export screenshots with these names:

```text
images/dashboard_patient_overview.png
images/dashboard_risk_factor_analysis.png
images/dashboard_model_performance.png
```

These images will be used in the final README.
