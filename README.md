# Diabetes prediction with XGBoost

> Course assignment from 2023, kept as it was written. The notes under "Reading the result" were added in November 2026.

Classifies diabetes on the Pima Indians dataset (768 women, 268 with diabetes, 8 measurements)
with XGBoost, using scikit-learn's grid search and randomised search.

## Result

| Evaluation | Value |
|---|---|
| 10-fold cross-validated accuracy | 0.771 |
| Hold-out (154 patients): accuracy | 0.773 |
| Hold-out: precision / recall / F1 for diabetes | 0.75 / 0.55 / 0.63 |

Predicting "no diabetes" for everyone scores 0.651.

## Reading the result

- **Nothing was tuned.** Each parameter list in the grid holds one value, so both searches
  evaluate the same single model (a linear booster). The searches show the API, not a tuned model.
- The model misses 45% of the diabetic patients in the hold-out set (25 of 55). For screening,
  the threshold would have to move.
- Zeros in glucose, blood pressure, skin thickness, insulin and BMI are missing values in this
  dataset. The notebook treats them as measurements.

## Newer work on the same topic

- [credit-risk-scorecard](https://github.com/faiqrasulov/credit-risk-scorecard): nested cross-validation for tuning, calibration and cost-based thresholds.

## Files

| File | Content |
|---|---|
| `Diabetes_Dataset.ipynb` | Analysis |
| `Diabetes_Dataset.html` | Rendered copy |
| `diabetes.csv` | The dataset |
| `About.txt` | Original brief |
