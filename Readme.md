# Washington Housing Value Analysis (2015–2024)

**Seattle University | DATA 5100 - Foundations of Data Science**

**Team Members:** Binay Raut and Quynh Giang Tran

## Project Overview

This project investigates home values across Washington State's 39 counties from 2015 through 2024. We investigate how home values are associated with median household income, unemployment rates, mortgage interest rates, and geographic location.

We also explore housing market differences across the six Washington State Department of Transportation (WSDOT) regions: Northwest, North Central, Olympic, Southwest, South Central, and Eastern.

Our goal is to identify statistical relationships between economic indicators and home values and evaluate whether regional classification provides additional explanatory value.

## Research Questions

1. Median Household Income: Is median household income significantly associated with home values in Washington State?
2. Unemployment Rate: Is the unemployment rate significantly associated with home values in Washington State?
3. Multiple Regression: Which economic predictors—median household income, unemployment rate, and mortgage interest rate—have statistically significant associations with home values after adjusting for the other predictors?
4. Regional Classification: Does including WSDOT regional classification improve the explanatory performance of a regression model beyond median household income, unemployment rates, and mortgage interest rates?

## Data

Our analysis uses publicly available data from the following sources:

| Dataset | Source | Description |
|---|---|---|
| Home Values | [Zillow Research](https://www.zillow.com/research/data/) | Zillow Home Value Index (ZHVI) |
| Median Household Income | [U.S. Census Bureau – ACS](https://data.census.gov/) | Median household income |
| Unemployment Rate | [Bureau of Labor Statistics – LAUS](https://www.bls.gov/lau/) | Unemployment rates |
| Mortgage Interest Rate | [Federal Reserve Economic Data – FRED](https://fred.stlouisfed.org/series/MORTGAGE30US) | 30-year fixed mortgage interest rates |
| Regional Classification | [Washington State Department of Transportation](https://wsdot.wa.gov/about/contacts/offices-regions) | Classification WSDOT regions |

### Data Preparation

The data sources have different reporting frequencies. Monthly ZHVI and weekly mortgage interest rates are aggregated to annual averages to create a consistent county-year dataset.

County-level records are merged using five-digit county FIPS codes and year. The final dataset contains:

- 39 Washington counties
- 10 years (2015–2024)
- 390 county-year observations
- 8 variables

The final dataset is available at [`data/housing_final.csv`](data/housing_final.csv).

One annual ZHVI value is missing for Columbia County in 2015. This observation is retained as missing rather than imputed.

## Repository Structure

- `code/` — Jupyter notebooks for data preparation and exploratory analysis
- `data/` — Original, cleaned, and merged datasets
- `reports/` — Project documentation and reports
- `requirements.txt` — Python dependencies

### Main Notebooks

- [`01_data_preparation.ipynb`](code/01_data_preparation.ipynb) — Data cleaning, integration, and preparation
- [`02_exploratory_data_analysis.ipynb`](code/02_exploratory_data_analysis.ipynb) — Housing value exploratory analysis
- [`EDA_unemployment rate.ipynb`](code/EDA_unemployment%20rate.ipynb) — Unemployment rate exploratory analysis (to be considolated)
- [`EDA_interest rate.ipynb`](code/EDA_interest%20rate.ipynb) — Mortgage interest rate exploratory analysis (to be considolated)

## Analytical Approach

We use Python, pandas, NumPy, Matplotlib, and Seaborn to prepare, summarize, and visualize the data.

Our statistical analysis begins with simple linear regression examining the individual associations of median household income and unemployment rates with housing values. We will then develop multiple regression models incorporating additional economic predictors and WSDOT regional classification.

We plan to compare regression models using R², adjusted R², RMSE, and residual diagnostics.

## Project Status

Data collection, cleaning, integration, and initial exploratory data analysis have been completed or started. An initial income-based linear regression has also been fitted.

Additional regression comparisons, regional statistical analysis, model diagnostics, and final reporting are in progress.