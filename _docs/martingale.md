---
layout: page
title: Martingale
permalink: /docs/martingale
---

# Martingale

## Martingale type

[*(starting from v2.01)*](/docs/versions-history#20200409-201)

Type of martingale strategy used. Can be enabled or disabled.


## Max trades in one direction

Max deals in series.


## New deal on the end of the bar only

*(starting from v2.20)*

If enabled, Step condition is checked using last bar Close price (+ current spread for buy-orders). So, only 1 trade per bar is allowed and all trades are opened on the beginning of the bar.


## Min pause between trades (in bars of Signal TF)

[*(starting from v2.18)*](/docs/versions-history#20200908-218)

Martingale deal can be opened only if previous trade in this direction was opened at least **Min pause bars** before (bars from **Signal TimeFrame** are used).

Set 0 to disable this filter.


## Use only opened trades for time filters

*(starting from v2.47)*

When true, **New deal on the end of the bar only** and **Min pause between trades** analyze only open positions.<br/>
When false, closed positions are taken into account as well (closed position may be opened later than opened one, for example after Partial close)


## Lot increasing mode

*(starting from v2.20)*

Can be one of the following:<br/>
* **Sum**: previous lot + adding [1-2-3-4-5-...]
* **Fibo**: previous lot + pre-previous lot [1-1-2-3-5-8-...]
* **Martin**: previous lot * coeff [1-2-4-8-16-...]
* **Martin Sum** *(starting from v2.29)*: previous lots sum * coeff [1-2-6-18-54-...]
* **Logistic Growth** *(starting from v2.30)*: lot is calculated using [logistic growth formula](https://communitypowerea.userecho.com/en/communities/1/topics/199-smart-risk-limitation-of-martingale-by-logistic-growth) (between Start Lot and Max Lot with average size at order x0, where x0 is specified by parameter “Lot coefficient / adding / x0”)
* **Soft Martin** *(starting from v2.32)*: previous lot * coeff - previous lot [1-1-2-4-8-...] ([details are here](https://communitypowerea.userecho.com/en/communities/1/topics/318-position-cutter-pc-reduce-the-lot-size-by-previous-lot-size-in-the-sequence))
* **Custom lot coefficients** *(starting from v2.33)*: user-defined coefficient sequence (see Custom lot coefficients parameter below)
* **1st deal lot * distance * coeff** *(starting from v2.50)*: lot calculated coefficient to 1st deal lot multiplied by distance between 1st entry price and current price. For EURUSD, coefficient values near 1000 have sense.


## Lot coefficient / adding / x0

Lot coefficient / adding / x0 for 2nd and next deals lot calculation.


## Custom lot coefficients

*(starting from v2.33)*

User-defined coefficient sequence for Custom lot coefficients increasing mode. Coefficients should be separated by comma. Max allowed string length — 63 symbols.

For example: sequence "1.0,2.0,3.0" with start lot 0.1 will cause a series with lots: 0.1 (first deal) - 0.1 - 0.2 - 0.3 - 0.3 - 0.3 - ...


## Step size

Step size (in points or like coefficient to Volatility)


## Step size calc mode

*(starting from v2.31)*

Step can be set:<br/>
* **In points** ([What is a "point" in CP?](https://communitypowerea.userecho.com/en/communities/7/topics/384-what-is-a-point-in-cp-what-does-stoploss-250-points-mean))
* Like **Coefficient to Volatility** ([volatility parameters](https://docs.google.com/document/d/1ww1M97H54IBwtCKZDhxtqsTsrtEMKofXHMEWMGCyZNs/edit#heading=h.sx27nza3heuj) must be set correctly)


## Step increase coefficient

Step increase coefficient for 2nd and all next martingale deals. <br/>
For example, with **Step size** = 20 points and **Step increase coefficient** = 1.5, distances between orders in martingale series will be 20 - 30 - 45 - 67.5 - 101.3 and so on


## Change step after order #, Change step by coefficient

*(starting from v2.46)*

Change the step after a certain order by custom coefficient (next steps also change).<br/>
For example, with **Step size** = 20 points, **Change step after order #** = 2 and **Change step by coefficient** = 2.0, distances between orders in martingale series will be 20 - 20 - 40 - 40 - 40 - 40 and so on.


## Custom step coefficients

*(starting from v2.36)*

Custom coefficients (comma separated) for 2nd and all next martingale deals. For example, with **Step size** = 20 points and **Custom step coefficients** = "1.5,2.5,5.0", distances between orders in martingale series will be 20 - 30 - 50 - 100 - 100 and so on (last coefficient applied to all following steps.

If both **Step increase coefficient** and **Custom step coefficients** are set, **Step increase coefficient** is applied first and then **Custom step coefficients** are applied. For example, with **Step size** = 20 points, **Step increase coefficient** = 1.5 and **Custom step coefficients** = "1.5,2.5,5.0", distances between orders in martingale series will be 20 - 45 - 112.5 - 337.5 - 506.5 and so on.

Set empty value to disable **Custom step coefficients**.


## Min step size (points)

*(starting from v2.29)*

Minimum step size (in points) ([What is a "point" in CP?](https://communitypowerea.userecho.com/en/communities/7/topics/384-what-is-a-point-in-cp-what-does-stoploss-250-points-mean)).<br/>
Calculated step can’t be smaller than the **Min step size** value.


## Max step size (points)

Maximum step size (in points)<br/>
Calculated step can’t be larger than the **Max step size** value.


<hr>

# Break even

## Close on BreakEven after order #

[*(starting from v2.18)*](/docs/versions-history#20200908-218)

Close all orders when your series containing a specified number of orders reaches Break Even.

For example, if **Close on BreakEven after order #** = 2, and if you have 2 or more deals opened in one direction, they will be closed as soon as they become profitable.

Set 0 to disable this function.


## BreakEven min profit

*(starting from v2.27)*

Min profit size to close series on BreakEven after order (in points) ([What is a "point" in CP?](https://communitypowerea.userecho.com/en/communities/7/topics/384-what-is-a-point-in-cp-what-does-stoploss-250-points-mean)).


## BreakEven Alert

[*(starting from v2.11)*](/docs/versions-history#20200528-211)

Send a message to Grammy when your series containing a specified number of orders reached Break Even. One alert for each series length.

For example, if **BreakEven Alert after order #** = 3, and if you have 3 or more deals opened in one direction, you’ll have a message as soon as these orders become profitable. You will not have a message if the opened series is shorter than 3 orders.

Set 0 to disable BreakEven alert.

<hr>

# Apply martin to the new deals

## Apply martin after closed loss

[*(starting from v2.07)*](/docs/versions-history#20200504-207)

Increase lot of the first deal of the new series (opened on signal) after loss is closed. EA will apply martingale till profit becomes positive.<br/>
To start again with a Start lot on account with loss, set new Magic number.

