# 08-Random-Forest-Classifier

## Task 1: Fruit Basket Classification with Majority Voting
- Dataset: [08-rf-dataset-task-1.csv](08-rf-dataset-task-1.csv) (synthetic fruit basket, 450 fruits)
- Code Base Link: [Notebook Link](https://github.com/sarvan-2187/23CSE301-ML-LAB/blob/main/08-Random-Forest-Classifier/rf-task-1.ipynb)

### Solution
The fruit basket has 450 fruits (150 Apple, 90 Banana, 80 Orange, 70 Grapes, 60 Mango), each described by Weight_g, Diameter_cm, Length_cm, Sweetness and Colour (one-hot encoded). After an 80:20 split, the random forest from the figure is built by hand. 25 bootstrap samples are drawn from the basket (with replacement), and an individual decision tree is trained on each sample, using a random subset of features at each split.

Every tree then classifies a new instance: a yellow, round, 170 g fruit. **16 trees vote Apple and 9 vote Orange, so majority voting gives Apple as the final class.** scikit-learn's `RandomForestClassifier` (100 trees) agrees, with 72% of its trees voting Apple. On the test set:

| Model | Accuracy |
|---|---|
| Average individual tree (bootstrap sample) | 92.2% |
| Hand-built forest (majority vote of 25 trees) | 94.4% |
| Single full decision tree | 95.6% |
| scikit-learn RandomForestClassifier (100 trees) | 96.7% |

**Answer: Apple is the fruit likely to be taken most often.** It is the most common fruit in the basket, so it is also picked most often into each random sample (about 121 of 360 fruits per sample), and it wins the majority vote. The notebook also shows three of the trees, the vote tally, a confusion matrix, a classification report and the feature importances.
