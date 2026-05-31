# Texas Employee Salary Prediction

# Project Overview

The goal of this project is to analyze and predict salary patterns of government employees working for the State of Texas using historical payroll data.

This project focuses on:

* Understanding salary distributions across departments, job titles, and demographics
* Identifying unusually high or low salaries (outliers)
* Analyzing wage disparities between managers and non-managers
* Building machine learning models to predict employee salaries

The project combines data analysis, visualization, feature engineering, and machine learning techniques to create a reliable salary prediction framework.

---

# Domain Analysis — Texas State Employee Salary

This project belongs to the **public sector payroll domain**, focusing on Texas state government employees.

The Texas government employs thousands of workers across different agencies and departments. Employee salaries are influenced by:

* Job role
* Department
* Experience
* Work hours
* Employment category

Accurate salary prediction and analysis can help in:

* Budget planning
* Payroll transparency
* Workforce analytics
* Wage disparity analysis
* Compensation management

Machine learning models help uncover hidden salary patterns and support data-driven decision-making for fair and efficient compensation management.

---

# Problem Statement

### Task 1

Prepare a complete exploratory data analysis report on the employee salary dataset.

### Task 2

Build predictive machine learning models to estimate employee salaries.

### Task 3

Analyze:

* Salary outliers
* Wage disparities between managers and employees
* Factors influencing salary predictions

---

# Dataset Information

The dataset contains Texas government employee payroll records.

## Important Features

* AGENCY
* AGENCY NAME
* CLASS CODE
* CLASS TITLE
* ETHNICITY
* GENDER
* STATUS
* HRLY RATE
* HRS PER WK
* MONTHLY
* ANNUAL
* STATE NUMBER
* multiple_full_time_jobs
* combined_multiple_jobs
* summed_annual_salary

## Target Variable

```python id="mohg9t"
ANNUAL
```

The target variable represents the annual salary of employees.

---

# Data Preprocessing

Several preprocessing steps were performed before model training.

## Steps Performed

1. Loaded and inspected the raw dataset.

2. Handled missing and null values.

3. Standardized column names and corrected data types.

4. Converted date-related columns into useful features where required.

5. Removed unnecessary text columns such as:

   * FIRST NAME
   * LAST NAME

6. Identified and removed data leakage columns such as:

   * MONTHLY
   * summed_annual_salary

7. Encoded categorical variables.

8. Prepared clean data for exploratory analysis and modeling.

---

# Exploratory Data Analysis (EDA)

EDA was performed to understand salary patterns and feature relationships.

## Analysis Performed

* Distribution analysis of annual salaries
* Department-wise salary comparison
* Gender and ethnicity salary trends
* Correlation analysis
* Outlier detection
* Work-hours vs salary analysis
* Agency-wise payroll comparison

## Visualizations Used

* Histograms
* Boxplots
* Bar charts
* Heatmaps
* Correlation matrix
* Salary distribution plots

---

# Task 3 Analysis

## 1. Salary Outliers

### Approach

The Interquartile Range (IQR) method was used to identify salary outliers in the annual salary column.

Outliers were defined as salaries:

* Below Q1 − 1.5 × IQR
* Above Q3 + 1.5 × IQR

### Findings

The analysis showed that a small percentage of employees had significantly higher salaries than the overall distribution.

These generally corresponded to:

* Executive positions
* Specialized technical staff
* Senior management roles

Such salaries often reflect:

* Higher experience
* Specialized skills
* Leadership responsibilities

---

## 2. Wage Disparities Between Managers and Employees

### Approach

Departments and job titles were grouped to compare:

* Mean salary
* Median salary

between:

* Managers
* Non-managers

### Findings

The largest wage disparities were observed in:

* Public Safety
* Information Technology
* Health Services

These gaps are likely caused by:

* Hierarchical differences
* Specialized managerial responsibilities
* Experience requirements

---

# Modeling & Evaluation

Multiple regression models were trained and compared.

