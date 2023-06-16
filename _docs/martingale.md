---
layout: page
title: Martingale
permalink: /docs/martingale
---

# Martingale

### Martingale type

<sup>[*(starting from v2.01)*](/docs/versions-history#20200409-201)</sup>

Type of martingale strategy used. Can be enabled or disabled.

<br />

### Max trades in one direction

Max deals in series.

<br />

### New deal on the end of the bar only

<sup>[*(starting from v2.20)*](/docs/versions-history#20201103-220)</sup>

If enabled, Step condition is checked using last bar Close price (+ current spread for buy-orders). So, only 1 trade per bar is allowed and all trades are opened on the beginning of the bar.

<br />

### Min pause between trades (in bars of Signal TF)

<sup>[*(starting from v2.18)*](/docs/versions-history#20200908-218)</sup>

Martingale deal can be opened only if previous trade in this direction was opened at least **Min pause bars** before (bars from **Signal TimeFrame** are used).

Set 0 to disable this filter.

<br />

### Use only opened trades for time filters

<sup>[*(starting from v2.47)*](/docs/versions-history#20220520-247)</sup>

When true, **New deal on the end of the bar only** and **Min pause between trades** analyze only open positions.<br/>
When false, closed positions are taken into account as well (closed position may be opened later than opened one, for example after Partial close)


### Lot increasing mode

<sup>[*(starting from v2.20)*](/docs/versions-history#20201103-220)</sup>

Can be one of the following:<br/>
* **Sum**: previous lot + adding [1-2-3-4-5-...]
* **Fibo**: previous lot + pre-previous lot [1-1-2-3-5-8-...]
* **Martin**: previous lot * coeff [1-2-4-8-16-...]
* **Martin Sum** [*(starting from v2.29)*](/docs/versions-history#20210403-229): previous lots sum * coeff [1-2-6-18-54-...]
* **Logistic Growth** [*(starting from v2.30)*](/docs/versions-history#20210419-230): lot is calculated using [logistic growth formula](https://communitypowerea.userecho.com/en/communities/1/topics/199-smart-risk-limitation-of-martingale-by-logistic-growth) (between Start Lot and Max Lot with average size at order x0, where x0 is specified by parameter “Lot coefficient / adding / x0”)
* **Soft Martin** [*(starting from v2.32)*](/docs/versions-history#20210605-232): previous lot * coeff - previous lot [1-1-2-4-8-...] ([Initial discussion is here](https://communitypowerea.userecho.com/en/communities/1/topics/318-position-cutter-pc-reduce-the-lot-size-by-previous-lot-size-in-the-sequence))
* **Custom lot coefficients** [*(starting from v2.33)*](/docs/versions-history#20210610-233): user-defined coefficient sequence (see Custom lot coefficients parameter below)
* **1st deal lot * distance * coeff** [*(starting from v2.50)*](/docs/versions-history#20221014-20230107-250): lot calculated coefficient to 1st deal lot multiplied by distance between 1st entry price and current price. For EURUSD, coefficient values near 1000 have sense.


### Lot coefficient / adding / x0

Lot coefficient / adding / x0 for 2nd and next deals lot calculation.


### Custom lot coefficients

<sup>[*(starting from v2.33)*](/docs/versions-history#20210610-233)</sup>

User-defined coefficient sequence for Custom lot coefficients increasing mode. Coefficients should be separated by comma. Max allowed string length — 63 symbols.

> For example: sequence "1.0,2.0,3.0" with start lot 0.1 will cause a series with lots: 0.1 (first deal) - 0.1 - 0.2 - 0.3 - 0.3 - 0.3 - ...


### Step size

Step size (in points or like coefficient to Volatility)


### Step size calc mode

<sup>[*(starting from v2.31)*](/docs/versions-history#20210508-231)</sup>

Step can be set:<br/>
* **In points** ([What is a "point" in CP?](/docs/FAQ/what-is-a-point))
* Like **Coefficient to Volatility** ([volatility parameters](/docs/volatility) must be set correctly)


### Step increase coefficient

Step increase coefficient for 2nd and all next martingale deals.

> For example, with **Step size** = 20 points and **Step increase coefficient** = 1.5, distances between orders in martingale series will be 20 - 30 - 45 - 67.5 - 101.3 and so on


### Change step after order #, Change step by coefficient

<sup>[*(starting from v2.46)*](/docs/versions-history#20220428-246)</sup>

Change the step after a certain order by custom coefficient (next steps also change).
> For example, with **Step size** = 20 points, **Change step after order #** = 2 and **Change step by coefficient** = 2.0, distances between orders in martingale series will be 20 - 20 - 40 - 40 - 40 - 40 and so on.


### Custom step coefficients

<sup>[*(starting from v2.36)*](/docs/versions-history#20210804-236)</sup>

Custom coefficients (comma separated) for 2nd and all next martingale deals. For example, with **Step size** = 20 points and **Custom step coefficients** = "1.5,2.5,5.0", distances between orders in martingale series will be 20 - 30 - 50 - 100 - 100 and so on (last coefficient applied to all following steps.

If both **Step increase coefficient** and **Custom step coefficients** are set, **Step increase coefficient** is applied first and then **Custom step coefficients** are applied. For example, with **Step size** = 20 points, **Step increase coefficient** = 1.5 and **Custom step coefficients** = "1.5,2.5,5.0", distances between orders in martingale series will be 20 - 45 - 112.5 - 337.5 - 506.5 and so on.

Set empty value to disable **Custom step coefficients**.


### Min step size (points)

<sup>[*(starting from v2.29)*](/docs/versions-history#20210403-229)</sup>

Minimum step size (in points) ([What is a "point" in CP?](/docs/FAQ/what-is-a-point)).<br/>
Calculated step can't be smaller than the **Min step size** value.


### Max step size (points)

Maximum step size (in points)<br/>
Calculated step can't be larger than the **Max step size** value.


<br />

# Break even

### Close on BreakEven after order #

<sup>[*(starting from v2.18)*](/docs/versions-history#20200908-218)</sup>

Close all orders when your series containing a specified number of orders reaches Break Even.

> For example, if **Close on BreakEven after order #** = 2, and if you have 2 or more deals opened in one direction, they will be closed as soon as they become profitable.

Set 0 to disable this function.


### BreakEven min profit

<sup>[*(starting from v2.27)*](/docs/versions-history#20210302-227)</sup>

Min profit size to close series on BreakEven after order (in points) ([What is a "point" in CP?](/docs/FAQ/what-is-a-point)).


### BreakEven Alert

<sup>[*(starting from v2.11)*](/docs/versions-history#20200528-211)</sup>

Send a message to Grammy when your series containing a specified number of orders reached Break Even. One alert for each series length.

> For example, if **BreakEven Alert after order #** = 3, and if you have 3 or more deals opened in one direction, you’ll have a message as soon as these orders become profitable. You will not have a message if the opened series is shorter than 3 orders.

Set 0 to disable BreakEven alert.


<br />

# Apply martin to the new deals

### Apply martin after closed loss

<sup>[*(starting from v2.07)*](/docs/versions-history#20200504-207)</sup>

Increase lot of the first deal of the new series (opened on signal) after loss is closed. EA will apply martingale till profit becomes positive.<br/>
To start again with a Start lot on account with loss, set new Magic number.

