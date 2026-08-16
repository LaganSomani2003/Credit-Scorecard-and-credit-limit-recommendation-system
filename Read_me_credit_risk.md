# Credit Risk Scoring & Credit Limit Recommendation System

## Overview

An end-to-end credit risk analytics project built on the Home Credit
dataset to predict loan default risk and translate model outputs into
actionable credit decisions. The project combines WOE/IV-based scorecard
development, Logistic Regression, risk segmentation, model evaluation,
and a rules-based credit limit recommendation engine.

## Business Use Case

Financial institutions need to identify borrowers with higher default
risk while maintaining explainable and consistent lending decisions.
This project develops a scorecard to estimate default risk, segments
customers into risk bands, and recommends credit limits using
risk-adjusted income multipliers and PD thresholds.

## Key Results

-   Built a credit risk scorecard on **307,511 loan applicants** with an
    **8.07% default rate**.
-   Achieved **0.75 ROC-AUC** using the final Logistic Regression
    scorecard.
-   Created **4 risk bands** with actual default rates ranging from
    **1.27% to 25.25%**, demonstrating an approximately **20x risk
    spread**.
-   Developed and validated a credit-limit recommendation engine across
    a **100-customer sample**, producing differentiated increase,
    decrease, and unchanged recommendations by risk band.

## Methodology

1.  Data preprocessing and feature engineering
2.  Missing-value and categorical-variable treatment
3.  WOE/IV binning for scorecard development
4.  Logistic Regression-based probability of default estimation
5.  PDO-scaled credit score construction
6.  Feature selection using statistical significance and VIF checks
7.  Model evaluation using ROC-AUC, KS and Gini
8.  Risk-band creation and validation against observed default rates
9.  Comparison with Random Forest and XGBoost
10. Rules-based credit limit recommendation using risk, PD, income and
    current credit exposure

## Model Comparison

  Model                   ROC-AUC   Precision   Recall       F1
  --------------------- --------- ----------- -------- --------
  Logistic Regression      0.7479      0.5769   0.0091   0.0178
  Random Forest            0.7454      0.1654   0.6447   0.2632
  XGBoost                  0.7537      0.6625   0.0107   0.0210

The Logistic Regression scorecard was retained as the primary scorecard
because of its interpretability and suitability for credit-risk
decisioning, while Random Forest and XGBoost were used for model
benchmarking.

## Risk Segmentation

The model assigns customers to four risk bands:

-   **Very Low Risk**
-   **Low Risk**
-   **Medium Risk**
-   **High Risk**

Observed default rates provide empirical validation that the risk bands
meaningfully differentiate borrower risk.

## Credit Limit Recommendation Engine

The Phase 2 decision engine applies risk-specific income multipliers and
risk restrictions to generate:

-   Recommended credit limit
-   Approve / Manual Review / Reject-Low Limit decision
-   Increase, decrease or unchanged limit classification
-   Explanatory reasons for the recommendation

High-risk customers are restricted from receiving credit-limit
increases, while lower-risk customers can retain or increase existing
limits subject to the policy rules.

## Technologies

-   Python
-   Pandas
-   NumPy
-   Scikit-learn
-   Statsmodels
-   ScorecardPy
-   Matplotlib
-   Jupyter Notebook

## Evaluation Metrics

-   ROC-AUC
-   KS Statistic
-   Gini Coefficient
-   Precision
-   Recall
-   F1 Score
-   Confusion Matrix
-   Risk-band default-rate validation

## Project Structure

``` text
Credit-Risk-Scoring/
│
├── Credit Scorecard Development and Credit Limit Recommendation System.ipynb
├── README.md
└── data/
    └── (Home Credit dataset - not included)
```

## Note

The dataset is not included in this repository. The project is intended
for educational and portfolio purposes and demonstrates an end-to-end
approach to interpretable credit-risk modeling and decision automation.
