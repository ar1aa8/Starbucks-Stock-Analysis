# Starbucks-Stock-Analysis
This project builds a small stock analysis product for beginner investors and business students who want to understand Starbucks’ stock performance using daily and monthly market data.
# Project Title
Starbucks Stock Performance Dashboard with DuPont Analysis
## 1. Problem & User
This project develops a Starbucks Stock Performance Dashboard to help beginner investors interested in consumer sector stocks and business school students understand the historical performance of Starbucks stock. The dashboard aims to present stock price trends, return patterns, trading volume changes, and key time periods in a simple and visually accessible way.In addition, the dashboard includes a DuPont analysis to help users understand Starbucks’ financial performance by decomposing return on equity (ROE) into profitability, asset efficiency, and financial leverage.

## 2. Data 
Data sources:
- Yahoo Finance, accessed through the Python package yfinance, for Starbucks stock price data.
- WRDS, for additional financial/market data.
Ticker symbol: SBUX
Access date: [2026-04-19]
Data frequency: Daily
Time period: [2018-01-01]
Key fields used
Date
Open
High
Low
Close
Adj Close
Volume
Derived variables
daily_return: percentage change in daily closing price
year_month: month identifier created from the date
monthly_price: closing price on the last trading day of each month
monthly_return: percentage change in monthly closing price
Additional financial statement fields used for DuPont analysis:
- Net Income
- Revenue
- Total Assets
- Shareholders’ Equity
## 3. Methods
The analysis was carried out in Python using a notebook-based workflow. The main steps are as follows:

Data collection

Historical Starbucks stock data was downloaded from WRDS and Yahoo Finance using yfinance.

Data cleaning and preparation

The date field was converted into datetime format.
The dataset was sorted chronologically.
Relevant columns were selected for analysis.
Missing values were checked and handled where necessary.
Daily stock performance analysis

Daily closing prices were plotted to show short-term and long-term price movement.
Daily returns were calculated using:
python
Copy
daily_return = Close.pct_change()
The highest and lowest daily returns were identified to highlight extreme movements.
Monthly stock performance analysis

Daily data was aggregated to monthly level by selecting the last available trading day in each month.
Monthly returns were calculated using percentage change in monthly closing prices.
Monthly price and return charts were created to improve trend interpretation.
Trading volume analysis

Daily trading volume was plotted to identify changes in market activity.
Periods of unusually high volume were compared with major price movements.
Visualisation

Line charts and return plots were created using Python libraries slike matplotlib.
Key time periods were highlighted to support interpretation of stock performance.
Interpretation

The dashboard uses simple descriptive statistics and visual indicators to help non-expert users understand Starbucks stock behaviour over time.

DuPont analysis  
To complement stock market analysis with accounting-based performance evaluation, a DuPont analysis was added. Return on equity (ROE) was decomposed into three components:

ROE = Profit Margin × Asset Turnover × Equity Multiplier

where:
- Profit Margin = Net Income / Revenue
- Asset Turnover = Revenue / Total Assets
- Equity Multiplier = Total Assets / Shareholders’ Equity

This method helps explain whether Starbucks’ shareholder returns were mainly driven by profitability, operating efficiency, or financial leverage. Annual financial statement data was used for this part of the analysis.
## 4. Key Findings
Starbucks stock shows clear periods of growth, decline, and recovery across the selected time period.
Daily returns are more volatile than monthly returns, which means monthly analysis provides a clearer picture of the overall trend.
Large price changes are often accompanied by increases in trading volume, suggesting higher market attention during these periods.
The most extreme positive and negative daily returns help identify dates when the stock experienced unusually strong market reactions.
Combining price, return, and volume charts provides a more complete understanding of stock performance than looking at price alone.
Key DuPont Analysis Insights
- ROE remained negative throughout 2020–2023, driven primarily by balance sheet structure rather than poor operations
- Profit margin improved steadily, showing strong underlying business profitability
- Asset turnover stayed stable, with no decline in operational efficiency
- Negative equity multiplier (negative shareholder equity) is the sole root cause of sustained negative ROE
## 5. How to run
To run this project locally, follow these steps:

Make sure Python is installed.
Install the required libraries:
bash
Copy
pip install pandas matplotlib seaborn yfinance
Open Jupyter Notebook:
bash
Copy
jupyter notebook
Run the notebook file step by step:
download the stock data
clean and prepare the dataset
calculate daily and monthly returns
generate charts and summary outputs
run the DuPont analysis section using annual financial statement data
Required files
Starbucks_Stock_Performance_Dashboard.ipynb
README.md
If the notebook uses a saved CSV file instead of direct online download, make sure the data file is stored in the same working directory.

## 6. Product link / Demo
Notebook file: sbux_analysis_project.ipynb
Repository / submission link: [please insert GitHub link or submission platform link]
Demo screenshots: [optional – insert image links or screenshot names if available]
## 7. Limitations & next steps
Limitations
This project focuses only on Starbucks, so it does not provide comparison with competitors or market benchmarks.
The dashboard mainly focuses on historical stock price, trading volume, and a limited set of accounting indicators. It does not yet incorporate broader macroeconomic variables, analyst expectations, or external news data.
The analysis is descriptive and does not attempt to predict future stock prices.
Yahoo Finance is a convenient public data source, but it may be less precise than professional financial databases.
Next steps
Compare Starbucks with other consumer sector firms, such as McDonald’s or Coca-Cola.
Add benchmark analysis against the S&P 500 index.
Include additional indicators such as moving averages, rolling volatility, or relative strength measures.
Mark major company events, such as earnings announcements, on the charts.
Develop the notebook into a more interactive dashboard using Streamlit or Plotly Dash.
Extend the financial analysis by including liquidity, profitability, and solvency ratios in addition to DuPont analysis
