# Financial Data Extraction and Visualization from SEC EDGAR Filings

This project involves extracting financial data from the SEC's EDGAR database for S&P 500 companies, processing the data, and visualizing key financial metrics alongside stock prices using Python. The aim is to perform in-depth financial analysis by combining market data, insider trading activities, and fundamental financial indicators.

## Table of Contents

- [Overview](#overview)
- [Data Sources](#data-sources)
- [Prerequisites](#prerequisites)
- [Project Structure](#project-structure)
- [Data Extraction](#data-extraction)
  - [Fetching S&P 500 Company List](#fetching-sp-500-company-list)
  - [Retrieving CIK Numbers](#retrieving-cik-numbers)
  - [Downloading Financial Concepts](#downloading-financial-concepts)
    - [Concepts Included](#concepts-included)
    - [Handling Alternative Concepts](#handling-alternative-concepts)
    - [Corner Cases and Data Variability](#corner-cases-and-data-variability)
- [Data Processing](#data-processing)
  - [Adjusting for Stock Splits](#adjusting-for-stock-splits)
  - [Calculating Trailing Twelve Months (TTM) EPS](#calculating-trailing-twelve-months-ttm-eps)
  - [Normalizing Data](#normalizing-data)
- [Visualization](#visualization)
  - [Plotting Stock Prices and TTM EPS](#plotting-stock-prices-and-ttm-eps)
  - [Adding Insider Trading Activities](#adding-insider-trading-activities)
  - [Incorporating Additional Financial Metrics](#incorporating-additional-financial-metrics)
- [Compliance with SEC Guidelines](#compliance-with-sec-guidelines)
- [Usage Instructions](#usage-instructions)

---

## Overview

This project automates the process of collecting, processing, and visualizing financial data from SEC filings. By extracting data such as earnings per share, cash flows, dividends, and share buybacks, and combining it with market data and insider trading activities, we can gain valuable insights into companies' financial health and performance over time.

---

## Data Sources

- **SEC EDGAR Database**: Official filings from publicly traded companies.
- **Wikipedia**: For the list of S&P 500 companies.
- **Market Data CSV Files**: Historical stock prices and volumes.

---

## Prerequisites

- **Python 3.x**
- Libraries:
  - `pandas`
  - `requests`
  - `numpy`
  - `plotly`
  - `beautifulsoup4` (if parsing HTML content)

---

## Project Structure

- **/**: Jupyter notebooks for data processing and visualization.
- **data/**
  - `sp500_companies.csv`: List of S&P 500 companies with tickers and CIKs.
  - `market_data/`: Folder containing market data CSV files for each ticker.
- **fundamentals/**
  - Financial data CSV files for each company.
- **sec_cache/** and **sec_data/**: Cache directories for downloaded SEC data.
- **scripts/**: Python scripts for data extraction and processing.

---

## Data Extraction

### Fetching S&P 500 Company List

We start by scraping the list of S&P 500 companies from Wikipedia and saving it to `sp500_companies.csv`.

```python
import pandas as pd

# Read S&P 500 components
url = 'https://en.wikipedia.org/wiki/List_of_S%26P_500_companies'
tables = pd.read_html(url)
df = tables[0]

# Rename columns for consistency
df = df.rename(columns={
    'Symbol': 'Ticker',
    'Security': 'Company',
    'GICS Sector': 'Sector',
    'GICS Sub-Industry': 'Sub-Industry',
    'Headquarters Location': 'Headquarters',
    'Date added': 'Date_Added',
    'Founded': 'Founded_Year'
})

# Save to CSV
df.to_csv('data/sp500_companies.csv', index=False)
print("CSV file 'sp500_companies.csv' has been created.")
```

### Retrieving CIK Numbers

The Central Index Key (CIK) uniquely identifies companies in the SEC's EDGAR system. We retrieve the CIK for each ticker.

```python
import requests

def get_ticker_cik_mapping():
    url = "https://www.sec.gov/include/ticker.txt"
    headers = {'User-Agent': 'Your Name yourname@example.com'}  # Replace with your actual information
    response = requests.get(url, headers=headers)
    response.raise_for_status()
    content = response.text

    ticker_cik = {}
    for line in content.splitlines():
        t, c = line.strip().split('\t')
        ticker_cik[t.upper()] = c.zfill(10)
    return ticker_cik

# Add CIK column to the dataframe
ticker_cik = get_ticker_cik_mapping()
df['CIK'] = df['Ticker'].apply(lambda x: ticker_cik.get(x.upper(), ''))

# Save updated CSV
df.to_csv('data/sp500_companies.csv', index=False)
```

**Corner Cases:**

- **User-Agent Header**: Required by the SEC to prevent blocking.
- **CIK Not Found**: If a ticker is not found in `ticker.txt`, the CIK is left empty.

### Downloading Financial Concepts

We extract financial data from the SEC's EDGAR database using their API. We focus on specific financial concepts over the last 10 years.

#### Concepts Included

- **Income Statement Items:**
  - `EarningsPerShareBasic`
  - `EarningsPerShareDiluted`
  - `NetIncomeLoss`
  - `OperatingIncomeLoss`
  - `GrossProfit`
  - `Revenues` (or `SalesRevenueNet` as an alternative)

- **Cash Flow Items:**
  - `NetCashProvidedByUsedInOperatingActivities` (Operating Cash Flow)
  - `NetCashProvidedByUsedInInvestingActivities` (Investing Cash Flow)
  - `NetCashProvidedByUsedInFinancingActivities` (Financing Cash Flow)
  - `PaymentsToAcquirePropertyPlantAndEquipment` (CapEx)

- **Dividends and Buybacks:**
  - `DividendsPaid` (e.g., `PaymentsOfDividendsCommonStock`, `PaymentsOfDividends`)
  - `ShareRepurchases` (e.g., `PaymentsForRepurchaseOfCommonStock`, `PurchaseOfEquitySecurities`)

#### Handling Alternative Concepts

Companies may use different XBRL tags for the same financial concept. We handle this by creating a mapping of concept categories to their possible tags.

```python
concepts = {
    'EarningsPerShareBasic': ['EarningsPerShareBasic'],
    'EarningsPerShareDiluted': ['EarningsPerShareDiluted'],
    'NetIncomeLoss': ['NetIncomeLoss'],
    'OperatingIncomeLoss': ['OperatingIncomeLoss'],
    'GrossProfit': ['GrossProfit'],
    'Revenues': ['Revenues', 'SalesRevenueNet'],
    'NetCashProvidedByUsedInOperatingActivities': ['NetCashProvidedByUsedInOperatingActivities'],
    'NetCashProvidedByUsedInInvestingActivities': ['NetCashProvidedByUsedInInvestingActivities'],
    'NetCashProvidedByUsedInFinancingActivities': ['NetCashProvidedByUsedInFinancingActivities'],
    'PaymentsToAcquirePropertyPlantAndEquipment': ['PaymentsToAcquirePropertyPlantAndEquipment'],
    'DividendsPaid': ['PaymentsOfDividendsCommonStock', 'PaymentsOfDividends'],
    'ShareRepurchases': ['PaymentsForRepurchaseOfCommonStock', 'PurchaseOfEquitySecurities']
}
```

#### Corner Cases and Data Variability

- **Missing Data**: Not all companies report all concepts or use the same tags.
- **Units**: Financial data can be reported in different units (e.g., thousands, millions). Units are stored alongside values.
- **Date Alignment**: Financial statements have different periods. We use 'fy' (fiscal year) and 'fp' (fiscal period) for alignment.

---

## Data Processing

### Adjusting for Stock Splits

Stock splits affect both stock prices and per-share financial metrics like EPS. We adjust historical EPS data to reflect current share counts.

- **Stock Prices**: Use the `adjClose` price, which is adjusted for splits.
- **EPS Adjustment**: Multiply historical EPS by the cumulative split factor.

```python
# Calculate cumulative split factor
stock_df['cumulative_split'] = stock_df['splitFactor'].cumprod()

# Adjust EPS for splits
eps_df['adj_EarningsPerShareDiluted'] = eps_df['EarningsPerShareDiluted'] * eps_df['cumulative_split']
```

### Calculating Trailing Twelve Months (TTM) EPS

We compute the TTM EPS by summing the adjusted EPS over the last four quarters.

```python
# Compute TTM EPS
eps_df['TTM_EPS'] = eps_df['adj_EarningsPerShareDiluted'].rolling(window=4).sum()
```

### Normalizing Data

To compare growth over time, we normalize both the adjusted stock price and TTM EPS to start at the same value.

```python
# Normalize data
stock_df['normalized_price'] = stock_df['adjusted_close'] / initial_price
stock_df['normalized_ttm_eps'] = stock_df['TTM_EPS'] / initial_ttm_eps
```

---

## Visualization

### Plotting Stock Prices and TTM EPS

We create a plot with the normalized stock price as a black line and the normalized TTM EPS as a green area.

```python
import plotly.graph_objects as go

fig = go.Figure()

# Plot stock price
fig.add_trace(
    go.Scatter(
        x=stock_df['date'],
        y=stock_df['normalized_price'],
        name='Adjusted Close Price',
        mode='lines',
        line=dict(color='black')
    )
)

# Plot TTM EPS
fig.add_trace(
    go.Scatter(
        x=stock_df['date'],
        y=stock_df['normalized_ttm_eps'],
        name='TTM EPS (4-Quarter Sum)',
        mode='lines',
        line=dict(color='green'),
        fill='tozeroy',
        fillcolor='rgba(0, 255, 0, 0.3)'
    )
)

# Update layout
fig.update_layout(
    title='AAPL Stock Price and TTM EPS (Normalized)',
    xaxis_title='Date',
    yaxis_title='Normalized Value',
    legend_title='Legend',
    template='plotly_white'
)

fig.show()
```

### Adding Insider Trading Activities

We overlay insider buys and sells on the stock price chart, marking them with colored symbols and annotating the transaction amounts.

```python
# Add insider buys
fig.add_trace(
    go.Scatter(
        x=insider_buys['transaction_date'],
        y=insider_buys['transaction_price'],
        mode='markers+text',
        name='Insider Buys',
        marker=dict(color='limegreen', symbol='triangle-up', size=12),
        text=insider_buys['formatted_amount'],
        textposition='top center'
    )
)

# Add insider sells
fig.add_trace(
    go.Scatter(
        x=insider_sells['transaction_date'],
        y=insider_sells['transaction_price'],
        mode='markers+text',
        name='Insider Sells',
        marker=dict(color='tomato', symbol='triangle-down', size=12),
        text=insider_sells['formatted_amount'],
        textposition='bottom center'
    )
)
```

### Incorporating Additional Financial Metrics

We can plot other financial metrics, such as dividends and share buybacks, to analyze capital allocation strategies.

```python
# Plot dividends paid over time
fig.add_trace(
    go.Bar(
        x=financial_data['date'],
        y=financial_data['DividendsPaid'],
        name='Dividends Paid',
        yaxis='y2'
    )
)

# Plot share repurchases over time
fig.add_trace(
    go.Bar(
        x=financial_data['date'],
        y=financial_data['ShareRepurchases'],
        name='Share Repurchases',
        yaxis='y2'
    )
)

# Update layout to include a secondary y-axis
fig.update_layout(
    yaxis2=dict(
        title='Amount ($)',
        overlaying='y',
        side='right'
    )
)
```

---

## Compliance with SEC Guidelines

- **User-Agent Header**: All HTTP requests to the SEC's servers include a `User-Agent` header with contact information.
- **Rate Limiting**: We implement delays between requests to avoid exceeding the SEC's recommended limits.
- **Caching**: Responses are cached locally to minimize redundant requests.

**Example of Delay Implementation:**

```python
# Delay between requests
time.sleep(0.2)  # After each download
time.sleep(0.5)  # Between processing each ticker
```

---

## Usage Instructions

1. **Clone the Repository**: Ensure you have all the scripts and directories set up as described.
2. **Install Dependencies**: Install the required Python libraries.
3. **Update User-Agent**: Replace `'Your Name yourname@example.com'` with your actual name and email in the code.
4. **Run Data Extraction Script**: Execute the script to download and save financial data for S&P 500 companies.
5. **Process and Visualize Data**: Use the provided notebooks or scripts to process the data and generate visualizations.

---

# SEC XBRL Downloader

This Python script downloads and processes XBRL (eXtensible Business Reporting Language) files from the U.S. Securities and Exchange Commission (SEC) EDGAR database for specified companies and filing types.

## Features

- Downloads XBRL instance documents for a given ticker symbol and filing type
- Caches downloaded files to reduce unnecessary network requests
- Extracts relevant information from SEC filing URLs
- Renames and stores processed XML files with a consistent naming convention

## Main Functions

### `get_cik(ticker)`
Retrieves the Central Index Key (CIK) for a given ticker symbol.

### `download_xml(ticker, filing_type='10-Q', num_filings=5)`
Downloads XBRL files for the specified ticker, filing type, and number of filings.

### `rename_and_store_xml_files(xml_files, ticker, destination_folder='xbrls')`
Renames and stores the downloaded XML files using a consistent naming convention.

## File Naming Convention

The script renames downloaded files using the following format:

```text
{ticker}-{cik}-{accession_number}-{date}.xml
```

- `ticker`: The stock ticker symbol (lowercase)
- `cik`: The 10-digit Central Index Key
- `accession_number`: The SEC filing accession number
- `date`: The filing date in `YYYYMMDD` format

## Caching

The script implements a caching mechanism to avoid redundant downloads. Cached files are stored in the following directories:

- HTML files: `sec_cache/`
- XML files: `xml_cache_{ticker}/`

## Limitations

- The script is designed for educational and research purposes and should be used in compliance with SEC's fair access rules.
- It may require adjustments for different filing types or changes in the SEC's website structure.

## Disclaimer

This script is provided as-is, without any warranties or guarantees. Users should ensure they comply with SEC's terms of service and usage guidelines when accessing EDGAR data.
