
# An Electrochemical-Temporal Machine Learning Framework for Early Prediction of Next-Cycle Battery Degradation

## Overview

This repository contains the implementation of an electrochemical-temporal machine-learning framework for early prediction of next-cycle lithium-ion battery degradation. The framework formulates battery degradation prediction as a binary classification problem using electrochemical resistance characteristics and temporal features extracted from discharge-cycle data.

The objective is to identify whether the battery capacity will cross a predefined degradation threshold during the subsequent cycle, enabling early warning and supporting battery health monitoring.

## Methodology

The proposed framework consists of the following stages:

1. Battery discharge data selection and preprocessing.
2. Electrochemical and temporal feature engineering.
3. Next-cycle degradation target generation.
4. Leakage-aware data preparation.
5. Battery-wise validation.
6. Comparative machine-learning model development.
7. Performance evaluation and feature-importance analysis.

## Machine-Learning Models

The following classification algorithms are implemented and evaluated:

- Logistic Regression
- Random Forest
- XGBoost
- LightGBM

## Feature Engineering

The input representation incorporates temporal and electrochemical characteristics, including:

- Cycle number
- Log-transformed cycle number
- Ambient temperature
- Ohmic resistance (Re)
- Charge-transfer resistance (Rct)
- Resistance variations
- Resistance drift characteristics
- Rct/Re ratio

Future-cycle capacity is used exclusively for target-label generation and is not included as a predictive input.

## Prediction Target

The next-cycle degradation condition is formulated as a binary classification task based on a capacity threshold of 0.80:

- **Degraded:** Next-cycle capacity ≤ 0.80
- **Normal:** Next-cycle capacity > 0.80

## Validation Strategy

Battery-wise validation is employed to evaluate model generalization across battery groups. The validation framework includes a fixed battery-wise holdout and five-fold Stratified Group Cross-Validation, ensuring that observations belonging to the same battery are maintained within the same group.

## Evaluation Metrics

Models are assessed using:

- Accuracy
- Balanced Accuracy
- Precision
- Recall
- F1-score
- Matthews Correlation Coefficient (MCC)
- ROC-AUC
- PR-AUC

## Dataset

The experimental dataset contains measurements from 34 batteries and 7,368 observations. The discharge-data selection and subsequent feature-target alignment are described in the associated research manuscript.

Dataset access and usage should follow the conditions imposed by the original data provider.

## Requirements

The implementation uses Python and common machine-learning and data-analysis libraries, including NumPy, Pandas, Scikit-learn, XGBoost, LightGBM, and Matplotlib.

Refer to `requirements.txt` for the software dependencies.

## Reproducibility

The repository is intended to support transparent implementation, experimental reproducibility, and further research into next-cycle battery degradation prediction.

## Research Paper

**Title:** An Electrochemical-Temporal Machine Learning Framework for Early Prediction of Next-Cycle Battery Degradation

The code and experimental details are provided for research and academic purposes.

## Authors

Please refer to the associated research article for author information and affiliations.

## Citation

Citation information will be added following publication of the manuscript.

## License

The source code is provided under the license specified in the `LICENSE` file. Please review the license before using, modifying, or redistributing the code.
