---
layout: page
title: Individual follow-up
permalink: /docs/individual-follow-up
---

# Individual StopLoss

<sup>[*(starting from v2.56)*](/docs/versions-history#20230818-1124-256)</sup>
<sup>[*(refactored in v2.60)*](/docs/versions-history#20240428-0903-260)</sup>

Individual StopLoss is set for each position right after opening.

It is always "real" (not virtual, even if [Use Virtual SL](/docs/follow-up#use-virtual-stoploss) is enabled).

{% include alert.html type="warning" title="Warning" content="Order closed by SL can be immediately reopened (if it is a martingale order and all conditions for opening are met)" %}

<br />

### StopLoss type

Can be one of the following:
* **StopLoss disabled**
* **Fixed StopLoss**: Fixed StopLoss in points ([what is a "point"?](/docs/FAQ/what-is-a-point))
* **StopLoss on extremum**: SL is set on the highest high or lowest low of the last **StopLoss Extremum Bars** bars, shifted by **StopLoss size / shift / coeff** points 
* **Donchian StopLoss**: SL is set on the Donchian channel, calculated with the **Donchian Signal Period** and **Donchian OpenShift Bars L/R** parameters, shifted by **StopLoss size / shift / coeff** points

<br />

### StopLoss size / shift / coeff

Individual StopLoss size or shift in points ([what is a "point"?](/docs/FAQ/what-is-a-point)).

<br />

### StopLoss TimeFrame

TimeFrame for Extremum bars and Donchian channel calculation.

<br />

### StopLoss Extremum Bars

Number of bars for Extremum calculation.

<br />

### Donchian Signal Period, OpenShift Bars L/R

Donchian channel parameters.

<br />

### Min StopLoss size

Min StopLoss size in points ([what is a "point"?](/docs/FAQ/what-is-a-point)).

If the calculated SL is less than **Min StopLoss size**, it will be set to **Min StopLoss size**.

<br />
<br />

# Individual TakeProfit

<sup>[*(starting from v2.56)*](/docs/versions-history#20230818-1124-256)</sup>
<sup>[*(refactored in v2.60)*](/docs/versions-history#20240428-0903-260)</sup>
<sup>[*(refactored in v2.60.6)*](/docs/versions-history#20240915-1015-261)</sup>

Individual TakeProfit is set for each position right after opening.

It is always "real" (not virtual, even if [Use Virtual TP](/docs/follow-up#use-virtual-takeprofit) is enabled).

{% include alert.html type="warning" title="Warning" content="Order closed by TP can be immediately reopened (if all conditions for opening are met)" %}

<br />

### TakeProfit type

Can be one of the following:
* **TakeProfit disabled**
* **Fixed TakeProfit**: Fixed TakeProfit in points ([what is a "point"?](/docs/FAQ/what-is-a-point))
* **TakeProfit with coefficient to SL**: TP size is calculated as SL size multiplied by **TakeProfit size / shift / coeff**

<br />

### TakeProfit size / shift / coeff

Individual TakeProfit size in points ([what is a "point"?](/docs/FAQ/what-is-a-point)) or coefficient.

<br />
<br />

# Individual BreakEven

<sup>[*(starting from v2.54)*](/docs/versions-history#20230427-0706-254)</sup>

Individual BE can only move SL in profit direction, it is always real (not virtual) and it can be replaced by a group SL, if the last one is set at a better price (for example, by trailing stop).

{% include alert.html type="warning" title="Be careful" content="Order closed by BE can be immediately reopened (if it is a martingale order and all conditions for opening are met)" %}

<br />

### BreakEven after, BreakEven to

If the profit of order reaches **BreakEven after** points ([what is a "point"?](/docs/FAQ/what-is-a-point)), SL will be moved to the level "open price + **BreakEven to** points" (opposite for sells).

Thus, the order will be closed with profit of **BreakEven to** points.

<br />

### ActivePeriod

BreakEven can be **always active** or use 1 of 4 predefined periods.

Each of 4 Active periods can be set in the [Active Periods for signals and filters](/docs/active-periods) section.

BreakEven works only if it is active.

<br />
<br />

# Individual TrailingStop

<sup>[*(starting from v2.56)*](/docs/versions-history#20230818-1124-256)</sup>

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

<br />
<br />

# Apply to Anti-martin orders only
<sup>[*(starting from v2.56)*](/docs/versions-history#20230818-1124-256)</sup>

If **true**, BreakEven and TrailingStop will be applied only to Anti-martin orders.
