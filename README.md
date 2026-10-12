# Flood Susceptibility Classification Using Logistic Regression

A beginner-friendly machine-learning portfolio project demonstrating binary classification with Python and scikit-learn in a civil/environmental engineering context.

## Important disclaimer

**The included dataset is synthetic and for learning only.** Its flood labels are generated from an illustrative probability rule, not observed flood events. Model scores and probabilities must not be interpreted as real-world flood risk, used for warnings, or used for engineering decisions.

## Objective

Use rainfall, temperature, soil moisture, and slope to demonstrate classification of records into:
- `0`: No flood
- `1`: Flood

## Repository contents

- `flood_susceptibility_logistic_regression.ipynb` — documented notebook with the full workflow and explanatory notes.
- `flood_susceptibility_synthetic.csv` — 500 synthetic records for reproducible practice.
- `PROJECT_NOTES.md` — concepts, metric definitions, and interpretation guidance.
- `requirements.txt` — Python packages.

## How to run

### Google Colab
1. Download this repository as a ZIP or upload the notebook and CSV to Colab.
2. Keep the notebook and CSV in the same Colab working directory, or update the CSV path.
3. Run the notebook cells from top to bottom.

### Local Python
```bash
pip install -r requirements.txt
jupyter notebook flood_susceptibility_logistic_regression.ipynb
```

## Workflow

1. Load and inspect the dataset.
2. Explore class distribution and selected feature relationships.
3. Define features (`X`) and target (`y`).
4. Split into training and test sets using stratification.
5. Train a pipeline with `StandardScaler` and `LogisticRegression`.
6. Predict classes and probabilities.
7. Evaluate with accuracy, precision, recall, F1-score, confusion matrix, and ROC-AUC when appropriate.
8. Inspect coefficients and make an illustrative prediction for a new case.

## Key concepts

- `X`: predictor columns.
- `y`: target class (`flood`).
- `fit()`: trains the pipeline.
- `predict()`: returns class labels.
- `predict_proba()`: returns estimated class probabilities.
- Precision: how many predicted positives are positive in the labelled test data.
- Recall: how many actual positives are detected.
- Confusion matrix: summarizes correct and incorrect predictions by class.

## Limitations and responsible use

This is a programming and learning demonstration, not a validated hydrological model. It does not represent observed catchment conditions, account for flood mechanisms in a physically grounded way, or establish causal relationships. A credible applied study requires quality-controlled observations, documented data provenance, temporal/spatial validation, baseline comparisons, and uncertainty analysis.

## Suggested future improvements

- Replace synthetic records with a documented real dataset.
- Validate on a separate catchment or time period.
- Compare Logistic Regression with Decision Tree and Random Forest baselines.
- Evaluate probability calibration and class imbalance.
- Document data licensing and reproducible preprocessing.
