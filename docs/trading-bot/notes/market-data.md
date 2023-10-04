# Market Data Sources

Comparison of various sources to get market data.

| Source | Cost | Description | Data Availability |
|||-|-|
| [histdata.com][histdata.com] | Free | For FX data. An open-source [script][histdata-script] is available to download the latest data in bulk. | From 2001 to present |
| [Dukascopy][dukascopy] | Free (requires account) | For FX data. | From 2003 to present |
| [IBKR API][ibkr] | Free (uses existing market data subscription) | For all products. Has [many restrictions][ibkr-data-limitations]. Not recommended for backtesting use (time period too short). | Limited to last 6 months |
| [findatpy][findatpy] | Free (open source) | Python API to download market data from many sources including Quandl, Bloomberg, Yahoo, Google etc. using a unified high level interface. | Varies |
| [pandas-datareader][pandas-datareader] | Free (open source) | Extract data from a wide range of Internet sources into a Pandas DataFrame. | Varies |
| [Nasdaq Data Link][nasdaq-data-link] (formerly Quandl) | Paid | Offers stock, currency, option and a large variety of historical data from various ranges. | Varies |

[histdata-script]: https://github.com/philipperemy/FX-1-Minute-Data
[histdata.com]: https://www.histdata.com/
[nasdaq-data-link]: https://data.nasdaq.com/
[pandas-datareader]: https://pandas-datareader.readthedocs.io/en/latest/index.html
[findatpy]: https://github.com/cuemacro/findatapy
[dukascopy]: https://www.dukascopy.com/swiss/english/marketwatch/historical/
[ibkr]: https://interactivebrokers.github.io/tws-api/historical_data.html
[ibkr-data-limitations]: https://interactivebrokers.github.io/tws-api/historical_limitations.html