## Models Used

* Linear Regression
* Decision Tree Regressor
* Random Forest Regressor
* Gradient Boosting Regressor
* XGBoost Regressor
* Ridge Regression
* Support Vector Regressor (SVR)
* K-Nearest Neighbors (KNN)

---

# Model Evaluation Metrics

The models were evaluated using:

* R² Score
* Mean Absolute Error (MAE)
* Root Mean Squared Error (RMSE)

---

# Final Outcome

## Best Model

```python id="vh44pf"
XGBoost Regressor (Tuned)
```

## Final Performance

* **R² Score:** 0.9229
* **MAE:** 508.46
* **RMSE:** 1039.39

The final model achieved strong predictive performance and successfully captured complex salary relationships.

---

# Why XGBoost Performed Best

XGBoost outperformed other models because it:

* Handles complex feature interactions effectively
* Performs well with mixed data types
* Reduces overfitting using regularization
* Handles missing values efficiently
* Provides strong predictive accuracy

---

# Feature Importance Analysis

The most influential salary prediction features were:

* HRLY RATE
* HRS PER WK
* CLASS TITLE
* AGENCY NAME
* EMPLOYMENT STATUS

These features had the strongest impact on salary estimation.

---

# Challenges Faced During The Project

* Missing values in several columns
* Presence of salary outliers
* Skewed salary distributions
* Risk of data leakage
* Encoding high-cardinality categorical features
* Managing correlated variables
* Preventing model overfitting
* Hyperparameter tuning complexity

Despite these challenges, systematic preprocessing and model evaluation helped achieve reliable results.

---

# Key Insights

| Question        | Insight Summary                                          |
| --------------- | -------------------------------------------------------- |
| Salary Outliers | Mostly executives and senior technical staff             |
| Wage Disparity  | Highest in Public Safety, IT, and Health departments     |
| Salary Trends   | General upward trend with some departmental fluctuations |

---

# Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* XGBoost
* Jupyter Notebook

---

# Project Structure

Texas-Employee-Salary-Prediction

* Dataset
   * salary.csv
* Notebooks
   * Texas Salary Predictions Project.ipynb
* README.md


---

# How to Run the Project

## Step 1: Clone the Repository

```bash id="jqlf6j"
git clone <your-github-repository-link>
```

---

## Step 2: Navigate to the Project Folder

```bash id="fy1f7n"
cd PRCP-1024-Texas-Employee-Salary-Prediction
```

---

## Step 3: Install Required Libraries

```bash id="4xqfqn"
pip install -r requirements.txt
```

---

## Step 4: Launch Jupyter Notebook

```bash id="7ydv4h"
jupyter notebook
```

---

## Step 5: Open the Notebook

Run all notebook cells step by step to:

* Perform data preprocessing
* Execute exploratory data analysis
* Train regression models
* Evaluate model performance
* Generate salary predictions

---

# Future Scope

* Deploy the model using Flask or Streamlit
* Build an interactive salary analytics dashboard
* Integrate real-time payroll forecasting
* Include employee experience and education features
* Perform time-series salary forecasting
* Improve explainability using SHAP values

---

# Conclusion

The Texas Employee Salary Prediction project successfully developed a machine learning framework for analyzing and estimating employee salaries using Texas state payroll data.

Through data preprocessing, exploratory data analysis, feature engineering, outlier handling, encoding, and scaling, the dataset was prepared for predictive modeling.

Multiple regression models were trained and compared, including:

* Linear Regression
* Decision Tree
* Random Forest
* Gradient Boosting
* XGBoost
* Ridge
* SVR
* KNN

After hyperparameter tuning, XGBoost achieved the best performance with an R² score of 0.9229.

The project demonstrates how ensemble machine learning techniques can effectively predict real-world salary structures and support payroll transparency, compensation analysis, and workforce planning.

# Authors

* Ayush Uniyal
* Vipin
* Shubha
* Aadi
* Hemanth Kumar
