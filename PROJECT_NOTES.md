# Project Notes: Logistic Regression for Flood Susceptibility Classification

## 1. Classification problem
Logistic Regression is used here for a binary target:
- `0` = No flood
- `1` = Flood

The model estimates the probability of class 1, then applies a decision threshold (0.5 by default) to produce a class label.

## 2. Features and target
- `rainfall_mm`: illustrative rainfall amount in millimetres.
- `temperature_c`: illustrative temperature in degrees Celsius.
- `soil_moisture_percent`: illustrative soil moisture percentage.
- `slope_percent`: illustrative slope percentage.
- `flood`: binary target label.

These are synthetic variables, not field observations.

## 3. Why split the data?
Training data is used to fit the model. Test data is held out to estimate performance on unseen rows from the same synthetic generation process. A random split does not establish transferability to real catchments or future periods.

## 4. Why use StandardScaler?
Scaling puts numeric features on comparable scales. The scaler is fitted only on the training set through a pipeline, reducing data leakage.

## 5. Evaluation measures
- **Accuracy** = correct predictions / all predictions.
- **Precision (class 1)** = true positives / (true positives + false positives).
- **Recall (class 1)** = true positives / (true positives + false negatives).
- **F1-score** = harmonic mean of precision and recall.
- **Confusion matrix** uses actual classes as rows and predicted classes as columns in scikit-learn.
- **ROC-AUC** measures how well predicted probabilities rank positive cases above negative cases.

For a safety-relevant application, recall and false negatives deserve careful attention, but the appropriate balance depends on the application and warning costs.

## 6. Coefficients
The pipeline standardizes features before fitting. Therefore, the coefficient table corresponds to standardized feature values. Positive coefficients increase the model's log-odds for class 1; negative coefficients decrease them, holding other variables fixed. These associations are not causal explanations.

## 7. Limitations
All records and labels in this project are synthetic. Performance metrics reflect an artificial dataset and should not be reported as evidence of real-world flood-prediction skill. Real application requires observed event labels, data quality assessment, leakage-aware validation, and uncertainty reporting.
