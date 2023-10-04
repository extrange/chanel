# Environment Variables

Secrets (such as usernames and passwords) are passed to each container via environment variables supplied from a `.env` file.

At runtime, Docker [substitutes] environment variables defined in the Compose file with the values in the `.env` file.

## The `ibkr` container

Runs [IBKR Docker], which the trading bot uses to connect to IBKR's servers.

`USERNAME`: Your IBKR username corresponding to the account type (`paper`/`live`)

`PASSWORD`: Your IBKR password

`PORT`: port to access the noVNC viewer for IBKR Docker (e.g. `6080`)

`TRADING_MODE`: `paper` or `live`

For more options, refer to the [repo][ibkr-docker-env].

## The `bot` container

The container running the trading bot.

`ACCOUNT`: IBKR account number, e.g. `U1234567`

`CHAT_ID`: ID of Telegram chat/group which notifications will be sent. The bot will only respond to commands from this group.

`UID`: The Linux user identifier of the current user (usually `1000`). Togethr with `GID`, this is used to set the owner of files created by the `bot` container (which is `root` by default).

`GID`: The Linux group identifier of the current user (usually `1000`).

[IBKR Docker]: https://github.com/extrange/ibkr-docker
[ibkr-docker-env]: https://github.com/extrange/ibkr-docker#environment-variables
[substitutes]: https://docs.docker.com/compose/environment-variables/set-environment-variables/
