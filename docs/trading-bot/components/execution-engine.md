# Execution Engine

Uses [IBKR Docker][ibkr-docker] to connect to [Interactive Broker][ibkr]'s [API][tws-api], to fetch prices and execute trades (as returned by the `Sizer`). This also allows connecting to [paper trading accounts][paper-trading], which receive the same prices as real money accounts.

Also manages reconnections.

[ibkr-docker]: https://github.com/extrange/ibkr-docker
[ibkr]: https://www.interactivebrokers.com/en/home.php
[paper-trading]: https://www.interactivebrokers.com/en/software/omnibrokers/topics/papertrader.htm
[tws-api]: https://interactivebrokers.github.io/tws-api/
