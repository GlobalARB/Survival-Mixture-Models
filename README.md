# Survival Mixture Models for Government Processing Times

2-segment Exponential-Weibull mixture for NYC license processing times with right-censoring, covariate-dependent mixing, hazard analysis, Bayesian updating from approval timing, and multinomial logit outcome prediction.

## Methods

- **Exponential-Weibull mixture:** Custom MLE via `GenericLikelihoodModel` with interval-censored likelihoods
- **Right-censoring:** Applications pending >50 days treated as censored observations
- **Covariate-dependent mixing:** Logistic model for segment probability based on license type, application type, category
- **Bayesian updating:** Posterior segment probability given observed approval day
- **Multinomial logit:** Predicts Issued / Denied / Withdrawn outcomes

## Sections

| # | Section | Description |
|---|---------|-------------|
| 1 | Setup & Data | NYC OpenData license applications (9,887 records) |
| 2 | Mixture Model | ExpoWeibull class, 7-parameter MLE estimation |
| 3 | Hazard Functions | Interval-censored probabilities, hazard rate comparison |
| 4 | Covariate Effects | Segment probability by application profile |
| 5 | Bayesian Updating | Prior → posterior from approval timing |
| 6 | Outcome Prediction | Multinomial logit for application status |
| 7 | Summary | Architecture overview, key findings |

## Data

**NYC OpenData — License Applications:** [Download here](https://data.cityofnewyork.us/Business/License-Applications/ptev-4hud/about_data). Save as `Archived_License_Applications.csv` in repo root.

## Setup

```bash
pip install -r requirements.txt
```

Runs on CPU.

## License

MIT
