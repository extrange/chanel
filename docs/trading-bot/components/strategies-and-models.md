# Strategies and Models

A `Model` takes in price data from an instrument, optionally with the current position in that instrument, and calculates a confidence score, which is used by the `Sizer` to determine the desired position in that instrument.

A `Model` can be used with any instrument, although it may perform better for certain instruments.

Models subclass `BaseModel`, which itself is a subclass of [`backtesting.Strategy`][backtesting.strategy] (and which can therefore be run in backtesting.py).

Models should be in a individual named file under `models/`, e.g. `models/my_model.py`.

The combination of a `Model` and an `Instrument` is known as a `Strategy`.

`Strategy`s can be backtested individually.

[backtesting.strategy]: https://kernc.github.io/backtesting.py/doc/backtesting/backtesting.html#backtesting.backtesting.Strategy
