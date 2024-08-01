# Credit Card Fraud Detection

## Dependencies

Libraries used are likely standard.
xgboost: https://xgboost.readthedocs.io/en/stable/install.html#conda
Dataset: https://www.kaggle.com/datasets/dhanushnarayananr/credit-card-fraud/data

## Data Preprocessing

- There were no null values, so no imputation required.
- The `fraud` class is unbalanced, (only 8.7% are fraudulent). Therefore, I will use a metric that emphasizes recall (likely F2 score) to minimize false negatives.
- Some features have extreme outliers (skewed right), so I will normalize with MinMaxScaler (removing outliers not an option). The other columns are binary, so they are unaffected.
- I will stratify split based on the fraud class to keep the same distribution of fraud in my training and test set.

## Training first model

- I picked RandomForestClassifer with a moderate 25 trees. The metrics were abnormally high, both for the training and testing set.
- I will consider some other models to compare to random forest.
