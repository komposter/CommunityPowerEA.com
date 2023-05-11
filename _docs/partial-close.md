---
layout: page
title: Partial close
permalink: /docs/partial-close
---

# Partial close

## Close partial after order # and Min profit to close (in account currency / in% from balance)

[*(starting from v2.20)*](/docs/versions-history#20201103-220)

Close some orders in the same direction (the last one and the first one, for example) if they sum profit is big enough (>= **Min profit to close**), the series is long enough (orders number >= **Close partial after order #**) and there is a signal for partial close (**Partial close on** parameter in each filter settings).

Min profit can be defined in account currency, in % from current balance [*(starting from v2.23)*](/docs/versions-history#20201210-223), or using both limits (greater will be taken into account).

Be careful, EA will reopen the last martingale order if the series is not totally closed, and lots will continue to increase. ([More info](https://communitypowerea.userecho.com/en/communities/1/topics/225-partial-close-of-martingale-trades-with-counter-trades-after-maximum-number-of-trades-are-reached))


## Min part of losing order to close (%)

*(starting from v2.32)*

Percent of losing order that can be closed with profit by Partial close.
For example, there are 2 deals opened:
1. buy-order 1.4 lots with profit +50
1. buy-order 1.2 lots with loss -80

With **Min profit to close** = 10 we can close only 50% (0.6 lots) of losing order, and have +50 - 40 = +10 total profit. So, if **Min part of losing order to close = 50% or less**, orders will be closed.

By default, only the entire order can be closed (**Min part of losing order to close** = 100%). Value of 0 also disables this function.


## Close any with any

*(starting from v2.44)*

Allows **partial close** to close orders with any direction (buy or sell).

If enabled, any number of profitable orders in any direction can be closed with the most losing order in any direction. Starts work when opened orders number >= **Close partial after order #**.

Same side closings (most losing buy with several profitable buys, for example) are still possible, if most losing buy is the most losing trade from all, and several profitable buys are most profitable trades.


## Close profit itself

*(starting from v2.46)*

Close only profitable orders on **Partial close on** signals even if profit is not big enough to cover the loss.

[Example](https://t.me/CommunityPowerNews/12)


<hr>


# ~~Partial close hedge (starting from v2.32)~~ **Removed in 2.50**

## ~~Close partial after order #, Min profit to close (in account currency / in% from balance / in % from opposite loss)~~

~~Close some opposite direction orders (the last buy and the first sell, for example) if they sum profit is big enough (>= Min profit to close) and the series is long enough (orders number >= Close partial after order #).~~

~~Min profit can be defined in account currency, in % from current balance, in % from opposite order loss, or using all 3 limits (greater will be taken into account).~~


## ~~Close main series by opposite main series~~

~~*(starting from v2.36)*~~

~~Allow partial close of opposite main series with total profit (all other partial close parameters also work for this mode)~~


## ~~Allow close both ways~~

~~**False**: close a winning order from a series with fewer orders with losing orders from a series with more orders.~~
~~**True**: allow close both ways (profitable order from a series with more orders with losing orders from a series with fewer orders, as well).~~


## ~~Max profitable orders to close~~

~~Max number of profitable orders that can be used for partial close hedge. Set 0 to disable this limit.~~


## ~~Min part of losing order to close (%)~~

~~Percent of losing order that can be closed with profit by Partial close.~~

~~The same as for Partial close of one-side orders.~~




