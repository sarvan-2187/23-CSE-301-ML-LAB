# 01-Linear-Regression

- Start Date: 25-06-2026
- End Date: 25-06-2026
- Dataset Link: [Dataset](https://amritacampuschennai-my.sharepoint.com/:x:/g/personal/ch_sc_u4cse24130_ch_students_amrita_edu/IQDQKt_-f8PPT4l8Pe8E2jmLAaNgetvuvzM6LH6MYEL_uUg?e=OQiaAk)

## Problem Statement Chosen:
<img width="850" height="400" alt="image" src="https://github.com/user-attachments/assets/ec319f5d-b965-4daa-a66a-b51ddbb26603" />

## Task 1: Taxi Fare Prediction
- Dataset: [City of Chicago Taxi Trips](01-linear-regression-dataset-task-1.csv)
- Code Base Link: [Notebook Link](https://github.com/sarvan-2187/23CSE301-ML-LAB/blob/main/01-Linear-Regression/linear-regression-task-1.ipynb)

### Solution
The payment_type column is transformed into a binary Payment_Card column, 1 if Credit Card and 0 otherwise. Rows missing trip_seconds, trip_miles or fare are dropped. The remaining data is split 80:20 into train and test sets, with trip_miles, trip_seconds and Payment_Card as the independent variables and fare as the target. The final MAE, MSE, R^2 scores are calculated.

## Task 2: Body Weight Prediction
- Dataset: [Dataset](01-linear-regression-dataset-task-2.csv)
- Code Base Link: [Notebook Link](https://github.com/sarvan-2187/23CSE301-ML-LAB/blob/main/01-Linear-Regression/linear-regression-task-2.ipynb)

### Solution
Firstly, as the model cannot understand Male or Female, that particular column is transformed as Gender_Male and is 1 if Male Gender and 0 if female. The given data of 10 rows has been split into 80:20 train & test sets and then the independent variables Height, Age, Gender_Male are given to X and output variable weight is given to y for training. The final RMSE, MAE, R^2 Scores are also been calculated.