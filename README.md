# A/B Testing Statistical Analysis

## Project Overview

This project focuses on analyzing A/B testing results using Python and statistical methods to evaluate differences in conversion rates between control and test groups.

The analysis includes automated statistical significance calculations for multiple conversion metrics and an interactive Tableau dashboard to visualize experiment results.

## Project Results

- [View A/B Testing Results on Google Drive]([https://drive.google.com/file/d/1N0rCcgKf9Pp17WMNOKEGFSHG0zhxHEy9/view])
- [View on Tableau Public](https://public.tableau.com/app/profile/anastasiia.pavlenko/viz/Significance_17915712118370/Dashboard1?publish=yes)

## Tools & Technologies

- **SQL (Google BigQuery)** — data extraction and preparation
- **Python** — automated statistical analysis
- **Pandas & NumPy** — data processing and calculations
- **Statsmodels** — statistical hypothesis testing
- **Google Colab** — analysis environment
- **Tableau** — interactive data visualization

## Analysis Workflow

### 1. Data Extraction & Preparation

- Extracted A/B testing data from Google BigQuery using SQL.
- Combined session, event, account, order, and experiment data.
- Prepared data for calculating conversion metrics.
- Aggregated results by experiment, test group, and event type.

### 2. Conversion Metrics

Calculated four key conversion metrics:

- `add_payment_info / session`
- `add_shipping_info / session`
- `begin_checkout / session`
- `new_accounts / session`

Each metric represents the corresponding event count relative to the total number of sessions.

### 3. Statistical Significance Testing

Used a **two-proportion z-test** to compare conversion rates between control and test groups.

The Python script automatically:

- Iterates through experiments and conversion metrics.
- Calculates conversion rates for both groups.
- Calculates relative changes in conversion rates.
- Performs a two-sided z-test.
- Calculates p-values and identifies statistically significant differences using a **0.05 significance level**.

The calculations are automated using loops, allowing the same approach to be applied across multiple experiments and metrics.

### 4. Results Export

Created a structured CSV file containing:

- Experiment number and conversion metric
- Event and session counts for both groups
- Conversion rates for control and test groups
- Relative conversion rate change (%)
- Z-statistic and p-value
- Statistical significance indicator

The resulting dataset was exported for further analysis and visualization in Tableau.

### 5. Tableau Visualization

The Tableau dashboard is designed to visualize A/B testing results and compare conversion performance between experimental groups.

It includes:

- Conversion metrics for control and test groups
- Changes in conversion rates
- Statistical significance indicators
- Experiment-level filtering

## Key Analytical Approach

The analysis uses a **two-sided two-proportion z-test** to evaluate whether observed differences in conversion rates between experimental groups are statistically significant.

- **p-value < 0.05** — statistically significant difference
- **p-value ≥ 0.05** — no statistically significant difference detected

Statistical significance indicates whether the observed difference provides evidence against the null hypothesis, but does not necessarily imply practical business significance.

## Conclusion

This project demonstrates how SQL, Python, statistical hypothesis testing, and Tableau can be combined to automate A/B testing analysis.

The automated approach enables consistent evaluation of multiple conversion metrics across experiments, reducing manual calculations and supporting data-driven decision-making.
