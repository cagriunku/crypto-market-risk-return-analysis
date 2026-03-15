# crypto-market-risk-return-analysis
Exploratory data analysis of the cryptocurrency market using CoinGecko API, focusing on returns, volatility, and risk-adjusted performance.


Crypto Market Analysis (EDA)
Project Overview

This project explores the behavior of the cryptocurrency market using historical price data from the CoinGecko API.

The goal is to analyze the risk and return characteristics of the top cryptocurrencies and understand relationships between them through basic financial metrics.

The analysis includes:

Collecting historical price data for the top 50 cryptocurrencies

Calculating daily returns

Measuring volatility

Estimating a Sharpe-like risk/return ratio

Analyzing correlation between major coins

This project demonstrates a typical data analysis workflow using Python.

Data Source

Data is collected from the CoinGecko API using the pycoingecko library.

Information collected includes:

Cryptocurrency ID

Date

Price (USD)

Daily price movements

The dataset contains 365 days of historical price data for the top 50 cryptocurrencies by market capitalization.

Technologies Used

Python

Pandas

NumPy

PyCoinGecko API

Matplotlib

Data Pipeline

The analysis follows these steps:

1. Fetch Market Data

The script retrieves the top 50 cryptocurrencies by market cap from CoinGecko.

For each coin, historical price data for the last 365 days is downloaded.

2. Build the Dataset

All price data is combined into a single dataframe with the following structure:

Column	Description
coin_id	Cryptocurrency identifier
date	Observation date
price	Price in USD

The dataset is saved as:

crypto_top50_365d.csv
crypto_top50_365d.parquet
Feature Engineering

Several financial metrics are calculated:

Daily Return

Daily return is calculated using:

return_1d = pct_change(price)

This measures the percentage change in price from one day to the next.

Volatility

Volatility is calculated as the standard deviation of daily returns for each cryptocurrency.

Higher volatility indicates higher risk.

Average Return

The mean of daily returns is used to estimate the average expected return.

Sharpe-Like Ratio

A simplified Sharpe-style metric is calculated:

sharpe_like = avg_return / volatility

Since no risk-free rate is used, this is referred to as a Sharpe-like ratio.

This metric helps identify cryptocurrencies with better return relative to their risk.

Correlation Analysis

A correlation matrix is computed for the top 10 cryptocurrencies.

This helps identify how closely different coins move together.

High correlation suggests that assets behave similarly during market movements.

Outputs

The project produces the following outputs:

Dataset files:

crypto_top50_365d.csv
crypto_top50_365d.parquet

Risk-Return summary:

crypto_risk_return_summary.csv

The summary dataset includes:

Column	Description
coin	Cryptocurrency name
avg_return	Average daily return
vol	Volatility (standard deviation of returns)
sharpe_like	Risk-adjusted return metric
Example Insights

The analysis allows us to:

Identify cryptocurrencies with higher risk-adjusted returns

Compare volatility across different assets

Explore correlations between major cryptocurrencies

Understand general market behavior

How to Run the Project
Install dependencies
pip install pycoingecko pandas numpy matplotlib
Run the notebook

Open the notebook and execute all cells:

crypto_eda.ipynb

This will:

Download cryptocurrency data

Calculate financial metrics

Export the results

Author

Çağrı 

Data Scientist working with:

Python

Data Analysis

Machine Learning

Data Pipelines

SQL
