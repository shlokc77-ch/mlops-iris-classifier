# Hyperparameter Tuning Analysis

## 1. Baseline Model

Model:
DecisionTreeClassifier

CV F1 Macro:
0.9663

Test Accuracy:
0.9000

## 2. Grid Search

Model:
RandomForestClassifier

Total combinations:
72

Cross-validation:
5-fold

Total fits:
360

Best CV F1 Macro:
0.9663

Test Accuracy:
0.9667

Best Parameters:
- max_depth: 3
- max_features: sqrt
- min_samples_split: 2
- n_estimators: 50

## 3. Random Search

Model:
RandomForestClassifier

Number of iterations:
30

Cross-validation:
5-fold

Total fits:
150

Best CV F1 Macro:
0.9663

Test Accuracy:
0.9667

Best Parameters:
- max_depth: 3
- max_features: sqrt
- min_samples_split: 6
- n_estimators: 100

## 4. Comparison

Grid Search evaluates all combinations in the specified
hyperparameter grid.

Random Search evaluates a selected number of combinations
from the search space.

In this experiment, Grid Search required 360 model fits,
while Random Search required 150 model fits.

Both tuning approaches achieved the same CV F1 Macro
of 0.9663 in this experiment.

Both tuning approaches achieved a test accuracy of 0.9667.