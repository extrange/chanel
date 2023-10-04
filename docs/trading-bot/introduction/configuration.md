# Configuration

## Environment Variables

`USERNAME`: Your IBKR username corresponding to the account type (`paper`/`live`)

`PASSWORD`: Your IBKR password

`ACCOUNT`: IBKR account number, e.g. `U1234567``

`PORT`: port to access the noVNC viewer for IBKR Docker (e.g. `6080`)

`CHAT_ID`: ID of Telegram chat/group which notifications will be sent. The bot will only respond to commands from this group.

`TRADING_MODE`: `paper` or `live`

| Key          | Value                               |
| ------------ | ----------------------------------- |
| USERNAME     | IBKR username                       |
| PASSWORD     | IBKR password                       |
| ACCOUNT      | IBKR account number, e.g. U1234567  |
| PORT         | noVNC viewer port, e.g. 6080        |
| CHAT_ID      | Telegram group ID for notifications |
| TRADING_MODE | 'paper' or 'live'                   |
| UID          | 1000                                |
| GID          | 1000                                |
