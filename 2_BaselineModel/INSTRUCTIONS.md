# Baseline Model

## Overview

The purpose of this milestone is to establish a baseline model for our deforestation prediction project. A baseline model serves as a simple reference point to evaluate the performance of more complex models in later stages.

## Guidelines

### Choice of Model

We selected **Logistic Regression** as our baseline model. It is appropriate for binary classification tasks such as predicting whether deforestation will occur (1) or not (0) in a given year. The reasons for this choice are:

- Simplicity and ease of interpretation.
- Low computational cost and minimal tuning requirements.
- It provides coefficient-based insights into feature importance.
- It performs reasonably well on imbalanced datasets when using `class_weight='balanced'`.

### Feature Selection

The model uses pixel counts of the following MapBiomas land cover classes, aggregated per municipality per year:

- **3** (Forest)
- **6** (Savanna)
- **11** (Wetland)
- **15** (Pasture)
- **24** (Agriculture)
- **33** (Other natural vegetation)

These features were chosen based on their relevance to land-use changes associated with deforestation. The target variable (`target`) is binary: 1 if deforestation occurred in the municipality-year, 0 otherwise. This was derived by spatially joining PRODES deforestation polygons with municipal boundaries and aggregating by year.

### Implementation

- Filtered both BR_Municipios and PRODES datasets to include only Amazonas.
- Performed a spatial join to count deforestation events per municipality-year.
- Created a binary target column based on the presence of deforestation.
- Merged the processed target with a dataset containing MapBiomas land cover features.
- Split the dataset into training and test sets (80/20).
- Trained a Logistic Regression model (`max_iter=1000`, `class_weight='balanced'`).
- Generated predictions and extracted model coefficients for interpretability.

### Evaluation

The model’s performance was assessed using:

- **Accuracy**: ~59% — correct predictions over all samples.
- **F1 Score**: ~0.74 — balance of precision and recall.
- **ROC-AUC**: ~0.48 — model’s ability to distinguish between classes.
- **Confusion Matrix**: revealed moderate classification performance.

A heatmap of the confusion matrix was plotted for visual assessment. While the F1 score is acceptable, the low ROC-AUC indicates poor discrimination between positive and negative cases. These results establish a clear baseline to compare future models with more complexity or additional features.