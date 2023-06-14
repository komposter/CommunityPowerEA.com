---
layout: page
title: Backtesting and optimization
permalink: /backtesting-and-optimization/
---

# Backtesting and optimization

{% include alert.html type="warning" 
title="Please, do all your tests in the MetaTrader 5!" 
content="There are full ticks history available “from the box”, no “synchronization errors” and powerful multithreaded optimization in MetaTrader 5." %}

To test the EA, connect your MT5 to the broker you want to trade with (different brokers have different quotes history!), open StrategyTester, select symbol, time interval, modeling mode, adjust EA settings and press the Start button.

Here are some **live** account credentials for your backtesting:

| Server | Login | Password |
| --- | --- | --- |
| ICMarketsSC-MT5 | 5018202 | CommunityPower1 |
| liveUK-mt5.darwinex.com | 4000002776 | CommunityPower1 |
| BlueberryMarkets-Live | 46293 | CommunityPower1 |


### Modelling mode
 - If TrailingStop and BreakEven disabled, and StopLoss/TakeProfit/Step size are bigger than average M5 bar, you can use “**1 minute OHLC**” mode,
 - Otherwise, please use “**Every tick based on real ticks**” mode.

### History quality
Quality of the history depends on the broker.

If broker provides all real ticks, quality is 100%. If there are some gaps in the history, quality is lower.

Backtest the EA only on 