Data Pipeline – MLOps Iris Classifier

PIPELINE OVERVIEW

Data Collection
      ↓
Data Preprocessing
      ↓
Feature Engineering
      ↓
Data Validation


1. DATA COLLECTION

Purpose:
Collect the Iris dataset and store it in the raw data zone.

Input:
Iris dataset from scikit-learn.

Output:
data/raw/iris_raw.csv

Operations:
- Load the Iris dataset
- Convert target values into species names
- Add collection timestamp
- Save the raw dataset


2. DATA PREPROCESSING

Purpose:
Clean and prepare the collected dataset.

Input:
data/raw/iris_raw.csv

Output:
data/processed/iris_preprocessed.csv

Operations:
- Remove duplicate records
- Correct numeric data types
- Handle missing numeric values
- Remove rows with missing target values
- Remove collection timestamp


3. FEATURE ENGINEERING

Purpose:
Create useful new features from the processed data.

Input:
data/processed/iris_preprocessed.csv

Output:
data/processed/iris_features.csv

Features Created:
- sepal_area
- petal_area
- sepal_to_petal_length_ratio
- petal_length_bin


4. DATA VALIDATION

Purpose:
Check whether the processed data is valid.

Input:
data/processed/iris_features.csv

Validation Rules:
- Required columns must exist
- No unexpected null values
- Species values must be valid
- Numerical values must be within expected ranges

Result:
Validation PASSED → pipeline can continue.
Validation FAILED → pipeline stops.


DVC PIPELINE

collect
   ↓
preprocess
   ↓
features
   ↓
validate


DVC DEPENDENCY FLOW

data/raw/iris_raw.csv
        ↓
preprocess.py
        ↓
data/processed/iris_preprocessed.csv
        ↓
features.py
        ↓
data/processed/iris_features.csv
        ↓
validate.py
        ↓
Validation Result


VERIFICATION COMMANDS

dvc repro
dvc dag

A second dvc repro without changes skips unchanged stages.