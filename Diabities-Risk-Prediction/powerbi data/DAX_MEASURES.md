# Recommended Power BI DAX Measures

Create these measures in Power BI, preferably inside the `fact_patients` table.

```DAX
Total Patients = COUNTROWS(fact_patients)
```

```DAX
Diabetes Positive Patients = 
CALCULATE(
    COUNTROWS(fact_patients),
    fact_patients[Outcome] = 1
)
```

```DAX
No Diabetes Patients = 
CALCULATE(
    COUNTROWS(fact_patients),
    fact_patients[Outcome] = 0
)
```

```DAX
Diabetes Positive Rate = 
DIVIDE([Diabetes Positive Patients], [Total Patients])
```

```DAX
Average Glucose = AVERAGE(fact_patients[Glucose])
```

```DAX
Average BMI = AVERAGE(fact_patients[BMI])
```

```DAX
Average Age = AVERAGE(fact_patients[Age])
```

```DAX
Average Blood Pressure = AVERAGE(fact_patients[BloodPressure])
```

```DAX
Average Insulin = AVERAGE(fact_patients[Insulin])
```

```DAX
Average Diabetes Probability = AVERAGE(diabetes_predictions[diabetes_probability])
```

```DAX
Correct Predictions = 
CALCULATE(
    COUNTROWS(diabetes_predictions),
    diabetes_predictions[prediction_correct] = TRUE()
)
```

```DAX
Prediction Accuracy = 
DIVIDE([Correct Predictions], COUNTROWS(diabetes_predictions))
```

## Formatting

- `Diabetes Positive Rate`: Percentage, 1 decimal place
- `Average Glucose`: Decimal, 1 decimal place
- `Average BMI`: Decimal, 1 decimal place
- `Average Age`: Decimal, 1 decimal place
- `Average Diabetes Probability`: Percentage, 1 decimal place
- `Prediction Accuracy`: Percentage, 1 decimal place
