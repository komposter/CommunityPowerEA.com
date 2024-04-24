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

| Server | Login | Password         |
| --- | --- |------------------|
| ICMarketsSC-MT5-2 | 7104388 | CommunityPower1  |
| liveUK-mt5.darwinex.com | 4000031968 | CommunityPower1! |
| BlueberryMarkets-Live | 46293 | CommunityPower1  |
| OctaFX-Real | 63078017 | CommunityPower1! |

<br />

### Modelling mode
If you don't use sensitive order management features like TrailingStop and BreakEven, and your StopLoss, TakeProfit and Martingale Step sizes are bigger than average M5 bar, you can use “**1 minute OHLC**” mode.

In all other cases I recommend to use “**Every tick based on real ticks**” mode. It is slower, but more accurate.

You can always compare results of both modes and choose the best one for your case.

<br />

### History quality
Quality of the history depends on the broker.

If broker provides all real ticks, quality is 100%. If there are some gaps in the history, quality is lower.

Backtest the EA only on the broker you want to trade with. Different brokers have different quotes history!