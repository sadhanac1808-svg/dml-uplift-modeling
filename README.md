# dml-uplift-modeling
Advanced Causal Inference with Double Machine Learning
# Advanced Causal Inference with Double Machine Learning (DML) for Uplift Modeling

This project implements the Double Machine Learning (DML) framework to estimate
Conditional Average Treatment Effects (CATE), also known as uplift modeling.
The goal is to accurately estimate heterogeneous treatment effects in the
presence of confounding variables.

This approach is widely used in:
- Targeted marketing
- Policy evaluation
- Personalized decision systems

---

## Project Objectives

- Generate a synthetic dataset with strong confounding
- Implement Double Machine Learning with cross-fitting
- Estimate individual-level uplift (CATE)
- Compare DML results with a baseline regression model
- Analyze heterogeneous treatment effects across feature space

---

## Dataset Description

- Synthetic, programmatically generated dataset
- 5,000 samples
- 10 covariates (X0–X9)
- Binary treatment variable (T)
- Continuous outcome variable (Y)
- Treatment assignment depends on covariates (confounding present)

---

## Methodology

### Double Machine Learning (DML)

The DML framework consists of three stages:

1. **Outcome Model**
   Estimate E[Y | X] using a regularized regression model (Lasso).

2. **Treatment Model (Propensity Score)**
   Estimate E[T | X] using a Random Forest Classifier.

3. **Orthogonalization and CATE Estimation**
   - Residualize outcome and treatment
   - Train a final model on residuals to estimate CATE

Cross-fitting with K-Fold cross-validation is used to ensure robustness
and to reduce overfitting and bias.

---

## Models Used

| Component | Model |
|---------|------|
| Outcome Model | Lasso Regression (with Cross-Validation) |
| Treatment Model | Random Forest Classifier |
| CATE Model | Random Forest Regressor |
| Baseline Model | Linear Regression with Interaction Terms |

---

## Evaluation Metrics

- Precision in Estimation of Heterogeneous Effects (PEHE)
- Comparison between DML and baseline regression
- Segment-wise uplift analysis

---

## Key Findings

- DML significantly reduces bias caused by confounding
- Baseline regression overestimates treatment effects
- DML accurately identifies both high and low responder groups
- Covariates X0 and X1 play a major role in treatment heterogeneity

---

## Project Structure
