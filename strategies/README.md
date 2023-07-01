# Starting

Let's create a conda environment:

* Create a new environment: `conda create -n backtest python=3.10`
* Activate the environment: `conda activate backtest`
* Install the necessary libraries: `conda install nb_conda_kernels yfinance backtrader jupyter notebook pandas plotly matplotlib pyfolio`

Backtrader is a well-known Python library for testing trading strategies. It includes tools for data feeding, strategy execution, trading simulation, and trading strategy performance analysis.

# Strategies

## Simple Gold Strategy

The approach is really straightforward and is built on two principles:

* The market constantly rises with time.
* Precious metals (specifically gold) tend to display a seasonal up-trend during December-February, and around August
The trading strategy is as follows:

Hold GLD (SPDR Gold Trust ETF) from December 20 of every year through February 20 of the following year, and during August.
* The rest of the time hold SPLV (Invesco S&P 500 Low Volatility ETF)
* This strategy is not optimized and simply involves buying Gold during its seasonal up-trend and a low volatility "market" ETF the rest of the time​​.

