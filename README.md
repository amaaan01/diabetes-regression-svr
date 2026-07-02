# Diabetes Regression using Support Vector Regression (SVR)

## Project Overview

This project uses Support Vector Regression (SVR) to predict disease progression in diabetes patients based on clinical measurements. Multiple SVR kernels and hyperparameter combinations were evaluated to identify the best-performing model.

The project also compares the performance of SVR and LinearSVR using the R² score.

---

## Dataset

The project uses the Diabetes dataset available in Scikit-Learn.

### Dataset Information

- 442 samples
- 10 numerical features
- Continuous target variable
- Regression problem

Dataset loaded using:

```python
from sklearn.datasets import load_diabetes
```

---

## Objective

Build a regression model capable of predicting diabetes disease progression based on patient characteristics and evaluate its performance using the R² metric.

---

## Project Workflow

### 1. Data Loading

- Load Diabetes dataset from Scikit-Learn
- Convert data into Pandas DataFrame

### 2. Train-Test Split

```python
train_test_split(
    X,
    y,
    test_size=0.2,
    random_state=42
)
```

- 80% Training Data
- 20% Testing Data

### 3. Target Scaling

The target variable was standardized using StandardScaler.

```python
StandardScaler()
```

### 4. Model Training

Support Vector Regression (SVR) models were trained using different kernels:

- Linear Kernel
- RBF Kernel
- Polynomial Kernel

### 5. Hyperparameter Tuning

GridSearchCV was used to identify the best model parameters.

Parameters explored:

```python
C = [1, 2, 5, 10, 50, 100]
kernel = ["rbf", "linear"]
epsilon = [0.01, 0.1, 0.2, 0.3, 0.5]
```

Cross-validation:

```python
cv = 5
```

Evaluation Metric:

```python
R² Score
```

### 6. Model Comparison

The optimized SVR model was compared against:

```python
LinearSVR
```

to evaluate performance differences.

---

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-Learn
- Jupyter Notebook

---

## Models Evaluated

| Model | Description |
|---------|------------|
| SVR (Linear Kernel) | Linear Support Vector Regression |
| SVR (RBF Kernel) | Non-linear Support Vector Regression |
| SVR (Polynomial Kernel) | Polynomial Regression Boundary |
| GridSearchCV Optimized SVR | Hyperparameter Tuned Model |
| LinearSVR | Fast Linear Support Vector Regression |

---

## Evaluation Metric

The model was evaluated using:

### R² Score

R² measures how well the model explains the variance in the target variable.

```text
R² = 1.0  → Perfect Prediction
R² = 0.0  → Predicting Mean
R² < 0.0 → Worse than Predicting Mean
```

---

## Repository Structure

```text
diabetes-regression-svr/
│
├── .gitignore
├── README.md
├── requirements.txt
└── diabetes_regression_svr.ipynb
```

---

## Results

| Metric | Value |
|----------|----------|
| Train R² | 0.5148886128277125 |
| Test R² | 0.47346104043236503 |

Replace the values above with your actual results.

---

## Key Learnings

- Support Vector Regression (SVR)
- Target Variable Scaling
- Hyperparameter Tuning using GridSearchCV
- Cross Validation
- Regression Model Evaluation using R² Score
- Comparison between SVR and LinearSVR

---

## Future Improvements

- Pipeline Implementation
- Feature Engineering
- Random Forest Regressor
- Gradient Boosting Regressor
- XGBoost Regressor
- Automated Hyperparameter Optimization

---

## Author

Amaan Shaikh
