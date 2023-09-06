---
layout: page
title: Individual follow-up
permalink: /docs/individual-follow-up
---

# Individual StopLoss

<sup>[*(starting from v2.55.2)*](/docs/versions-history#20230818-0905-2552)</sup>

Individual StopLoss is set for each position right after opening (if [Use Virtual SL](/docs/follow-up#use-virtual-stoploss) is disabled) or checked on each tick (if Use Virtual SL is enabled).

{% include alert.html type="warning" title="Be careful" content="Order closed by SL can be immediately reopened (if it is a martingale order and all conditions for opening are met)" %}

<br />

### StopLoss size

StopLoss size (in points or Like Coefficient to Volatility).

Set 0 to disable StopLoss.

<br />

### StopLoss calc mode

StopLoss can be set:
* **In points** ([what is a "point"?](/docs/FAQ/what-is-a-point))
* Like **Coefficient to Volatility** ([volatility parameters](/docs/volatility) must be set correctly)

<br />


# Individual TakeProfit

<sup>[*(starting from v2.55.2)*](/docs/versions-history#20230818-0905-2552)</sup>

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
