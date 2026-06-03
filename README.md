# Marketing Mix Modeling for Campaign ROI Analysis

## Overview

This project analyzes how advertising spend across TV, radio, and newspaper channels relates to product sales. The goal is to build a baseline regression-based marketing mix analysis that estimates channel contribution, evaluates model performance, and supports data-driven campaign budget discussions.

This is an MMM-style regression project, not a full production-grade marketing mix model. It does not yet include adstock transformations, saturation curves, Bayesian estimation, seasonality, or experimental calibration.

## Business Problem

Marketing teams need to understand which advertising channels are most strongly associated with sales and whether campaign spend is being allocated efficiently. Without a structured measurement approach, budget decisions can rely too heavily on intuition instead of evidence.

This project uses advertising spend and sales data to estimate the relationship between media channels and sales, compare channel contribution, and provide a baseline framework for campaign ROI analysis.

## Dataset

**Dataset:** Advertising Dataset
**Records:** 200 observations
**Target Variable:** Sales
**Media Channels:** TV, Radio, Newspaper

The dataset contains advertising spend across three traditional media channels and corresponding product sales.

## Methodology

* Loaded and explored advertising spend and sales data
* Checked dataset structure, missing values, and summary statistics
* Winsorized extreme newspaper spend values at the 95th percentile
* Split the data into training, validation, and test sets
* Trained a multiple linear regression model using TV, radio, and newspaper spend
* Evaluated model performance using R-squared, MAE, and RMSE
* Interpreted model coefficients to compare relative channel contribution
* Visualized residuals, actual vs. predicted sales, and channel coefficient importance

## Model Performance

| Dataset    | R-squared |   MAE |  RMSE |
| ---------- | --------: | ----: | ----: |
| Training   |     0.908 |     — |     — |
| Validation |     0.894 | 1.293 | 1.750 |
| Test       |     0.816 | 1.544 | 1.932 |

The model explains a meaningful share of sales variation on the held-out test set, with a test R-squared of 0.816. Validation and test results show reasonable generalization, though the drop from validation to test performance suggests that further model refinement would be useful.

## Channel Coefficients

| Feature   | Coefficient |
| --------- | ----------: |
| TV        |      0.0449 |
| Radio     |      0.1984 |
| Newspaper |      0.0089 |

Radio has the largest coefficient in the fitted model, followed by TV and newspaper. Coefficients should be interpreted carefully because they reflect association in this dataset, not guaranteed causal impact.

## Key Findings

* TV and radio spend show stronger relationships with sales than newspaper spend.
* Radio has the largest estimated coefficient in the fitted regression model.
* Newspaper spend contributes weakly compared with TV and radio.
* The model provides a useful baseline for campaign ROI analysis, but it should not be treated as causal proof of channel incrementality.
* Further MMM improvements should include adstock, saturation, seasonality, and regularization.

## Business Impact

This project demonstrates how regression-based marketing analytics can support campaign budget discussions. By estimating channel contribution and model performance, marketing teams can identify stronger media signals, question weaker spend areas, and create a baseline for future budget reallocation analysis.

## Tech Stack

Python, Pandas, NumPy, Scikit-learn, Statsmodels, Matplotlib, Seaborn, Jupyter Notebook, Linear Regression

## Repository Structure

```text
marketing-mix-modeling-roi-analysis/
├── Marketing_MMM_for_Campaign_ROI_Optimization.ipynb
├── advertising.csv
├── README.md
```

## How to Run

```bash
git clone https://github.com/amit4009/marketing-mix-modeling-roi-analysis.git
cd marketing-mix-modeling-roi-analysis
jupyter notebook
```

Then open:

```text
Marketing_MMM_for_Campaign_ROI_Optimization.ipynb
```

## Limitations

* This is a regression-based MMM-style analysis, not a full modern MMM system.
* The dataset is small, with only 200 observations.
* The final model currently uses TV, radio, and newspaper spend only.
* Engineered lag, interaction, and nonlinear features are created in the notebook but are not included in the final fitted model.
* The model does not include adstock or carryover effects.
* The model does not include saturation or diminishing-return curves.
* The model does not include seasonality, pricing, promotions, competitor activity, or macroeconomic controls.
* The analysis is based on regression association and should not be treated as causal proof of channel incrementality.

## Future Improvements

* Train a second model using engineered lag, interaction, and nonlinear features
* Add Ridge and Lasso regression to reduce overfitting risk
* Add adstock transformations to model delayed media effects
* Add saturation curves to capture diminishing returns
* Add cross-validation for more stable performance estimates
* Add scenario-based budget reallocation simulation
* Add confidence intervals around channel contribution estimates
* Add digital channels such as paid search, social, display, and influencer marketing
* Build a dashboard for channel contribution and ROI scenario planning
