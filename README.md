# Multi-Output Neural Network: Predicting Department and Attrition

## Overview

This project utilizes a multi-output neural network to predict two employee-related outcomes based on HR data:

- **Department** (multiclass classification)
- **Attrition** (binary classification)

Using TensorFlow and Keras, the model is designed with a shared input layer and separate output branches for each prediction task.

---

## Data

The dataset was sourced from [BC EdX's Attrition Dataset](https://static.bc-edx.com/ai/ail-v-1-0/m19/lms/datasets/attrition.csv) and includes various employee-related features.

- **Target variables:**
  - `Department`: Multiclass output
  - `Attrition`: Binary output

- **Features:**
  - At least 10 features were selected, preprocessed, and scaled using `StandardScaler`.
  - Categorical outputs (`Department`, `Attrition`) were encoded using `OneHotEncoder`.

---

## Model Architecture

- **Input Layer**: Based on the number of features in the training dataset.
- **Shared Hidden Layers**: Two dense layers used to extract general features from input data.
- **Department Branch**:
  - One hidden layer
  - Output layer with softmax activation (for multiclass classification)
- **Attrition Branch**:
  - One hidden layer
  - Output layer with sigmoid activation (for binary classification)

---

## Compilation & Training

- **Loss Functions**:
  - Categorical crossentropy for department
  - Binary crossentropy for attrition
- **Optimizer**: Adam
- **Metrics**: Accuracy for both outputs
- **Training**: Model trained using `.fit()` with training and testing datasets for each output

---

## Results

**Test Accuracy**:
- Department: `0.8288`
- Attrition: `0.5679`

---

## Considerations

- Accuracy may not be the most informative metric for attrition if class imbalance exists.
- The model could be improved through additional feature engineering, hyperparameter tuning, or alternative model architectures.
- The use of appropriate activation functions ensures correct interpretation of model outputs:
  - Softmax for multiclass classification
  - Sigmoid for binary classification

---


## Dax Kelson
