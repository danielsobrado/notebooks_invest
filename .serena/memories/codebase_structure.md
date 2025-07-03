# Codebase Structure

## Root Directory
- `README.md` - Main project documentation
- `.gitignore` - Git ignore patterns
- Multiple analysis directories organized by topic

## Main Analysis Directories

### `/data/` - Data Sources and Collection
- `edgar/` - SEC EDGAR filings and earnings data
- `finviz/` - FinViz data collection notebooks
- `helper/` - Utility modules (e.g., finnhub_client.py)
- `indices_constituents/` - Index constituent data
- `investpy/` - Investing.com data
- `kaggle/` - Kaggle datasets
- `margin_statistics/` - FINRA margin statistics
- `stooq/` - Stooq market data
- `tiingo/` - Tiingo fundamental data
- `yfinance/` - Yahoo Finance data

### `/strategies/` - Trading Strategies
- `base.py` - Base strategy class for backtesting
- `util.py` - Utility functions for strategy analysis
- Multiple strategy notebooks (Buy and Hold, RSI, Moving Average, etc.)
- `PutCall/` - Put/Call ratio strategies
- `VIX/` - VIX-based strategies

### `/indicators/` - Technical Analysis
- Technical indicator analysis notebooks
- Mansfield Relative Strength analysis

### `/insiders/` - Insider Trading Analysis
- SEC insider trading data analysis
- Multiple data sources and parsing notebooks

### `/seasonality/` - Seasonal Analysis
- Market seasonality studies
- Day/month/sector seasonality analysis

### `/machine_learning/` - ML Applications
- Deep learning notebooks
- NLP text analysis with parallelization

### `/cycles/` - Market Cycles
- Benner Cycle analysis
- Presidential Cycle analysis

### `/countries/` - International Analysis
- Country performance analysis

## File Patterns
- **Notebooks**: `.ipynb` files for analysis and experimentation
- **Data**: `.csv` files as primary storage format
- **Support**: `.py` modules for reusable code
- **Configuration**: Minimal, mostly embedded in notebooks

## Data Organization
- Raw data stored in respective source directories
- Processed data often in `/data/` subdirectories
- No central data management system