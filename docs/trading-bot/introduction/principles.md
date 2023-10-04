# Core Principles

During development of the trading bot, the following principles, which guide development, were agreed upon.

## 1. Fully automated

There should **never** be any manual take profit button, close position button, or any possibility for interfering with a trade whatsoever (barring errors occuring as a result of programming). While this may seem risky, the whole idea of the trading bot is so that human emotions and biases such as fear and greed do not play a part in trading, and lets us focus on what should really be improved upon - the algorithm.

## 2. Profitable

All rules in production must have at least a 1y backtest with positive return.

## 3. Pure functions

Models (and by extension, Strategies) must be pure functions.

This means that given the same inputs (e.g. `position`, `avg_cost`, OHLC data), it must return the same outputs (e.g. `confidence`). There must be no internal or hidden state whatsoever.

For example, the following is not allowed:

```python
class MyModel(BaseModel):

  # ...

  def get_confidence(
      self,
      position: float,
      avg_cost: float | None,
      **kwargs,
  ) -> tuple[float, list]:

    # Check if function was called in the last 15 minutes
    within_15_min = self.last_called - datetime.datetime.now() < datetime.timedelta(minutes=15)

    # If called in the last 15 minutes, return confidence of 0
    if within_15_min:
        return 0

    # Otherwise, continue with execution
    self.last_called = datetime.datetime.now()
    # ...
```

In the example above, there is an implicit variable, `within_15_min`, which depends on whether the function was previously called in the last 15 minutes.

Functions like that are difficult to unit-test, so we should avoid those.