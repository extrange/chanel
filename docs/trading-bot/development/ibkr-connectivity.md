# IBKR Connectivity Issues

IBKR (and by extension, the `ib_insync` library) has some platform-specific quirks which affect connectivity, and are important to understand.

## IB Gateway Restart Schdule

IB Gateway insists on being [restarted daily] at least once. IBC can help with this, and the setting for the auto-restart is via the `docker compose` variable `IBC_AutoRestartTime`. No user authentication is required for this.

IB Gateway also insists on being **fully** [restarted weekly] (every Sunday at 1300 SGT). A manual login is required for this.

There are also routine server [resets], which occur:

- Daily at 0545 SGT (few seconds)
- Weekly on Saturday 1100-1500 SGT (entire duration)

No connectivity to IB is available during those times.

## IBKR 'soft disconnects'

At times, IBKR stops sending market data updates for seemingly no reason. These episodes are ofter preceded by the following error:

```
ib_insync.wrapper - ERROR - Error 366, reqId 6: No historical data query found for ticker id:6, contract: Forex('CHFJPY', conId=14321010, exchange='IDEALPRO', localSymbol='CHF.JPY', tradingClass='CHF.JPY')
```

[`timeoutEvent`][timeoutEvent] seems like it should work but as of `ib_insync 0.9.86` it is not called even after the above event happens.

The best solution right now seems to be to not rely on `updateEvent`, and instead call `reqHistoricalDataAsync` (async version of [`reqHistoricalData`][reqHistoricalData]) periodically from our code.


[restarted daily]: https://github.com/IbcAlpha/IBC/blob/ff041039e9f21369ebb3adb28dfda88a058237cd/resources/config.ini#L523
[restarted weekly]:https://www.ibkrguides.com/tws/usersguidebook/configuretws/auto_restart_info.htm
[resets]: https://www.interactivebrokers.com/en/index.php?f=2225
[timeoutEvent]: https://ib-insync.readthedocs.io/api.html#module-ib_insync.ib
[reqHistoricalData]: https://ib-insync.readthedocs.io/api.html#ib_insync.ib.IB.reqHistoricalData