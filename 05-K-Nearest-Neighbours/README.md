# 05-K-Nearest-Neighbours

## Task 1: Handwritten Digit Recognition
- Dataset: [digits.zip](digits.zip), taken from [pbharrin/machinelearninginaction (Ch02)](https://github.com/pbharrin/machinelearninginaction/tree/master/Ch02)
- Code Base Link: [Notebook Link](https://github.com/sarvan-2187/23CSE301-ML-LAB/blob/main/05-K-Nearest-Neighbours/knn-task-1.ipynb)

### Solution
The dataset contains 1934 training and 946 test samples of the handwritten digits 0–9. Each digit is a 32x32 grid of 0s and 1s stored as a text file. The notebook reads every sample directly from the zip file and flattens it into a 1024-length vector (`img2vector`). The book's `classify0` kNN classifier, ported to Python 3, computes the Euclidean distance from each new sample to every training sample and returns the majority label of the k=3 nearest neighbours. It reaches 98.84% accuracy on the test set (11 errors out of 946), and scikit-learn's `KNeighborsClassifier` gives the same result. The model is evaluated using a confusion matrix and a classification report, some misclassified digits are displayed, and one new sample is shown next to its three nearest training neighbours.

## Task 2: Euclidean Distance for a New Entry
- Dataset: [05-knn-dataset-task-2.csv](05-knn-dataset-task-2.csv) (the Brightness / Saturation / Class table from the exercise)
- Code Base Link: [Notebook Link](https://github.com/sarvan-2187/23CSE301-ML-LAB/blob/main/05-K-Nearest-Neighbours/knn-task-2.ipynb)

### Solution
The new entry is Brightness = 20, Saturation = 35. The Euclidean distance d = √((x₂ − x₁)² + (y₂ − y₁)²) from the new entry to each of the 7 existing rows is calculated and printed step by step, then the rows are ranked by distance. With k = 5, the nearest neighbours are 14.14 (Red), 25.0 (Red), 33.54 (Blue), 45.28 (Blue) and 47.17 (Red). That gives 3 Red votes to 2 Blue, so the new entry is classified as **Red**. scikit-learn's `KNeighborsClassifier` gives the same prediction, and a scatter plot shows the new entry with lines to its 5 nearest neighbours.

| Brightness | Saturation | Class | Distance |
|---|---|---|---|
| 10 | 25 | Red | 14.14 |
| 40 | 20 | Red | 25.00 |
| 50 | 50 | Blue | 33.54 |
| 25 | 80 | Blue | 45.28 |
| 60 | 10 | Red | 47.17 |
| 70 | 70 | Blue | 61.03 |
| 60 | 90 | Blue | 68.01 |
