# Trading Bot Core

Main indicators: Awesome Oscillator

Platform: IBKR

Products: Forex for now (less market influence)

## Forex Basics

### What is a Pip 
- Forex currency pairs are quoted in terms of pips, short for percentage in points.
-  In practical terms, a pip is one-hundredth of one percent (1/100 x .01) and appears in the fourth decimal place (0.0001).
-  A pip equals one basis point.
-  The bid-ask spread of a forex quote is measured in pips.
-  The Japanese yen is an exception because its exchange rate extends only two decimal places past the decimal point, not four.

### Calculating Pip
- Assuming forex account is funded with U.S. dollars
- When the USD is the second of the pair (or the quote currency), Multiply the size of a pip  by the trade value. (EURUSD, GBPUSD)
	If you bought 10,000 euros against the dollar at 1.0801 and sold at 1.0811, you'd make a profit of 10 pips or $10. 
- When the USD is the first of the pair (or the base currency), Divide the size of a pip by the exchange rate and then multiply by the trade value. (USDJPY, USDCHF)
	If you bought 100,000 USD against the Canadian dollar at 1.2829 and sold at 1.2830, you'd make a profit of 1 pip or $7.79.


## 0. Risk Management
### Crap trades, timeouts and monthly limits
Equally, you need to set monthly limits. A standard limit might be a 10% account balance stop per month. At that point you close all your positions immediately and stop trading till next month.

Having monthly calendar breaks is nice for another reason. Say you made a load of money in January. You don’t want to start February feeling you are up 5% or it is too tempting to avoid trading all month and protect the existing win. Each month and each year should feel like a clean slate and an independent period. 

Everyone has trading slumps. It is perfectly normal. It will definitely happen to you at some stage. The trick is to take a break and refocus. Conserve your capital by not trading a lot whilst you are on a losing streak. This period will be much harder for you emotionally and you’ll end up making suboptimal decisions. An enforced break will help you see the bigger picture.

### Squeezes 

- A short squeeze is when a participant ends up in a short position they are forced to cover. Especially when the rest of the market knows that this participant can be bullied into stopping out at terrible levels, provided the market can briefly drive the price into their pain zone.

