# 04-Support-Vector-Machines

## Task 1: Quadratic Distribution Classification
- Dataset: [04-svm-dataset-task-1.csv](04-svm-dataset-task-1.csv) (randomly generated, 400 rows)
- Code Base Link: [Notebook Link](https://github.com/sarvan-2187/23CSE301-ML-LAB/blob/main/04-Support-Vector-Machines/svm-task-1.ipynb)

### Solution
A random dataset of 400 points is generated with X1 in [-3, 3] and X2 in [-3, 8]. Each point is labelled Class 1 if it lies above the quadratic curve X2 = X1² − 2 (with Gaussian noise), otherwise Class 0. After an 80:20 split, a linear-kernel SVM reaches only 78.75% accuracy because it can only draw a straight line. A degree-2 polynomial-kernel SVM (coef0=1, C=10, with StandardScaler) learns the parabola and reaches 92.5% accuracy. The model is evaluated using accuracy, a confusion matrix and a classification report, and the decision boundaries of both kernels are plotted side by side.

## Task 2: Email Spam Classification
- Dataset: [04-svm-dataset-task-2.csv](04-svm-dataset-task-2.csv) (synthetic, 500 rows)
- Code Base Link: [Notebook Link](https://github.com/sarvan-2187/23CSE301-ML-LAB/blob/main/04-Support-Vector-Machines/svm-task-2.ipynb)

### Solution
Each email has word-frequency features (Freq_Free, Freq_Money, Freq_Win, Freq_Meeting), Exclamation_Count and Message_Length, with Spam (1 = spam, 0 = not spam) as the target. The data is split 80:20 (stratified), and the features are scaled with StandardScaler because Message_Length is much larger than the word frequencies. An RBF-kernel SVM is then fit and reaches 87% accuracy, evaluated using a confusion matrix and a classification report. Finally, the model classifies two new example emails.
