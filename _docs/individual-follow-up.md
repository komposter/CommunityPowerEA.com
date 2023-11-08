---
layout: page
title: Individual follow-up
permalink: /docs/individual-follow-up
---

# Individual StopLoss

<sup>[*(starting from v2.56)*](/docs/versions-history#20230818-1025-256)</sup>

Individual StopLoss is set for each position right after opening (if [Use Virtual SL](/docs/follow-up#use-virtual-stoploss) is disabled) or checked on each tick (if Use Virtual SL is enabled).

{% include alert.html type="warning" title="Be careful" content="Order closed by SL can be immediately reopened (if it is a martingale order and all conditions for opening are met)" %}

<br />

### StopLoss size

Individual StopLoss size (in points or Like Coefficient to Volatility).

Set 0 to disable StopLoss.

<br />

### StopLoss calc mode

StopLoss can be set:
* **In points** ([what is a "point"?](/docs/FAQ/what-is-a-point))
* Like **Coefficient to Volatility** ([volatility parameters](/docs/volatility) must be set correctly)

<br />
<br />

# Individual TakeProfit

<sup>[*(starting from v2.56)*](/docs/versions-history#20230818-1025-256)</sup>

Individual TakeProfit is set for each position right after opening (if [Use Virtual TP](/docs/follow-up#use-virtual-takeprofit) is disabled) or checked on each tick (if Use Virtual TP is enabled).

<br />

### TakeProfit size

Individual TakeProfit size (in points or Like Coefficient to Volatility).

Set 0 to disable TakeProfit.

<br />

### TakeProfit calc mode

TakeProfit can be set:
* **In points** ([what is a "point"?](/docs/FAQ/what-is-a-point))
* Like **Coefficient to Volatility** ([volatility parameters](/docs/volatility) must be set correctly)

<br />
<br />

# Individual BreakEven

<sup>[*(starting from v2.54)*](/docs/versions-history#20230427-0706-254)</sup>

Individual BE can only move SL in profit direction, it is always real (not virtual) and it can be replaced by a group SL, if the last one is set at a better price (for example, by trailing stop).

{% include alert.html type="warning" title="Be careful" content="Order closed by BE can be immediately reopened (if it is a martingale order and all conditions for opening are met)" %}

<br />

### BreakEven after, BreakEven to

If the profit of order reaches **BreakEven after** points ([what is a "point"?](/docs/FAQ/what-is-a-point)), SL will be moved to the level "open price + **BreakEven** to points" (opposite for sell).

Thus, the order will be closed with profit of **BreakEven to** points.

<br />

### ActivePeriod

BreakEven can be **always active** or use 1 of 4 predefined periods.

Each of 4 Active periods can be set in the [Active Periods for signals and filters](/docs/active-periods) section.

BreakEven works only if it is active.

<br />

### Apply to Anti-martin orders only
<sup>[*(starting from v2.56)*](/docs/versions-history#20230818-1025-256)</sup>

If **true**, BreakEven will be applied only to Anti-martin orders.

<br />
<br />

# Individual TrailingStop

<sup>[*(starting from v2.56)*](/docs/versions-history#20230818-1025-256)</sup>

Individual TrailingStop can only move SL in profit direction, it is always real (not virtual) and it can be replaced by a group SL, if the last one is set at a better price (for example, by trailing stop).

{% include alert.html type="warning" title="Be careful" content="Order closed by TrailingStop can be immediately reopened (if it is a martingale order and all conditions for opening are met)" %}

<br />

### TrailingStop size

Individual TrailingStop size in points ([what is a "point"?](/docs/FAQ/what-is-a-point)).

Set 0 to disable TrailingStop.

<br />

### Min profit to protect

TrailingStop will move SL only to the level where profit is more than **Min profit to protect** points.

> For example, if **TrailingStop size** = 20 points and **Min profit to protect** = 10 points, SL will be moved if profit is more than 30 points (SL will protect 10 points of profit).

Set 0 to make first modification of SL to the level of position open price.

<br />

### Trailing step

Trailing step in points ([what is a "point"?](/docs/FAQ/what-is-a-point)).

SL can be moved by at least **Trailing step** points.

<br />

### ActivePeriod

TrailingStop can be **always active** or use 1 of 4 predefined periods.

Each of 4 Active periods can be set in the [Active Periods for signals and filters](/docs/active-periods) section.

TrailingStop works only if it is active.
