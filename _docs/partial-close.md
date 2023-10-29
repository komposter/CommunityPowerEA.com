---
layout: page
title: Partial close
permalink: /docs/partial-close
---

# Partial close
<sup>[*(starting from v2.20)*](/docs/versions-history#20201103-220)</sup>

Close some orders in the same direction (the last one and the first one, for example) if they sum profit is big enough (>= **Min profit to close**), the series is long enough (orders number >= **Close partial after order #**) and there is a signal for partial close (**Partial close on** parameter in each filter settings).

Min profit can be defined in account currency, in % from current balance [*(starting from v2.23)*](/docs/versions-history#20201210-223), or using both limits (greater will be taken into account).

Be careful, EA will reopen the last martingale order if the series is not totally closed, and lots will continue to increase.

[Initial discussion is here](https://communitypowerea.userecho.com/en/communities/1/topics/225-partial-close-of-martingale-trades-with-counter-trades-after-maximum-number-of-trades-are-reached).

<br />

### Close partial after order #

Min number of orders in series to start partial close.

Set 0 to disable partial close.

<br />

### Min profit to close

Min profit (in account currency / in% from balance) to close part of orders in series.

<br />

### Min part of losing order to close (%)
<sup>[*(starting from v2.32)*](/docs/versions-history#20210605-232)</sup>

Percent of losing order that can be closed with profit by Partial close.
> For example, there are 2 deals opened:
1. buy-order 1.4 lots with profit +50
2. buy-order 1.2 lots with loss -80
<br />With **Min profit to close** = 10 we can close only 50% (0.6 lots) of losing order, and have +50 - 40 = +10 total profit. So, if **Min part of losing order to close = 50% or less**, orders will be closed.

By default, only the entire order can be closed (**Min part of losing order to close** = 100%). Value of 0 also disables this function.

<br />

### Close any with any
<sup>[*(starting from v2.44)*](/docs/versions-history#20220312-244)</sup>

Allows **partial close** to close orders with any direction (buy or sell).

If enabled, any number of profitable orders in any direction can be closed with the most losing order in any direction. Starts work when opened orders number >= **Close partial after order #**.

Same side closings (most losing buy with several profitable buys, for example) are still possible, if most losing buy is the most losing trade from all, and several profitable buys are most profitable trades.

<br />

### Close profit itself
<sup>[*(starting from v2.46)*](/docs/versions-history#20220428-246)</sup>

Close only profitable orders on **Partial close on** signals even if profit is not big enough to cover the loss.

![partial_close.jpg](..%2Fassets%2Fimg%2Fdocs%2Fpartial_close.jpg)

<br />

### Sort By Profit
<sup>[*(starting from v2.55)*](/docs/versions-history#20230720-0818-255)</sup>

If **true**, orders are sorted by profit before partial close. So, the most profitable orders will be closed with the most losing ones.

If **false**, orders are sorted by opening time before partial close. So, the oldest orders will be closed with the newest ones.

<br />

### ActivePeriod

<sup>[*(starting from v2.56)*](/docs/versions-history#20230818-1025-256)</sup>

Partial close can be done only during the specified ActivePeriods.

Each of 4 Active periods can be set in the [Active Periods for signals and filters](/docs/active-periods) section.

In the 'Any with any' mode, active period should be active for one of the directions (buy or sell).

> For example, if you set 'Activate after trades number >= 3', Partial close 'any with any' will be active if there are 3 buy or 3 sell orders opened.

<br />
<br />

# ~~Partial close hedge~~

<sup>[**(removed in 2.50)**](/docs/versions-history#20221014-20230107-250)</sup>


