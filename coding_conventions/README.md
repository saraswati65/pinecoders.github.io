
//@version=5
indicator("Custom Buy Sell Signal", overlay=true)

ema50 = ta.ema(close, 50)
rsi = ta.rsi(close, 14)
[macdLine, signalLine, _] = ta.macd(close, 12, 26, 9)

buy = ta.crossover(macdLine, signalLine) and close > ema50 and rsi > 50
sell = ta.crossunder(macdLine, signalLine) and close < ema50 and rsi < 50

plotshape(buy, title="Buy Signal", location=location.belowbar, color=color.green, style=shape.labelup, text="BUY")
plotshape(sell, title="Sell Signal", location=location.abovebar, color=color.red, style=shape.labeldown, text="SELL")
[<img src="https://www.pinecoders.com/images/PineCodersLong.png">](https://www.pinecoders.com/)

Our original Pine Script Coding Conventions now live in the [Style guide](https://www.tradingview.com/pine-script-docs/en/v5/writing/Style_guide.html) page of the Pine User Manual.
