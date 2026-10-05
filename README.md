# Student Performance Prediction

Machine-learning course project. Predicts three recommendation categories for university
students from survey and academic data (894 records, 31 features).

## Results

| Task | Best model | Accuracy |
|---|---|---|
| CGPA Improvement Action | Random Forest | 96.09% |
| Recommended Future Focus | Random Forest | 87.15% |
| Predicted Strength Area | Random Forest | 79.89% |

Models compared: Random Forest, Decision Tree, K-Nearest Neighbors, Gaussian Naive Bayes.
80/20 train-test split, `random_state=42`.

## Files

| File | Description |
|---|---|
| `finalproject.ipynb` | Full analysis — outputs included, no need to run |
| `IUBAT_Student_Performance_Dataset.csv` | Raw survey export |
| `IUBAT_Student_Performance_Dataset_Final.csv` | With the three derived target columns (the notebook reads this) |
| `1.png`, `2.png`, `3.png` | Model accuracy comparisons |
| `confusion matrix.png`, `CM_Predicted_Strength_Area.png` | Confusion matrices |
| `ML Paper.pdf` | Write-up |

## Running

```
pip install pandas numpy scikit-learn matplotlib seaborn
jupyter notebook finalproject.ipynb
```

Note: written for pandas 2.x. On pandas 3.0 the `dtype == 'object'` checks need to become
`pd.api.types.is_numeric_dtype()`, since text columns now carry the `str` dtype.

## Note on the targets

The three target columns are derived from the feature columns by rule — they are empty in the
raw CSV and populated in the `_Final` one. The models therefore measure how well each
algorithm recovers that rule rather than predicting unseen student outcomes.
