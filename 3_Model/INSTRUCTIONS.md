# Model Definition and Evaluation

## Overview

This milestone defines and evaluates a more sophisticated model for predicting deforestation increase, aiming to improve upon the baseline Logistic Regression. We used a deep learning approach that includes feature engineering, custom loss functions, and class imbalance handling.

## Guidelines

### Model Selection

We implemented a **deep neural network** using TensorFlow/Keras. The model architecture includes multiple dense layers with regularization, normalization, dropout, and LeakyReLU activations. This choice allows the model to capture complex, non-linear relationships in the data that the baseline model could not. Additionally, we used **focal loss** to address class imbalance and prioritize hard-to-classify instances.

### Feature Engineering

The final model includes both the baseline MapBiomas class features and several engineered features:

- MapBiomas land cover classes: 3, 6, 11, 15, 24, 33  
- Additional land cover/land use classes: 12, 25, 4  
- Temporal signal: `prev_count` (deforestation in previous year)  
- Interaction feature: `prev_count_x_33` (interaction between deforestation history and forest cover)  

Missing values in features 25 and 4 were filled with zero. Feature scaling was applied using `StandardScaler`.

### Hyperparameter Tuning

Key hyperparameters were manually selected through iterative testing:

- Learning rate: `3e-4`  
- Batch size: `16`  
- Epochs: up to `120` with early stopping (patience = 15)  
- Dropout rates: `0.4` and `0.3` for regularization  
- L2 regularization: `0.001` for dense layers  
- Focal loss parameters: `gamma=2`, `alpha=0.25`  

Early stopping with validation monitoring was used to avoid overfitting.

### Implementation

- Dataset split into train/validation/test (with stratification).
- Features scaled using `StandardScaler`.
- Class weights computed to address class imbalance.
- Model defined using a multi-layer dense architecture.
- Compiled with Adam optimizer and custom `FocalLoss`.
- Trained with early stopping and class weights.

### Evaluation Metrics

- **Accuracy**: ~68% — proportion of correct predictions.
- **F1 Score**: ~0.77 — accounts for precision/recall tradeoff.
- **ROC-AUC**: ~0.74 — ability to distinguish between classes.
- **Precision**: ~0.72 — proportion of predicted positives that were correct.
- **Recall**: ~0.83 — ability to find all positive cases.
- **Confusion Matrix**: used to analyze false positives/negatives.
- Threshold optimized for F1 score via sweep from 0.1 to 0.9.

A threshold of ~0.48 yielded the best F1 score.

### Comparative Analysis

Compared to the baseline model:

- Accuracy improved from ~59% to ~68%
- ROC-AUC improved from ~0.48 to ~0.74
- F1 Score increased from ~0.74 to ~0.77
- Substantially better precision and recall balance

The final model significantly outperforms the baseline, particularly in class separability (ROC-AUC) and recall, confirming its ability to better identify municipalities at risk of deforestation increase.