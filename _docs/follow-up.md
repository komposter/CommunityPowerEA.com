---
layout: page
title: Follow up
permalink: /docs/follow-up
---

# Follow up

In this section you can set parameters that affect position management after it is opened.

<br />
<br />

# StopLoss

### StopLoss size

StopLoss for the last position in series (for the single position, if martingale disabled)

<br />

### StopLoss reduce every bar K, Start reducing after bars, StopLoss min size

<sup>[*(starting from v2.53)*](/docs/versions-history#20230412-0426-253)</sup>

Reduces SL size every bar of Signal TF by specified coefficient, starting from bar # **Start reducing after bars** after the 1st position open.

SL can't be less than **StopLoss min size (points)**.

> For example, with **StopLoss reduce every bar K = 0.95** and initial SL = 100 points, on the bar #2 after position open SL will be 100 * 0.95 = 95 points, on the bar #3 -- 100 * 0.95 * 0.95 = 90 points, and so on.

Set 0 to disable SL reducing

[Initial discussion is here](https://forum.communitypowerea.com/communities/1/topics/423-decrease-stop-loss-depending-on-trade-duration?redirect_to_reply=2763#comment-2763)

<br />

### StopLoss mode

<sup>[*(starting from v2.20)*](/docs/versions-history#20201103-220)</sup>

StopLoss mode:
* **From average open price** - SL based on weighted average open price of all positions in the series.
* **From last open price** - SL based on the open price of the last position in the series.
* **From first open price** - SL based on the open price of the first position in the series.

<br />

### StopLoss calc mode

StopLoss can be set:
* **In points** ([what is a "point"?](/docs/FAQ/what-is-a-point))
* Like **Coefficient to Volatility** ([volatility parameters](/docs/volatility) must be set correctly)

<br />

### Sum StopLoss in account currency

<sup>[*(starting from v2.23)*](/docs/versions-history#20201210-223)</sup>

Sum StopLoss for all positions opened by EA in account currency.

Set 0 to disable.

<br />

### Sum StopLoss (% from balance)

<sup>[*(starting from v2.07)*](/docs/versions-history#20200504-207)</sup>

Sum StopLoss for all positions opened by EA in % from current balance.

Set 0 to disable.

<br />

### PauseAfterLoss

<sup>[*(starting from v2.23)*](/docs/versions-history#20201210-223)</sup>

Disables opening new first trades after closing by StopLoss or GlobalStopLoss. Specifies in bars of Signal TimeFrame.

<br />

### Use virtual StopLoss

<sup>[*(starting from v2.27)*](/docs/versions-history#20210302-227)</sup>

Set **true** to close trades by market when SL level is reached.<br/>
Set **false** to set the real SL for all orders (if possible).

<br />
<br />

# TakeProfit

### TakeProfit size

TakeProfit size (In points or Like Coefficient to Volatility) (0 - disabled)

<br />

### TakeProfit mode

TakeProfit mode:
* **From average open price** - TP based on weighted average open price of all positions in the series (price1*lot1 + price2*lot2 + priceN*lotN)/(lot1 + lot2 + lotN).
* **From last open price** - TP based on the open price of the last position in the series.
* **From first open price** [*(starting from v2.20)*](/docs/versions-history#20201103-220) - TP based on the open price of the first position in the series.

Spread included. Sells are closed by Ask price. So, only when Ask became <= TP must trigger.

Commission and swap also included.

<br />

### TakeProfit calc mode

TakeProfit can be set:
* **In points** ([what is a "point"?](/docs/FAQ/what-is-a-point))<br/>
* Like **Coefficient to Volatility** ([volatility parameters](/docs/volatility) must be set correctly)

<br />

### Reduce TP after minutes, Reduce coefficient

<sup>[*(starting from v2.23)*](/docs/versions-history#20201210-223)</sup>

TakeProfit reduce coefficient for all orders. Activates after a certain number of minutes have passed since first order opening.

<br />

### Reduce TP for every order: Reduce size, Reduce coefficient, Min TakeProfit size

<sup>[*(starting from v2.11)*](/docs/versions-history#20200528-211)</sup>

TakeProfit reduce size and coefficient for every order in series.

If enabled, TP for each next order in the series will be reduced by specified **reduce size**. This size will be also multiplied by **reduce coefficient** for each next stage too.

> For example, with TakeProfit = 50, reduce size = 10 and reduce coeff = 1.1 you will have the following series:
* For the 1st deal TP will be = 50 points
* For 2 deals: 50 - 10 = 40
* For 3 deals: 50 - 10 - 10 * 1.1 = 29
* For 4 deals: 50 - 10 - 10 * 1.1 - 10 * 1.1 * 1.1 = 16.9
* For 5 deals: 50 - 10 - 10 * 1.1 - 10 * 1.1 * 1.1 - 10 * 1.1 * 1.1 * 1.1 = 3.6
* And so on (-11 for 6 deals, -27.2 for 7 deals)

<br />

TakeProfit can't be less than **Min TakeProfit size (points)** ([what is a "point"?](/docs/FAQ/what-is-a-point)).

> For example, if you set **Min TakeProfit size** = 20, for all deals from the last example, starting from 4th TP will be = 20 (16.9 is less than 20, so will be replaced).

**Min TakeProfit size** can be negative. So, you can limit it to -5 or -20 points.

<br />

### Sum TakeProfit (% from balance)

<sup>[*(starting from v2.17)*](/docs/versions-history#20200826-217)</sup>

Sum TakeProfit for all positions opened by EA in % from current balance.

Set 0 to disable.

<br />

### Sum TakeProfit (account currency)

<sup>[*(starting from v2.35)*](/docs/versions-history#20210715-235)</sup>

Sum TakeProfit for all positions opened by EA in account currency.

Set 0 to disable.

<br />

### Sum TakeProfit works if both buy and sell are open

<sup>[*(starting from v2.35)*](/docs/versions-history#20210715-235)</sup>

Set this parameter to true to activate Sum TakeProfit if both buy and sell trades are opened.

<br />

### Min profit to close on signal

<sup>[*(starting from v2.20)*](/docs/versions-history#20201103-220)</sup>

When you select **Close in profit only** mode for any signal, it will close the series with profit >= X only.

<br />

### Max profit to close on signal

<sup>[*(starting from v2.52)*](/docs/versions-history#20230211-0324-252)</sup>

When you select **Close in profit only** mode for any signal, it will close the series with profit <= X only.

<br />

### Min/max profit calc mode

Min/max profit can be set:
* **In points** ([what is a "point"?](/docs/FAQ/what-is-a-point))
* Like **Coefficient to Volatility** ([volatility parameters](/docs/volatility) must be set correctly)

<br />

### Use virtual TakeProfit

<sup>[*(starting from v2.27)*](/docs/versions-history#20210302-227)</sup>

Set **true** to close trades by market when TP level is reached.

Set **false** to set the real TP for all orders (if possible).

<br />
<br />

# BreakEven

<sup>[*(starting from v2.49)*](/docs/versions-history#20221007-249)</sup>


### BreakEven after, BreakEven to

If the profit of a series reaches **BreakEven after** points ([what is a "point"?](/docs/FAQ/what-is-a-point)), SL of all positions will be moved to the level "average open price + **BreakEven** to points" (opposite for sell).

Thus, the series will be closed with profit of **BreakEven to** points.

<br />

### BreakEven calc mode

BreakEven can be set:
* **In points** ([what is a "point"?](/docs/FAQ/what-is-a-point))
* Like **Coefficient to Volatility** ([volatility parameters](/docs/volatility) must be set correctly)


<br />
<br />

# TrailingStop


### TrailingStop size

Trailing stop size (0 - disabled)

<br />

### Trailing Step

<sup>[*(starting from v2.16)*](/docs/versions-history#20200819-216)</sup>

Minimal step to move the StopLoss

<br />

### Start trailing after

Trailing activated after profit = **Start trailing after**.<br/>
If 0, trailing activated after profit = **Trailing stop size**.

<br />

### Increase trailing every, Increase size

<sup>[*(starting from v2.45)*](/docs/versions-history#20220421-245)</sup>

If **Increase trailing every** > 0, Trailing stop size changes by **Increase size** every **Increase trailing every** (points or volatilities, see below).

> For example, if **TrailingStop size** = 5.0, **Increase every** = 2.0 and **Increase size** = -1.0:
* if profit <= 7.0, TrailingStop distance = 5.0
* if profit >= 7.0 and < 9.0, TrailingStop distance = 5.0 + (-1.0) = 4.0
* if profit >= 9.0 and < 11.0, TrailingStop distance = 5.0 + (-1.0) + (-1.0) = 3.0 and so on…<br />
As you can see, **Increase size** can be negative.

<br />

### Decrease every minutes, Decrease coefficient, Decrease start after minutes

<sup>[*(starting from v2.46)*](/docs/versions-history#20220428-246)</sup>

After **Decrease start after minutes** after first position open, TrailingStop size increases/decreases by **Decrease coefficient** every **Decrease every minutes**.

> For example, with Initial Trailing Stop size 50 points:
* after 30 minutes it will be 50 * 0.9 = 45 points
* after 35 minutes it will be 50 * 0.9 * 0.9 = 40.5 points
* after 40 minutes it will be 50 * 0.9 * 0.9 * 0.9 = 36.5 points
* ...
* after 60 minutes it will be 50 * 0.9 * 0.9 * 0.9 * 0.9 * 0.9 * 0.9 * 0.9 = 23.9 points

Set **Decrease every minutes** = 0 to disable this function.

If both **Increase trailing every** and **Decrease every minutes** are activated, **Increase trailing every** is applied first.

[Initial discussion is here](https://communitypowerea.userecho.com/en/communities/1/topics/424-trailingstop-decrease-after-time)

<br />

### Min size, Max size

<sup>[*(starting from v2.46)*](/docs/versions-history#20220428-246)</sup>

If **Min/max size** is set, TrailingStop size after applying all modificators can't be less than **Min size** value and can't be greater than **Max size** value.

Set 0 to disable limits.

<br />

### TrailingStop mode

TrailingStop mode:
* **From average open price** - TS based on average open price of all positions in the series;
* **From last open price** - TS based on the open price of the last position in the series.
* **From first open price** [*(starting from v2.20)*](/docs/versions-history#20201103-220) - TS based on the open price of the first position in the series.

<br />

### TrailingStop calc mode

TrailingStop, TrailingStep, Start trailing after, Increase trailing every and Increase size can be set:
* **In points** ([what is a "point"?](/docs/FAQ/what-is-a-point))
* Like **Coefficient to Volatility** ([volatility parameters](/docs/volatility) must be set correctly)
