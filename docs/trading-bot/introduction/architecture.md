# Architecture

```mermaid
graph TD
  IbkrDocker["IBKR Gateway (Docker)"]
  TradingConfig
  CommandHandler
  Telegram
  IBKR[IBKR's Servers]

  IbkrDocker <--> |TWS Gateway| IBKR
  CommandHandler --> |controls| TradingEngine

  TradingEngine["Trading Engine (see below)"]
  TradingConfig["Trading Config"] --> TradingEngine

  TradingEngine <-->|ib_insync| IbkrDocker
  Telegram --> CommandHandler
```

## Trading Engine

The Trading Engine is the heart of the bot, and receives market data, executes strategies, and performs trade executions.

```mermaid
graph TD

  Instrument1["Instrument 1"]
  Instrument2["Instrument 2"]
  Instrument3["Instrument 3"]
  Model1["Model 1"]
  Model2["Model 2"]
  Model3["Model 3"]
  Sizer["Sizer"]
  Position1["Units to buy/sell for<br/>Instrument 1"]
  Position2["Units to buy/sell for<br/>Instrument 2"]
  Position3["Units to buy/sell for<br/>Instrument 3"]
  ExecutionEngine["Execution Engine"]

  subgraph Strategy 1
    Instrument1 --> |price data| Model1
  end

  subgraph Strategy 2
    Instrument2 --> |price data| Model2
  end

  subgraph Strategy 3
    Instrument3 --> |price data| Model3
  end

  Model1 --> |confidence| Sizer
  Model2 --> |confidence| Sizer
  Model3 --> |confidence| Sizer
  Sizer --> Position1
  Sizer --> Position2
  Sizer --> Position3
  Position1 --> |executed by| ExecutionEngine
  Position2 --> |executed by| ExecutionEngine
  Position3 --> |executed by| ExecutionEngine
```

A strategy can be combined with any instrument. The same model can operate on different instruments, e.g. `Model1` on `Instrument1` and `Model2` on `Instrument1`.

Adapted from [Systematic Trading][systematic-trading]:

![](../../static/trading-bot/trading-system.png)

[systematic-trading]: https://github.com/extrange/trading-bot/releases/download/trading-books/systematic-trading.pdf
