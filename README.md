# Stock Market Notebooks

The objective of this repo is to analyze historical market data to gain insights that you can only get by doing your own experiments.

You should research them by analyzing historical data in order to have in-depth knowledge about the market.

Know how the market works by looking into the data from multiple angles, don't trust blindly other people's analysis and charts, do your own homework.

## Data Sources

Data is key. Having good sources of data is a challenge, and also very important. 

We'll use free data sources in these repositories, but you'll be able to extrapolate the analysis, to other commercial data, if required.

### Investpy

[Investpy](https://github.com/alvarobartt/investpy) is a Python package to retrieve data from Investing.com

Install it via pip with a Python3.5 version or higher:

``$ pip install investpy``

### Kaggle

Kaggle is one amazing source of datasets, very dynamic and with a thriving community.

#### Huge Stock Market Dataset

[Huge Stock Market Dataset](https://www.kaggle.com/borismarjanovic/price-volume-data-for-all-us-stocks-etfs)  full historical daily price and volume data for all US-based stocks and ETFs trading on the NYSE, NASDAQ, and NYSE MKT.

The data (last updated 11/10/2017) is presented in CSV format as follows: Date, Open, High, Low, Close, Volume, OpenInt. Note that prices have been adjusted for dividends and splits.

#### Financials as Reported 2010-2020 - SEC Filings

Source: [Finnhub - Financials Reported](https://finnhub.io/docs/api#financials-reported)

[reported-financials](https://www.kaggle.com/finnhub/reported-financials) The data is cleaned and sourced directly from SEC filings from 2010-2020.

#### SEC Filings 1994-2020

Source: [Finnhub - Filings](https://finnhub.io/docs/api#filings)

[SEC Filings 1994-2020](https://www.kaggle.com/finnhub/sec-filings)  The data is cleaned and sourced directly from SEC filings from 1994-2020.

#### S&P 500 futures tick data (SP)

Source: [Finnhub](https://finnhub.io/)

[S&P 500 futures tick data](https://www.kaggle.com/finnhub/sp-500-futures-tick-data-sp)  S&P futures tick dataset from 2000-2019.

#### Historical stock data for all current S&P 500 companies

Historical stock prices (last 5 years) for all companies currently found on the S&P 500 index.

The script I used to acquire all of these .csv files can be found in this [GitHub repository] (https://github.com/CNuge/kaggle-code/tree/master/stock_data)

[Historical stock data for all current S&P 500 companies] (https://www.kaggle.com/camnugent/sandp500) The data from The Investor's Exchange api.

### Stooq
[Stooq](https://stooq.com/db/h/)  Daily	Hourly and 5 Minutes data for multiple markets (World, U.S., U.K., Japan, Hong Kong, Germany, Poland, Hungary and some Macroeconomy indicators).

### Paid services with free allowance
* [Polygon](https://polygon.io/)

### Data Scrapping

* [FinViz](https://finviz.com/)
    * Scrap with: [FinViz Finance](https://github.com/lit26/finvizfinance)
        * ``pip install finvizfinance``
        * Sample Notebook: 
* [Graph Fundamentals] (http://graphfundamentals.com/) Free forever, they claim the source is the SEC fillings, I can see that the quality is not great, probably because of inconsistencies in the format of the fillings.

### Shiller

Data used in the book: *Irrational Exuberance* [Princeton University Press 2000, Broadway Books 2001, 2nd ed., 2005]

[Online DATA ROBERT SHILLER](http://www.econ.yale.edu/~shiller/data.htm) This data set consists of monthly stock price, dividends, and earnings data and the consumer price index (to allow conversion to real values), all starting January 1871. 

### FINRA Margin Statistics

* [Margin Statistics] https://www.finra.org/investors/learn-to-invest/advanced-investing/margin-statistics

## Statistics

## Seasonality

### Day of the week
* Sample Notebook:

### Month of the year
* Sample Notebook:

## Sentiment

## Insiders

One of the most famous investors of all time, Peter Lynch, said  "insiders might sell their shares for any number of reasons, but they buy them for only one: they think the price will rise."

**See**: [Insiders]  (https://github.com/danielsobrado/notebooks_invest/tree/master/insiders)

### Insider Websites
- [Insider Monkey](https://www.insidermonkey.com/)
- [Insider Screener](https://www.insiderscreener.com/en/)
- [Insider Tracking](https://www.insidertracking.com/)
- [Open Insider](http://openinsider.com/)
- [Senate Stock Watcher](https://senatestockwatcher.com/)

### Webs

* [Sec Api](https://sec-api.io/)
    * Sample Notebook: 
* [Insider Monitor](https://www.insider-monitor.com/)
    * Sample Notebook: 

### SEC-Edgar

[sec-edgar](https://github.com/sec-edgar/sec-edgar) is a Python package to  download all of a company’s periodic reports, filings and forms from the EDGAR database.

Install it via pip with:

``$ pip install secedgar``

### SEC Edgar Downloader 

[sec-edgar-downloader](pip install -U sec-edgar-downloader) is a Python package for downloading company filings from the SEC EDGAR database. Searches can be conducted either by stock ticker or Central Index Key (CIK).

Install it via pip with:

``$ pip install -U sec-edgar-downloader``

## Constituents

* Scrape ETF holdings:[etf4u](https://github.com/leoncvlt/etf4u)

## Indicators

### Moving averages
* Sample Notebook:

### RSI
* Sample Notebook:

### MACD
* Sample Notebook:

### Demark TD Sequential
* Sample Notebook:
References:
* Example from: [finplot](https://github.com/highfestiva/finplot/blob/master/finplot/examples/bfx.py)
* Example from: [AdhamAlHarazi](https://github.com/AdhamAlHarazi/StockMarketAlgos/blob/master/Demark%20Indicators%20Tested.py)
See: https://github.com/txjohnny5/Tom-Demark-Indicator/blob/master/TD_plotter.py
Study on TD Sequential and improvements: [cloudquant](https://info.cloudquant.com/2017/08/improving-td-bear-flip/)

## Strategies

### Buy & Hold
* Sample Notebook:

### Sector Rebalancing

## Interesting Repos

### Compilations
* Compilation of resources Quant Machine Learning: [Awesome Quant Machine Learning Trading](https://github.com/grananqvist/Awesome-Quant-Machine-Learning-Trading)
* Compilation of resources Deep Learning Trading: [Awesome Deep Trading](https://github.com/cbailes/awesome-deep-trading)

### Visualization
* Visual analysis of financial data: [Matplotlib Finance](https://github.com/matplotlib/mplfinance)</br>
``pip install --upgrade mplfinance``
* [Finance Plotter] (https://github.com/highfestiva/finplot)
``pip install finplot``
* Altair and Vega: [Altair] (https://altair-viz.github.io/)</br>
``pip install altair_viewer``</br>
``conda install vega``</br>
``jupyter nbextension install --sys-prefix --py vega``</br>
``jupyter nbextension enable vega --py --sys-prefix``</br>
``jupyter labextension install @jupyterlab/vega5-extension``</br>
* Plotly: [Plotly] (https://pypi.org/project/plotly/)
``pip install plotly==4.14.3``</br>
``pip install "notebook>=5.3" "ipywidgets>=7.5"``

### Data 
* Postgres based DB to capture and store data: [pySecMaster](https://github.com/camisatx/pySecMaster)

### Machine Learning
* Reinforcement Learning for trading: [FinRL: A Deep Reinforcement Learning Library for Quantitative Finance](https://github.com/AI4Finance-LLC/FinRL-Library)
* MlFinlab: [MlFinlab](https://github.com/hudson-and-thames/mlfinlab)

## Interesting Links

* Gary Antonacci’s Dual Momentum Explained: [Dual Momentum](https://engineeredportfolio.com/2018/05/02/accelerating-dual-momentum-investing/) 

### Portfolio Optimization

Portfolio Allocation backtesting and simulations:

* Portfolio Charts: https://portfoliocharts.com/portfolios/
* Portfolio Visualizer: https://www.portfoliovisualizer.com/
* Backtest: https://backtest.curvo.eu/

### Blogs

Great blogs and aggregators to follow:

* [Quantdare](https://quantdare.com/) 
* [Quantocracy](https://quantocracy.com/)
* [Alpha Architect](https://alphaarchitect.com/)
* [Milton Financial Market Research Institute](https://miltonfmr.com/)
* [Cesar Alvarez](https://alvarezquanttrading.com
    * The [Barometer](https://alvarezquanttrading.com/market-barometer/) is interesting.

## Disclaimer
Before using this software, be sure to understand and follow the terms of all data providers. I am not responsible for how you use this software, so please be responsible in your use of it! Please see the following links for some information:

  - [Quandl TOS](http://help.quandl.com/category/133-terms-and-conditions)
  - [Google Finance TOS](https://www.google.com/intl/en/googlefinance/disclaimer)
  - [Yahoo Finance TOS](https://policies.yahoo.com/us/en/yahoo/terms/utos/index.htm)

For further information, please seek legal counsel.

## License (GNU AGPLv3)

This program is free software: you can redistribute it and/or modify it under the terms of the GNU Affero General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU Affero General Public License for more details.

You should have received a copy of the GNU Affero General Public License along with this program. If not, see http://www.gnu.org/licenses/.
