## zoo-decision-tree-ccp

I built this because I wanted to understand what actually happens when a decision tree learns, how and why it works the way it does

The UCI Zoo dataset is small(101 animals, 16 binary features, 7 classes) which makes it perfect for learning.



## what this project does

Trains a Decision Tree on the Zoo dataset, then prunes it using Cost Complexity Pruning (CCP).

The unpruned tree had a depth of 8 and 16 leaves. After tuning the alpha parameter to `0.0163`, it settled at depth 7 and 9 leaves — same 90.5% accuracy, with significantly less noise.


## stack

- Python 3.9
- scikit-learn
- pandas
- matplotlib
- graphviz

---

## dataset

[UCI Zoo Dataset](https://archive.ics.uci.edu/ml/datasets/zoo) — 101 animals, 16 boolean features (hair, feathers, eggs, milk, airborne, aquatic, etc.), 7 animal classes.

---

## results

| | Full Tree | Pruned Tree |
|---|---|---|
| Accuracy | 90.5% | 90.5% |
| Depth | 8 | 7 |
| Leaves | 16 | 9 |
| Alpha (α) | 0 | 0.0163 |


---

## visualizations

Six panels are covered:

- accuracy comparison (full vs pruned)
- tree complexity (depth & leaves side by side)
- alpha vs test accuracy curve 
- confusion matrix for the full tree
- confusion matrix for the pruned tree
- feature importance for the pruned tree — `milk` and `feathers` are the most impactful features

---

## how to run

```bash
git clone https://github.com/kgadharsh/zoo-decision-tree-ccp
cd zoo-decision-tree-ccp
pip install -r requirements.txt
jupyter notebook
```

Download the dataset from UCI and place `zoo.csv` and `class.csv` in the project directory.

---

## what I learned

I learned that a tree can still maintain its accuracy despite losing a few branches. Effective pruning removes unnecesary data from the tree and retains only the meaningful information that actually contributes towards the classification.
