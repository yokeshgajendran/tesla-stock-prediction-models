# esla Stock Price Prediction : A Comparison of Predictive Models

This project focuses on comparing three machine learning regression models — **Multiple Linear Regression**, **Decision Tree Regressor**, and **Random Forest Regressor** to identify the most effective model for predicting **Tesla's stock closing price**.

---

## Objective

To evaluate and compare the performance of multiple supervised learning algorithms for forecasting Tesla stock prices, based on selected numerical features, and determine the most accurate and reliable model.

---

## Project Workflow

###  Data Preprocessing
- Loaded Tesla stock dataset and performed data overview.
- Engineered three new features:
  - **Daily Return**
  - **Daily Volume Change**
  - **Daily Price Range**
- Handled missing values using **median imputation**.
- Applied **min-max normalization**.
- Performed **descriptive statistical analysis**.

### Exploratory Data Analysis (EDA)
- Visualized trends in **closing prices** and **trading volume** to understand market behavior over time. This insight helps understand how stock prices and trading activity change over time, which supports the selection of meaningful features for accurate prediction.
- Created scatter plots to explore the relationship between engineered features and closing price.
- Calculated and visualized a **correlation matrix**.
- Based on EDA and correlation results, selected **High**, **Low**, and **Open** as the input features.

### Model Implementation & Training
- Trained the following models on selected features:
  - **Multiple Linear Regression**
  - **Decision Tree Regressor**
  - **Random Forest Regressor**
- Used standard splitting **80/20 split** for training and testing datasets.

#### Basis for Model Selection
- **Multiple Linear Regression**: A simple, interpretable baseline model effective for linear relationships.
- **Decision Tree**: Captures **nonlinear** relationships and handles feature interaction.
- **Random Forest**: An **ensemble** model that improves accuracy and reduces overfitting.

---

## Model Evaluation

### Metrics Used
- **MAE** (Mean Absolute Error) – Measures average absolute error.
- **MSE** (Mean Squared Error) – Penalizes larger errors more heavily.
- **RMSE** (Root Mean Squared Error) – More interpretable version of MSE.
- **R²** (Coefficient of Determination) – Measures variance explained by the model.
- **Adjusted R²** – Adjusted for number of predictors.

Also performed **10-fold cross-validation** to evaluate the model's ability to generalize beyond the test set.

#### Importance of Cross-Validation
Even if a model performs well on a test split, **cross-validation** ensures **robustness** across multiple subsets, reducing variance and helping detect **overfitting**.

---

## Results Summary

### Direct Evaluation Scores

| Model                   | MAE    | MSE    | RMSE  | R²     | Adjusted R² |
|------------------------|--------|--------|-------|--------|-------------|
| Multi Linear Regression| 1.49   | 3.36   | 1.83  | 0.9972 | 0.9971      |
| Decision Tree          | 3.83   | 24.26  | 4.93  | 0.9798 | 0.9795      |
| Random Forest          | 2.32   | 8.47   | 2.91  | 0.9929 | 0.9928      |

### Cross-Validation Mean R² Scores

| Model                   | Mean R² Score |
|------------------------|----------------|
| Multi Linear Regression| 0.962          |
| Decision Tree          | 0.790          |
| Random Forest          | 0.898          |

---

## Conclusion

- **Multiple Linear Regression** outperformed other models in both evaluation metrics and cross-validation, indicating strong predictive power for **Tesla’s closing prices** based on **High**, **Low**, and **Open** values.
- Standard preprocessing and EDA helped identify the most relevant features for model training.
- **Cross-validation** confirmed the **consistency and generalizability** of the results.
