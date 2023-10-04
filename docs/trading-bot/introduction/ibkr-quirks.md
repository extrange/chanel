# IBKR Quirks

IBKR has some platform-specific quirks which affect connectivity, and they are detailed here.

## IB Gateway Restart Schdule

IB Gateway [insists][ib-daily-restart] on being restarted daily at least once. IBC can help with this, and the setting for the auto-restart is via the `docker compose` variable `IBC_AutoRestartTime`. No user authentication is required for this.

IB Gateway also insists on being **fully** restarted [weekly][ib-weekly-restart] (every Sunday at 1300 SGT). A manual login is required for this.

There are also routine server resets, which occur:

- Daily at 0545 SGT (few seconds)
- Weekly on Saturday 1100-1500 SGT (entire duration)

No connectivity to IB is available during those times.

[ib-daily-restart]: https://github.com/IbcAlpha/IBC/blob/ff041039e9f21369ebb3adb28dfda88a058237cd/resources/config.ini#L523
[ib-weekly-restart]:https://www.ibkrguides.com/tws/usersguidebook/configuretws/auto_restart_info.htm
[ib-server-reset]: https://www.interactivebrokers.com/en/index.php?f=2225