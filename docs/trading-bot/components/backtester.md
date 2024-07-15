# Backtester

Run/optimize a strategy on test data, using [backtesting.py][backtesting.py].

![](../../static/trading-bot/backtest.jpg)

Run `python -m backtester --help` for more info.

## Chanel's Tasks (What is this?)

-   Take in strategies (trade multiple instruments)
    -   Forex
    -   Index-Based ETFs
    -   Commodity Futures
-   Generate Report on Strategy
    -   For each trading model for each instrument - optimize parameters
    -   Select best trading model and test on new month data
    -   Scenario analysis simulation
        -   Down
        -   Up
        -   Ranging

[backtesting.py]: https://kernc.github.io/backtesting.py/
