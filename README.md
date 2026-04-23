# Starbucks-Stock-Analysis
This project builds a small stock analysis product for beginner investors and business students who want to understand Starbucks’ stock performance using daily and monthly market data.
# Project Title
Starbucks Stock Performance Dashboard with DuPont Analysis
## 1. Problem & User
This project analyses the historical stock performance of Starbucks to help beginner investors and business students better understand how a company’s share price behaviour can be examined using Python. The analysis focuses on stock price trends, return patterns, trading volume, volatility, comparison with a market proxy, and DuPont analysis.

The main aim is to provide a clear and accessible view of how Starbucks performed over time, what risk patterns can be observed from daily and monthly returns, and how accounting-based financial ratios can help explain shareholder returns.

Target users:
- Beginner investors interested in understanding stock behaviour
- Business and finance students learning financial data analysis
- Users who want a simple example of Python-based stock analysis

## 2. Data 
Data sources:
- Yahoo Finance, accessed through the Python package yfinance, for Starbucks stock price data.
- WRDS, for additional financial/market data.
Ticker symbol: SBUX
Access date: [2026-04-19]
Data frequency: Daily
Key fields used
Date
Open
High
Low
Close
Adj Close
Volume
Derived variables
sbux_daily.csv– Starbucks daily stock data
sbux_monthly.csv – Starbucks monthly stock data
sbux_security.csv – Starbucks security identifier and company information
sp500_financials_price_data.csv` – price dataset used to construct an S&P 500 market proxy
Additional financial statement fields used for DuPont analysis:
- Net Income
- Revenue
- Total Assets
- Shareholders’ Equity
## 3. Methods
The analysis was carried out in Python using pandas, matplotlib, and seaborn. The workflow includes data cleaning, return calculation, descriptive analysis, visualisation, market comparison, and DuPont decomposition.

### 3.1 Data cleaning and preparation
The daily, monthly, and security datasets were loaded from CSV files. The main preparation steps included:
- converting date columns to datetime format
- sorting data by date
- removing missing values in key fields
- removing duplicate rows
- converting numerical columns into proper numeric format
- standardising column names where necessary

The security dataset was also cleaned and merged with the stock datasets using `gvkey` and `iid`.

### 3.2 Daily stock analysis
Daily closing prices were analysed to identify the long-term movement of Starbucks stock. Daily returns were calculated using percentage change in the closing price.

Main tasks:
- plot daily stock price
- calculate `daily_return`
- identify highest and lowest daily returns
- inspect extreme daily return values
- plot distribution of daily returns
- calculate rolling volatility using a moving standard deviation
- summarise average return, volatility, and trading volume by year

### 3.3 Monthly stock analysis
Monthly stock data was analysed separately to provide a clearer long-term perspective. Monthly closing price, trading volume, return, and cumulative return were examined.

Main tasks:
- plot monthly closing price
- plot monthly trading volume
- analyse monthly return distribution
- calculate cumulative monthly return
- summarise yearly average return, volatility, and trading volume
- calculate monthly price range percentage using high and low prices

### 3.4 Market comparison
To compare Starbucks with the broader market, a simple market proxy was constructed from the S&P 500 price dataset. The first column was converted to a date field, price columns were identified, and their cross-sectional average was used to form a market proxy series. This proxy was then normalised to a base value of 100.

Starbucks daily and monthly prices were also normalised to 100 and compared with the market proxy through line charts and descriptive statistics.

### 3.5 DuPont analysis
To complement the stock market analysis, a DuPont analysis was used to break down return on equity (ROE) into three components:

**ROE = Profit Margin × Asset Turnover × Equity Multiplier**

where:
- **Profit Margin = Net Income / Revenue**
- **Asset Turnover = Revenue / Total Assets**
- **Equity Multiplier = Total Assets / Equity**

This helps show whether Starbucks’ ROE was mainly influenced by profitability, operating efficiency, or capital structure.
## 4. Key Findings
The analysis produced several main findings:

- Starbucks’ stock price showed clear periods of growth, decline, and recovery over time.
- Daily returns were much more volatile than monthly returns, so monthly data gave a clearer picture of the broader trend.
- Extreme positive and negative daily returns highlighted dates with unusually strong market reactions.
- Periods of higher volatility often coincided with larger changes in trading volume.
- The comparison with the market proxy showed that Starbucks did not always move in line with the broader market, suggesting the presence of firm-specific influences.
- The monthly cumulative return chart showed the long-term change in shareholder value more clearly than daily price movements alone.

### DuPont analysis findings
- ROE remained negative during 2020–2023.
- This negative ROE was not mainly caused by weak profitability.
- Profit margin improved over time, suggesting that operating performance remained relatively strong.
- Asset turnover stayed fairly stable, indicating no major deterioration in efficiency.
- The main reason for negative ROE was negative equity, which caused the equity multiplier to become negative.

These results show that ROE should not always be interpreted on its own, especially when a company has an unusual balance sheet structure.
## 5. How to run
To run this project locally, follow these steps:

Make sure Python is installed.
Install the required Python libraries:
```bash
pip install pandas matplotlib seaborn
Files needed
Make sure the following files are available in the project folder or update the file paths in the code:

sbux_daily.csv
sbux_monthly.csv
sbux_security.csv
sp500_financials_price_data.csv
Run steps
Open the Python notebook or script.
Load the CSV files.
Run the daily stock analysis section.
Run the monthly stock analysis section.
Run the security data cleaning and merge section.
Run the S&P 500 proxy construction and comparison section.
Run the DuPont analysis section.
README.md
If the notebook uses a saved CSV file instead of direct online download, make sure the data file is stored in the same working directory.


## 6. Product link / Demo
Notebook file: sbux_analysis_project.ipynb
Repository / submission link: [please insert GitHub link or submission platform link]
Demo screenshots: [optional – insert image links or screenshot names if available]
## 7. Limitations & next steps
Limitations
The market benchmark is a simple proxy constructed from available S&P 500 constituent price columns, so it is not identical to the official index.
Some annual financial statement values for the DuPont analysis were entered manually, so there is a risk of input error.
The project focuses on a single company and does not compare Starbucks with direct competitors.
The analysis is descriptive rather than predictive.
No regression analysis or formal statistical testing was included.
Next steps
Compare Starbucks with similar firms such as McDonald’s or Coca-Cola.
Use an official market index series instead of a manually constructed proxy.
Include additional indicators such as moving averages, drawdown, or annualised volatility.
Add major corporate events to the timeline for deeper interpretation.
Develop the project into an interactive dashboard using Streamlit or Plotly Dash
