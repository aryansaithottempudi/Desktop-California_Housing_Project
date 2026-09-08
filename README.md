# California Housing Price Prediction

## Overview

This project predicts California median house values using **Linear Regression, Ridge Regression, and Lasso Regression**. The main objective is to compare these models, analyze the effect of regularization on coefficients, and determine which model generalizes best.

## Dataset

The project uses the **California Housing Prices** dataset.

* **Rows:** 20,640
* **Target:** `median_house_value`
* **Train/Test Split:** 80% / 20%

Main features include:

* Longitude
* Latitude
* Housing median age
* Total rooms
* Total bedrooms
* Population
* Households
* Median income
* Ocean proximity

## Data Preprocessing

The following preprocessing steps were performed:

* Missing numerical values were filled using median imputation.
* `ocean_proximity` was converted using One-Hot Encoding.
* Numerical features were standardized using `StandardScaler`.
* The data was split into 80% training and 20% testing data.

## Models Used

1. **Linear Regression** — Baseline regression model.
2. **Ridge Regression** — Uses L2 regularization to reduce coefficient magnitudes.
3. **Lasso Regression** — Uses L1 regularization and can reduce coefficients to zero.

## Model Performance

| Model             |            MAE |           RMSE |         R² |
| ----------------- | -------------: | -------------: | ---------: |
| Linear Regression |     $50,670.49 | **$70,059.19** | **0.6254** |
| Ridge Regression  |     $50,676.92 |     $70,066.02 | **0.6254** |
| Lasso Regression  | **$50,669.89** |     $70,082.94 |     0.6252 |

## Best Model

**Linear Regression** performed best overall.

It achieved the lowest RMSE of approximately **$70,059** and an R² score of **0.6254**.

The train R² was **0.6497** and test R² was **0.6254**, resulting in a small gap of **0.0242**. This indicates that the model generalizes reasonably well to unseen data.

## Regularization Results

Ridge Regression reduced the magnitude of the coefficients without setting them to zero.

Lasso Regression performed stronger feature selection and reduced **2 coefficients to zero**.

Overall, Ridge and Lasso did not significantly improve prediction performance compared with standard Linear Regression for this dataset and train/test split.

## Evaluation Metrics

Models were compared using:

* MAE — Mean Absolute Error
* MSE — Mean Squared Error
* RMSE — Root Mean Squared Error
* R² — Coefficient of Determination

## Technologies

* Python
* Pandas
* NumPy
* Scikit-learn
* Matplotlib
* Jupyter Notebook

## Conclusion

Linear Regression was selected as the best model because it achieved the strongest overall performance on unseen test data.

Regularization demonstrated its effect on model coefficients, particularly with Lasso performing feature selection, but it did not provide a meaningful improvement in predictive performance.

## Author

**Aryan Sai**
