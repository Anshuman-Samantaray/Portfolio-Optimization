# Portfolio Optimization with Python

This repository contains Python code for portfolio optimization using financial data. The code utilizes pandas, numpy, seaborn, matplotlib, and scipy libraries to process and analyze stock data, optimize portfolio weights, and calculate metrics such as expected return, risk (standard deviation), and Sharpe ratio.

## Getting Started

### Prerequisites

Make sure you have Python 3.x installed along with the following libraries:

- pandas
- numpy
- seaborn
- matplotlib
- scipy
- fredapi (for fetching risk-free rates)

You can install these libraries using pip:

```bash
pip install pandas numpy seaborn matplotlib scipy fredapi
```


# Description

## 1. Data Preparation (`portfolio_optimization.py`)

- **Importing Libraries**: Imports necessary libraries and sets up initial capital.
- **Creating Dataset**: Loads stock data from `archive.zip` based on predefined stock symbols.
- **Handling Missing Values**: Fills missing values in numeric columns using a rolling window median.
- **Pivoting Dataframe**: Converts the dataset into a pivot table of adjusted close prices for correlation analysis.
- **Calculating Log Normal Returns**: Calculates log normal returns for statistical normalization.
- **Covariance Matrix**: Computes the covariance matrix of log returns for risk assessment.

## 2. Optimization Functions

- **Standard Deviation**: Calculates the standard deviation of portfolio returns.
- **Expected Return**: Computes the expected return of the portfolio.
- **Sharpe Ratio**: Calculates the Sharpe ratio, adjusting for risk-free rate.
- **Negative Sharpe Ratio**: Prepares the negative of the Sharpe ratio for optimization.

## 3. Optimization Process

- **Calculating Risk-Free Rate**: Fetches the latest 10-year Treasury rate from FRED API.
- **Defining Constraints and Bounds**: Sets up optimization constraints (total weight equals 1) and bounds (individual stock weights between 0 and 0.5).
- **Optimize Weights to Maximize Sharpe Ratio**: Uses `scipy.optimize.minimize` to find optimal portfolio weights that maximize the Sharpe ratio.

## 4. Output

- **Portfolio Composition**: Displays the final portfolio composition, including investments, counts of shares to buy, and latest prices.
- **Metrics**: Prints portfolio metrics such as return, risk (standard deviation), and Sharpe ratio.
