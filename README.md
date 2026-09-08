# auto-insurance-claim-propensity-glm

Actuarial GLM project for auto insurance claim propensity, model validation, O/E analysis, and risk segmentation.

## Overview

This project develops an interpretable binomial GLM to estimate auto insurance claim propensity using policyholder, vehicle, and geographic characteristics.

- 58,592 policies
- Observed claim rate: 6.4%
- Final model: Model 2
- Holdout ROC-AUC: 0.5765
- Overall O/E: 0.9997

The model is intended for risk segmentation, underwriting support, and portfolio monitoring rather than standalone pricing.

## Modeling Approach

The analysis includes:

- Exploratory claim-rate analysis
- Confidence intervals and low-volume review
- Customer-age spline modeling
- GLM model selection using AIC and likelihood-ratio tests
- Holdout validation
- Calibration and O/E analysis
- Adjusted odds-ratio interpretation
- Exposure sensitivity testing
- Class-weighting and oversampling challengers

## Key Results

Model 2 includes:
- Customer age
- Vehicle age
- Fuel type
- Region

Adding geography significantly improved model fit, while vehicle segment and safety features provided little additional value.

### Holdout Performance

| Metric | Model 2 |
|---|---:|
| ROC-AUC | 0.5765 |
| PR-AUC | 0.0853 |
| Log Loss | 0.2356 |
| Brier Score | 0.0596 |
| Predicted Claim Rate | 6.40% |
| Actual Claim Rate | 6.40% |

## Risk Segmentation

The observed claim rate increased from approximately:
- 3.9% in the lowest-risk decile
- 9.1% in the highest-risk decile

The model therefore provides useful broad risk separation despite modest individual-level discrimination.

## Business Interpretation

The model can support:
- Underwriting review
- Risk segmentation
- Portfolio monitoring
- O/E analysis

It should not be used as a complete pricing model because claim severity and reliable earned exposure are unavailable.

## Limitations

- Models claim occurrence, not claim severity
- Exposure information is limited
- Some segments have low volume
- ROC-AUC is modest
- Validation is random rather than out-of-time
