# GARCH Volatility Modeling

## Overview

This project analyzes volatility clustering and persistence across four major global equity indices using GARCH(1,1) models. Historical market data are used to examine how volatility evolves over time and how effectively different GARCH specifications capture the dynamics of equity returns.

The analysis covers:

- S&P 500
- EURO STOXX 50
- Nikkei 225
- FTSE 100

## Data

Daily historical adjusted closing prices are obtained from Yahoo Finance beginning in January 2010. Prices are cleaned and transformed into percentage log returns for volatility modeling.

## Methodology

The project follows the following workflow:

1. Download and clean historical price data using `yfinance`
2. Calculate daily log returns and summary statistics
3. Explore return distributions, volatility clustering, and 21-day rolling volatility
4. Estimate GARCH(1,1) models using both Normal and Student-t error distributions
5. Compare model specifications using AIC and BIC
6. Measure volatility persistence using the estimated alpha + beta parameters
7. Perform Ljung-Box residual diagnostics to evaluate model adequacy
8. Compare conditional volatility dynamics across global equity markets

## Key Findings

- GARCH(1,1) models capture the volatility clustering observed across all four equity indices.
- Student-t specifications consistently outperform Normal specifications based on information criteria, supporting the presence of heavy-tailed return distributions.
- The S&P 500 exhibits the highest volatility persistence, with alpha + beta close to one, indicating that volatility shocks decay slowly.
- All four markets experience substantial volatility spikes during periods of financial stress, particularly during the COVID-19 crisis.
- Residual diagnostics suggest that the fitted models capture most serial dependence, although some remaining volatility dynamics are present for the Nikkei 225.

## Tools & Libraries

- Python
- pandas
- NumPy
- Matplotlib
- yfinance
- arch
- statsmodels

## Repository Contents

- `GARCH project.ipynb` — Complete data analysis, model estimation, diagnostics, and visualization
- `summary_statistics.csv` — Summary statistics for index returns
- `garch_aic_bic_comparison.csv` — Model comparison using AIC and BIC
- `garch_parameters.csv` — Estimated GARCH parameters and volatility persistence
- `garch_diagnostics.csv` — Residual diagnostic test results

## Conclusion

The analysis demonstrates that volatility in major global equity markets is highly persistent and clustered over time. The superior performance of Student-t GARCH specifications highlights the importance of accounting for heavy-tailed return distributions when modeling financial market volatility.
