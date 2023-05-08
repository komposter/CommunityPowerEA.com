---
layout: page
title: Anti-martingale
permalink: /docs/anti-martingale
---

# Anti-martingale

*(starting from v2.12)*

New type of exit in profit: instead of fixed TP or closing by opposite signal, EA will open new deals in the same direction, but on the profit side. After each new deal is opened, SL is moved to the new level.

<hr>

## Anti-martingale type

Type of anti-martingale strategy used. Can be enabled or disabled.


## Max trades

Max anti-martingale deals in series.


## Min pause between trades (in bars of Signal TF)

*(starting from v2.52)*

Anti-martingale deal can be opened only if previous trade in this direction was opened at least **Min pause bars** before (bars from **Signal TimeFrame** are used).

Set 0 to disable this filter.


## Use martingale signal for anti-martin trades

*(starting from v2.52)*

If **true**, anti-martingale trades can be opened only on signals with **Open martin on...** enabled.


## Lot increasing mode

*(starting from v2.20)*

Can be one of the following:<br/>
* **Sum**: previous lot + adding [1-2-3-4-5-...]<br/>
* **Fibo**: previous lot + pre-previous lot [1-1-2-3-5-8-...]<br/>
* **Martin**: previous lot * coeff [1-2-4-8-16-...]<br/>
* **Martin Sum** *(starting from v2.29)*: previous lots sum * coeff [1-2-6-18-54-...]<br/>
* **Logistic Growth** *(starting from v2.30)*: lot is calculated using [logistic growth formula](https://communitypowerea.userecho.com/en/communities/1/topics/199-smart-risk-limitation-of-martingale-by-logistic-growth) (between Start Lot and Max Lot with average size at order x0, where x0 is specified by parameter "Lot coefficient / adding / x0")<br/>
* **Soft Martin** *(starting from v2.32)*: previous lot * coeff - previous lot [1-1-2-4-8-...] ([details are here](https://communitypowerea.userecho.com/en/communities/1/topics/318-position-cutter-pc-reduce-the-lot-size-by-previous-lot-size-in-the-sequence))<br/>
* **Custom lot coefficients** *(starting from v2.33)*: user-defined coefficient sequence (see **Custom lot coefficients** parameter below)<br/>


## Lot coefficient / adding / x0

Lot coefficient / adding / x0 for 2nd and next deals lot calculation.


## Custom lot coefficients

*(starting from v2.33)*

User-defined coefficient sequence for **Custom lot coefficients** increasing mode. Coefficients should be separated by comma. Max allowed string length - 63 symbols.

For example: sequence "1.0,2.0,3.0" with start lot 0.1 will cause a series with lots: 0.1 (first deal) - 0.1 - 0.2 - 0.3 - 0.3 - 0.3 - ...


## Step size

Step size (in points or like coefficient to Volatility)


## Step size calc mode

*(starting from v2.31)*

Step can be set:
* **In points** ([What is a "point" in CP?](https://communitypowerea.userecho.com/en/communities/7/topics/384-what-is-a-point-in-cp-what-does-stoploss-250-points-mean))
* Like **Coefficient to Volatility** ([volatility parameters](https://docs.google.com/document/d/1ww1M97H54IBwtCKZDhxtqsTsrtEMKofXHMEWMGCyZNs/edit#heading=h.sx27nza3heuj) must be set correctly)


## Step increase coefficient

Step increase coefficient for 2nd and all next martingale deals.<br/>
For example, with **Step size** = 20 points and **Step increase coefficient** = 1.5, distances between orders in martingale series will be 20 - 30 - 45 - 68 and so on


## Min step size (points)

*(starting from v2.29)*

Minimum step size (in points) ([What is a "point" in CP?](https://communitypowerea.userecho.com/en/communities/7/topics/384-what-is-a-point-in-cp-what-does-stoploss-250-points-mean)).<br/>
Calculated step can’t be smaller than the Min step size value.

<hr>

# Anti-StopLoss

## Anti-StopLoss size

StopLoss applies to the series after the anti-martingale strategy is activated (2nd order in series is opened).
Can be negative (when calculated from average price) (starting from v2.20)


## Anti-StopLoss reduce size, Anti-StopLoss reduce coefficient and Min Anti-StopLoss size

*(starting from v2.20)*

Anti-StopLoss reduce size and coefficient.
If enabled, SL for each next anti-martingale order in the series will be reduced by specified **reduce size**. This size will be also multiplied by **reduce coefficient** for each next stage too.

For example, with Anti-StopLoss = 50, reduce size = 10 and reduce coeff = 1.1 you will have the following series:<br/>
* For the 1st deal SL will be = 50 points<br/>
* For 2 deals: 50 - 10 = 40<br/>
* For 3 deals: 50 - 10*1.1 = 29<br/>
* For 4 deals: 50 - 10 - 10*1.1 - 10*1.1*1.1 = 16.9<br/>
* For 5 deals: 50 - 10 - 10*1.1 - 10*1.1*1.1 - 10*1.1*1.1*1.1 = 3.6<br/>
* And so on (-11 for 6 deals, -27.2 for 7 deals)<br/>

Anti-StopLoss can’t be less than **Min Anti-StopLoss size (points)** ([What is a "point" in CP?](https://communitypowerea.userecho.com/en/communities/7/topics/384-what-is-a-point-in-cp-what-does-stoploss-250-points-mean)).

For example, if you set **Min Anti-StopLoss size** = 20, for all deals from the last example, starting from 4th SL will be = 20 (16.9 is less than 20, so will be replaced).<br/>
**Anti-StopLoss size** can be negative.


## Anti-StopLoss mode

*(starting from v2.20)*

Anti-StopLoss mode:<br/>
* **From average open price**: SL based on weighted average open price of all positions in the series.<br/>
* **From last open price**: SL based on the open price of the last position in the series.<br/>
* **From first open price**: SL based on the open price of the first position in the series.


## Anti-StopLoss calc mode

*(starting from v2.31)*

Can be: <br/>
* **In points** ([What is a "point" in CP?](https://communitypowerea.userecho.com/en/communities/7/topics/384-what-is-a-point-in-cp-what-does-stoploss-250-points-mean))
* Like **Coefficient to Volatility** ([volatility parameters](https://docs.google.com/document/d/1ww1M97H54IBwtCKZDhxtqsTsrtEMKofXHMEWMGCyZNs/edit#heading=h.sx27nza3heuj) must be set correctly)


## Allow TakeProfit for anti-martin trades

*(starting from v2.37)*

Set **true** to enable simple TakeProfit for series with anti-martingale trade open.


<hr>

# Allow both Martin and Anti-martin

## Allow both Martin and Anti-martin

*(starting from v2.32)*

Set **true** to allow martingale deals if any anti-martingale deal is opened and vice versa.



