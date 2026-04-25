# Portfolio_rebalancer_enhanced
Advanced Python GUI system for risk-aware stock portfolio rebalancing using technical indicators, two-level genetic optimization, NSGA-II, Pareto front analysis, walk-forward backtesting, and dynamic dashboards.

## Description

Portfolio_rebalancer_enhanced is an extended research software prototype for analyzing financial time series and building dynamic stock portfolio rebalancing strategies.

This project continues the previous Portfolio_Rebalancer work and develops it into a more complete experimental application. The system combines technical indicator analysis, asset scoring, multi-objective portfolio optimization, transaction cost modeling, walk-forward backtesting, and interactive GUI-based visualization.

The main goal of the project is not only to maximize final return, but also to improve the risk profile of a portfolio by controlling volatility, drawdown, turnover, diversification, and transaction costs.

## Research Topic

**Development of a software system for stock portfolio rebalancing based on technical indicators**

## Key Features

- OHLCV financial data loading and preprocessing
- Data caching and unified trading calendar construction
- Technical indicator calculation
- Rolling z-score normalization
- Asset attractiveness scoring
- Two-level genetic optimization architecture
- Level A: technical indicator weight calibration
- Level B: portfolio weight optimization
- NSGA-II-style multi-objective optimization
- Pareto front construction and visualization
- ASF-based executable solution selection
- Walk-forward backtesting
- Long and short position support
- Portfolio constraints by weight, leverage, and number of assets
- Transaction cost and turnover accounting
- Risk-aware performance evaluation
- Dynamic metric cards with mini charts
- Capital curve visualization with rebalancing markers
- Portfolio structure visualization
- Interactive dashboard
- Pareto front analysis tab
- GUI logging and background calculations without freezing the interface

## Project Evolution

This repository is a continuation of the previous portfolio rebalancing project.

The earlier version focused on building the basic pipeline:

- OHLCV data loading;
- technical indicator calculation;
- genetic algorithm-based asset scoring;
- portfolio optimization;
- backtesting;
- basic GUI and metrics.

The current version extends the project with a more advanced research-oriented architecture:

- improved two-level optimization model;
- NSGA-II-based portfolio optimization;
- Pareto front analysis;
- ASF rule for selecting the final portfolio;
- extended cost modeling;
- dynamic dashboards;
- improved GUI;
- richer experiment tracking;
- more detailed comparison with baseline strategies.

## Methodology

The system uses a two-level optimization approach.

### Level A — Asset-Level Optimization

At the first level, the system calibrates technical indicator weights for each asset.

The goal is to build an asset score that reflects the relative attractiveness of a stock based on historical indicator behavior.

The level A optimization uses:

- technical indicators;
- normalized features;
- genetic algorithm calibration;
- directional accuracy;
- regularization;
- walk-forward validation.

### Level B — Portfolio-Level Optimization

At the second level, the system selects portfolio weights during rebalancing.

The portfolio optimization problem is formulated as a multi-objective task with conflicting criteria:

- expected return;
- portfolio risk;
- turnover;
- concentration;
- transaction costs.

Instead of searching for a single objective optimum, the system builds a Pareto front of non-dominated portfolio solutions using an NSGA-II-style genetic algorithm.

The final executable portfolio is selected from the Pareto front using an ASF-based compromise rule.

## Optimization Criteria

The portfolio optimization process considers:

- net expected return;
- covariance-based risk;
- portfolio turnover;
- capital concentration;
- transaction costs;
- leverage limits;
- minimum and maximum asset weights;
- maximum number of active positions.

## Metrics

The system evaluates strategy performance using the following metrics:

- Total Return
- CAGR
- Annualized Volatility
- Sharpe Ratio
- Calmar Ratio
- Maximum Drawdown
- Average Turnover
- Total Transaction Costs
- Cost Rate
- Gross Exposure
- Short Exposure
- Effective Number of Positions
- Successful Rebalancing Periods
- Indicator-Level IC
- Directional Accuracy
- Level A Stability

## Experimental Setup

The prototype was tested on historical OHLCV stock market data from the Hugging Face `siddharthmb/stocks-ohlcv` dataset.

The main experimental scenario used a portfolio of 10 US stocks:

- MSFT
- JPM
- UNH
- MCD
- XOM
- CSCO
- IBM
- PFE
- M
- WBA

The system was compared with several baseline strategies:

- long-only holding of all assets;
- short-only holding of all assets;
- random position allocation.

## Results

The developed prototype demonstrated a positive final return while improving the portfolio risk profile compared to baseline strategies.

In the main experiment, the prototype achieved:

- lower volatility than the long-only baseline;
- lower maximum drawdown;
- higher Sharpe Ratio;
- higher Calmar Ratio;
- controlled portfolio concentration;
- meaningful diversification;
- positive performance after transaction costs.

The main practical result is improved risk-adjusted performance rather than simple maximization of final return.

## Technologies Used

- Python
- pandas
- NumPy
- SciPy
- Matplotlib
- Seaborn
- ttkbootstrap
- Tkinter
- Hugging Face datasets
- pyarrow
- Optuna
- Genetic Algorithms
- NSGA-II
- Pareto Optimization
- Walk-Forward Backtesting
- Technical Analysis
- Financial Time Series Analysis

## Project Structure

```text
Portfolio_rebalancer_enhanced/
├── data.py              # data loading, caching, calendar alignment
├── indicators.py        # technical indicators
├── signals.py           # normalization and asset scoring
├── level_a.py           # genetic calibration of indicator weights
├── risk.py              # covariance and risk estimation
├── costs.py             # transaction cost modeling
├── level_b.py           # portfolio-level NSGA-II optimization
├── pareto.py            # Pareto front and ASF solution selection
├── backtest.py          # walk-forward backtesting
├── gui.py               # graphical user interface
├── main.py              # application entry point
└── README.md