- Knowing if the market is currently at extreme levels of long or short can therefore be helpful. 
	- The CFTC makes available a weekly report, which details the overall positions of speculative traders “Non Commercial Traders” in some of the major futures products. This includes futures tied to deliverable FX pairs such as EURUSD as well as products such as gold. The report is called “CFTC Commitments of Traders” ("COT").
	- This is a great benchmark. It is far more representative of the overall market than the proprietary ones offered by retail brokers as it covers a far larger cross-section of the institutional market. 
	- Generally market participants will not pay a lot of attention to commercial hedgers, which are also detailed in the report. This data is worth tracking but these folks are simply hedging real-world transactions rather than speculating so their activity is far less revealing and far more noisy. 
	- ou can find the data online for free and [download it directly here](https://www.cftc.gov/MarketReports/CommitmentsofTraders/HistoricalViewable/index.htm).

### Events

- Economic releases can cause large short-term volatility. The most famous is Non Farm Payrolls, which is the most widely watched measure of US employment levels and affects the price of many instruments.On an NFP announcement currencies like EURUSD might jump (or drop) 100 pips no problem. 

- This is fine and there are trading strategies that one may employ around this but the key thing is to be aware of these releases.You can find economic calendars all over the internet - including on this site - and you need only check if there are any major releases each day or week.

- For example, if you are trading off some intraday chart and scalping a few pips here and there it would be highly sensible to go into a known data release flat as it is pure coin-toss and not the reason for your trading. It only takes five minutes each day to plan for the day ahead so do not get caught out by this. Many retail traders get stopped out on such events when price volatility is at its peak.

### Asymmetric losses

- Ideally what you are looking for is asymmetric risk trade set-ups: that is where the downside is clearly defined and smaller than the upside. What you want to avoid is the opposite.

- A famous example of this going wrong was the Swiss National Bank de-peg in 2012. The SNB suddenly did the unthinkable. They stopped defending the price. CHF jumped and so EURCHF (the number of CHF per 1 EUR) dropped to new lows very fast. Clearly, this trade had horrific risk : reward asymmetry: you risked 30% to make 0.05%.

- Other strategies like naively selling options have the same result. You win a small amount of money each day and [then spectacularly blow up](https://www.tampabay.com/business/how-tampas-james-cordier-went-from-high-roller-to-youtube-apology-after-losing-150-million-20190206/) at some point down the line.

## 1. Capital and Position Sizing

The first thing you have to know is how much capital you are working with. Let’s say you have $100,000 deposited. This is your maximum trading capital. Your trading capital is not the leveraged amount. It is the amount of money you have deposited and can withdraw or lose.

1. Risk no more than 2% of one’s account balance on an individual trade and 
2. Risk no more than 8% of one’s account balance on a specific theme. 
3. No more than one in twenty trades are graded exceptional and allocated 5% of account balance risk

## 2. Stop Loss
A stop loss is a resting order, left with the broker, to automatically close your position if it reaches a certain price.

The valid concern with stop losses is that disreputable brokers look for a concentration of stops and then, when the market is close, whipsaw the price through the stop levels so that the clients ‘stop out’ and sell to the broker at a low rate before the market naturally comes back higher. This is referred to as ‘stop hunting’.

*Always have a pre-determined stop loss before you put on a trade*

### Price-based stops

1.  Use technical analysis to pick important levels (support, resistance, previous high/lows, moving averages etc.) as these provide clear exit and entry points on a trade.
    
2.  Ensure that the stop gives your trade enough room to breathe and reflects your timeframe and typical volatility of each pair. 
	- One simple technique is simply to look at your chosen chart - let’s say daily bars. And then look at previous trends and use the measuring tool. Those generally look something like this and then you just click and drag to measure.For example if we wanted to bet on a downtrend on the chart above we might look at the biggest retracement on the previous uptrend. That max drawdown was about 100 pips or just under 1%. So you’d want your stop to be able to withstand at least that. If market conditions have changed - for example if CVIX has risen - and daily ranges are now higher you should incorporate that. If you know a big event is coming up you might think about that, too. The human brain is a remarkable tool and the power of the eye-ball method is not to be dismissed. This is how most discretionary traders do it.
	- Look at the Average True Range (ATR). This attempts to capture the volatility of a pair, typically averaged over a number of sessions. It looks at three separate measures and takes the largest reading. Think of this as a moving average of how much a pair moves.
	- Professional traders tend to use standard deviation as a measure of volatility instead of ATR. There are advantages and disadvantages to both. Averages are useful but can be misleading when regimes switch (see above chart).
	- Once you have chosen a measure of volatility, stop distance can then be back-tested and optimised. For example does 2x ATR work best or 5x ATR for a given style and time horizon? 
	- Discretionary traders may still eye-ball the ATR or standard deviation to get a feeling for how it has changed over time and what ‘normal’ feels like for a chosen study period - daily, weekly, monthly etc. For example, below shows the daily move in EURUSD was around 60 pips before spiking to 140 pips in March. Conditions were clearly far more volatile in March. Accordingly, you would need to leave your stop further away in March and take a correspondingly smaller position size.
    
3.  Always pick your stop level first. Then use a calculator to determine the appropriate lot size for the position, based on the % of your account balance you wish to risk on the trade.

### Fundamental stops 

Used alongside - not instead of - price stops. If either breaks you’re out.

If you stop understanding why a product is going up or down and your fundamental thesis has been confirmed wrong, get out. For example, if you are long because you think the central bank is turning hawkish and AUDUSD is going to play catch up with rates … then you hear dovish noises from the central bank and the bond yields retrace lower and back in line with the currency - close your AUDUSD position. You already know your thesis was wrong. No need to give away more money to the market.

If you have some big upcoming data like Non Farm Payrolls that you know can move the market +/- 150 pips and you have no edge going into the release then many traders will take off or scale down their positions. They’ll go back into the positions when the data is out and the market has quietened down after fifteen minutes or so. This is a matter of some debate - many traders consider it a coin toss and argue you win some and lose some and it all averages out.

### Trailing stops

Trailing stops can also be used to ‘lock in’ profits. We looked at those before. As the trade moves in your favour (say up if you are long) the stop loss ratchets with it.

## 3. Entering a position

### Limit order

Use technical analysis to pick important levels (support, resistance, previous high/lows, moving averages etc.) as these provide clear exit and entry points on a trade.

Imagine the price is 1.1250 and the recent low is 1.1205. 

You might wish to leave a bid around 1.2010 to enter a long position, if the market reaches that price. This way you don’t need to sit at the computer and wait.

Again, typically traders will use tech analysis to identify attractive levels. Again - other traders will cluster with your orders. Just like the stop loss we need to bake that in. 

So this time if we know everyone is going to buy around the recent low of 1.1205 we might leave the take profit bit a little bit above there at 1.1210 to ensure it gets done. Sure it costs 5 more pips but how mad would you be if the low was 1.1207 and then it rallied a hundred points and you didn’t have the trade on?!

### Scaling 
Scaling in is one such technique. Let’s imagine that you think we are in a long-term bulltrend for AUDUSD but experiencing a brief retracement. You want to take a total position of 500,000 AUD and don’t have a strong view on the current price action.

You might therefore leave a series of five bids of 100,000. As the price moves lower each one gets hit. The nice thing about scaling in is it reduces pressure on you to pick the perfect level. Of course the risk is that not all your orders get hit before the price moves higher and you have to trade at-market.

### Pyramiding
Pyramiding is the second technique. Pyramiding is for take profits what a trailing stop loss is to regular stops. It is especially common for momentum traders.

Again let’s imagine we’re bullish AUDUSD and want to take a position of 500,000 AUD.

Here we add 100,000 when our first signal is reached. Then we add subsequent clips of 100,000 when the trade moves in our favour. We are waiting for confirmation that the move is correct.

Obviously this is quite nice as we humans love trading when it goes in our direction. However, the drawback is obvious: we haven’t had the full amount of risk on from the start of the trend.

## 4. Exiting a winning position

Let winners run. Just like stops you need to know in advance the level where you will close out at a profit. Then let the trade happen. Don’t override yourself and let emotions force you to take a small profit. A classic mistake to avoid.

The trader puts on a trade and it almost stops out before rebounding. As soon as it is slightly in the money they spook and cut out, instead of letting it run to their original take profit. Do not do this.

