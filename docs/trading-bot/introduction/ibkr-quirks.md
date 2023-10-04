# IBKR Quirks

IBKR has some platform-specific quirks which affect connectivity, and are important to understand.

## IB Gateway Restart Schdule

IB Gateway insists on being [restarted daily] at least once. IBC can help with this, and the setting for the auto-restart is via the `docker compose` variable `IBC_AutoRestartTime`. No user authentication is required for this.

IB Gateway also insists on being **fully** [restarted weekly] (every Sunday at 1300 SGT). A manual login is required for this.

There are also routine server [resets], which occur:

- Daily at 0545 SGT (few seconds)
- Weekly on Saturday 1100-1500 SGT (entire duration)

No connectivity to IB is available during those times.

[restarted daily]: https://github.com/IbcAlpha/IBC/blob/ff041039e9f21369ebb3adb28dfda88a058237cd/resources/config.ini#L523
[restarted weekly]:https://www.ibkrguides.com/tws/usersguidebook/configuretws/auto_restart_info.htm
[resets]: https://www.interactivebrokers.com/en/index.php?f=2225