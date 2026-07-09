# 02-Logistic-Regression

## Task 1: Graduate Admission Prediction
- Dataset: [UCLA binary.dta](https://stats.idre.ucla.edu/stat/stata/dae/binary.dta), saved as [02-logistic-regression-dataset-task-1.csv](02-logistic-regression-dataset-task-1.csv)
- Code Base Link: [Notebook Link](https://github.com/sarvan-2187/23CSE301-ML-LAB/blob/main/02-Logistic-Regression/logistic-regression-task-1.ipynb)

### Solution
The dataset has 400 rows with GRE score, GPA, undergraduate institution rank and a binary admit outcome. The data is split 80:20 into train and test sets, with gre, gpa and rank as the independent variables and admit as the target. A logistic regression model is fit and evaluated using accuracy, a confusion matrix and a classification report.

## Task 2: Disease Susceptibility Prediction
- Dataset: [02-logistic-regression-dataset-task-2.csv](02-logistic-regression-dataset-task-2.csv)
- Code Base Link: [Notebook Link](https://github.com/sarvan-2187/23CSE301-ML-LAB/blob/main/02-Logistic-Regression/logistic-regression-task-2.ipynb)

### Solution
Disease, Gender and Smoker_status are transformed into binary columns (Diseased, Gender_Male, Is_Smoker). The 80:20 split uses Age, Gender_Male and Is_Smoker as independent variables and Diseased as the target for a logistic regression model, evaluated using accuracy, a confusion matrix and a classification report.
