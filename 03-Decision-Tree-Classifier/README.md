# 03-Decision-Tree-Classifier

## Task 1: Purchase Prediction (Age & Income)
- Dataset: [03-decision-tree-dataset-task-1.csv](03-decision-tree-dataset-task-1.csv)
- Code Base Link: [Notebook Link](https://github.com/sarvan-2187/23CSE301-ML-LAB/blob/main/03-Decision-Tree-Classifier/decision-tree-task-1.ipynb)

### Solution
The dataset has 400 rows with User ID, Gender, Age, EstimatedSalary and a binary Purchased outcome. The data is split 80:20 with Age and EstimatedSalary (income) as the independent variables and Purchased as the target. A Gini-based decision tree classifier (max_depth=3) is fit. Its root node splits on Age at about 44.5 because that split makes the data purer than any other, and the next level splits on EstimatedSalary. The model is evaluated using accuracy, a confusion matrix and a classification report, and the tree is visualised with export_text and plot_tree.
