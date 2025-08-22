## Dataset
The dataset is the Diabetes Dataset from the National Institute of Diabetes and Digestive and Kidney Diseases. It aims to predict whether a patient has diabetes based on diagnostic measurements. 

### Source
[Kaggle](https://www.kaggle.com/datasets/akshaydattatraykhare/diabetes-dataset)

## Feature Description

This dataset includes the following attributes related to diagnostic measurements:

| Feature                     | Description                                                                 |
| --------------------------- | --------------------------------------------------------------------------- |
| 1. Pregnancies              | Number of times a patient has been pregnant.                                |
| 2. Glucose                  | Plasma glucose concentration 2 hours after an oral glucose tolerance test.  |
| 3. BloodPressure            | Diastolic blood pressure (mm Hg).                                         |
| 4. SkinThickness            | Triceps skin fold thickness (mm).                                           |
| 5. Insulin                  | 2-Hour serum insulin (mu U/ml).                                             |
| 6. BMI                      | Body mass index (weight in kg / (height in m)^2).                           |
| 7. DiabetesPedigreeFunction | A function that scores likelihood of diabetes based on family history.      |
| 8. Age                      | Age of the patient in years.                                                |
| 9. Outcome                  | The class variable (0 for non-diabetic, 1 for diabetic).                  |

## Goals

### Risk Factor Analysis

- What is the distribution of diabetes diagnoses across different age groups? This would help to identify which age brackets are most affected by the disease.

- Is there a clear relationship between BMI and diabetes? This could analyze whether patients with higher BMI values have a significantly higher rate of diabetes.

- How does a history of Pregnancies affect the likelihood of a diabetes diagnosis? This could reveal insights into the prevalence of gestational diabetes or its long-term effects.

- Does the presence of Hypertension or HeartDisease significantly increase a patient's risk of diabetes? By comparing the Outcome for patients with and without these conditions, we can quantify their impact.

- What is the optimal threshold for Glucose or BMI that best distinguishes between diabetic and non-diabetic patients? You could perform a threshold analysis to find a cutoff value for these continuous features that maximizes the model's accuracy.

## Key Insights

*   **Feature Distributions:**
    *   Several features (Glucose, BloodPressure, SkinThickness, Insulin, and BMI) had records with a value of 0, which is physiologically impossible for some of these metrics. These were treated as missing values.
    *   `Pregnancies`, `DiabetesPedigreeFunction`, and `Age` show right-skewed distributions.
    *   `Glucose`, `BloodPressure`, `SkinThickness`, `Insulin`, and `BMI` show approximately normal distributions with varying degrees of skewness and outliers.
*   **Data Cleaning and Imputation:** Records with a high number of zero values across key features were removed. Zero values in `Glucose`, `BloodPressure`, and `BMI` were imputed with the median of non-zero values, while zero values in `SkinThickness` and `Insulin` were imputed with the mean of non-zero values.
*   **Bivariate Analysis (Predictors vs. Outcome):**
    *   `Glucose`, `BMI`, and `Age` appear to be the strongest individual predictors of diabetes, with higher values generally associated with a higher likelihood of diabetes.
    *   `Pregnancies` and `DiabetesPedigreeFunction` also show some predictive power, with higher values more common in the diabetic group.
    *   `BloodPressure`, `SkinThickness`, and `Insulin` show weaker individual relationships with the outcome, although the distribution and outliers for `Insulin` in the diabetic group are notable.
*   **Bivariate Analysis (Predictors vs. Predictors):**
    *   Moderate positive correlations exist between `Age` and `Pregnancies`, `Glucose` and `Insulin`, and `BMI` and `SkinThickness`. These relationships are generally expected but could indicate potential multicollinearity for certain modeling techniques.
*   **Correlation Heatmap:** Confirmed the bivariate findings, highlighting `Glucose` as the strongest predictor based on linear correlation, followed by `BMI`, `Age`, and `Pregnancies`. It also quantified the relationships between predictor variables.