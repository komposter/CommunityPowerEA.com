---
layout: page
title: Anti-martingale
permalink: /docs/anti-martingale
---

# Anti-martingale

<sup>[*(starting from v2.12)*](/docs/versions-history#20200624-212)</sup>

Anti-martingale means opening new deals in the same direction, but on the profit side.

After each new deal is opened, SL is moved to the new level.

<br />

### Anti-martingale type

Type of anti-martingale strategy used. Can be enabled or disabled.

<br />

### Max trades

Max anti-martingale deals in series.

<br />

### Min pause between trades (in bars of Signal TF)

<sup>[*(starting from v2.52)*](/docs/versions-history#20230211-0324-252)</sup>

Anti-martingale deal can be opened only if previous trade in this direction was opened at least **Min pause bars** before (bars from **Signal TimeFrame** are used).

Set 0 to disable this filter.

<br />

### Use martingale signal for anti-martin trades

<sup>[*(starting from v2.52)*](/docs/versions-history#20230211-0324-252)</sup>

If **true**, anti-martingale trades can be opened only on signals with **Open martin on...** enabled.

<br />

### Lot increasing mode

<sup>[*(starting from v2.20)*](/docs/versions-history#20201103-220)</sup>

Can be one of the following:
* **Sum**: previous lot + adding [1-2-3-4-5-...]
* **Fibo**: previous lot + pre-previous lot [1-1-2-3-5-8-...]
* **Martin**: previous lot * coeff [1-2-4-8-16-...]
* **Martin Sum** [*(starting from v2.29)*](/docs/versions-history#20210403-229): previous lots sum * coeff [1-2-6-18-54-...]
* **Logistic Growth** [*(starting from v2.30)*](/docs/versions-history#20210419-230): lot is calculated using [logistic growth formula](https://communitypowerea.userecho.com/en/communities/1/topics/199-smart-risk-limitation-of-martingale-by-logistic-growth) (between Start Lot and Max Lot with average size at order x0, where x0 is specified by parameter "Lot coefficient / adding / x0")
* **Soft Martin** [*(starting from v2.32)*](/docs/versions-history#20210605-232): previous lot * coeff - previous lot [1-1-2-4-8-...] ([Initial discussion is here](https://communitypowerea.userecho.com/en/communities/1/topics/318-position-cutter-pc-reduce-the-lot-size-by-previous-lot-size-in-the-sequence))
* **Custom lot coefficients** [*(starting from v2.33)*](/docs/versions-history#20210610-233): user-defined coefficient sequence (see **Custom lot coefficients** parameter below)

<br />

### Lot coefficient / adding / x0

Lot coefficient / adding / x0 for 2nd and next deals lot calculation.

<br />

### Custom lot coefficients

<sup>[*(starting from v2.33)*](/docs/versions-history#20210610-233)</sup>

User-defined coefficient sequence for **Custom lot coefficients** increasing mode. Coefficients should be separated by comma. Max allowed string length - 63 symbols.

> For example: sequence "1.0,2.0,3.0" with start lot 0.1 will cause a series with lots: 0.1 (first deal) - 0.1 - 0.2 - 0.3 - 0.3 - 0.3 - ...

<br />

### Step size

Step size (in points or like coefficient to Volatility)

<br />

### Step size calc mode

<sup>[*(starting from v2.31)*](/docs/versions-history#20210508-231)</sup>

Step can be set:
* **In points** ([what is a "point"?](/docs/FAQ/what-is-a-point))
* Like **Coefficient to Volatility** ([volatility parameters](/docs/volatility) must be set correctly)

<br />

### Step increase coefficient

Step increase coefficient for 2nd and all next martingale deals.

> For example, with **Step size** = 20 points and **Step increase coefficient** = 1.5, distances between orders in anti-martingale series will be 20 - 30 - 45 - 67.5 - 101.3 and so on

Set 0 to disable step change <sup>[*(starting from v2.54)*](/docs/versions-history)</sup>

<br />

### Min step size (points)

<sup>[*(starting from v2.29)*](/docs/versions-history#20210403-229)</sup>

Minimum step size (in points) ([what is a "point"?](/docs/FAQ/what-is-a-point)).

Calculated step can't be smaller than the Min step size value.

<br />
<br />

# Anti-StopLoss

### Anti-StopLoss size

StopLoss applies to the series after the anti-martingale strategy is activated (2nd order in series is opened).

Can be negative (when calculated from average price) [*(starting from v2.20)*](/docs/versions-history#20201103-220)

<br />

### Anti-StopLoss reduce size, Anti-StopLoss reduce coefficient and Min Anti-StopLoss size

<sup>[*(starting from v2.20)*](/docs/versions-history#20201103-220)</sup>

Anti-StopLoss reduce size and coefficient.

If enabled, SL for each next anti-martingale order in the series will be reduced by specified **reduce size**. This size will be also multiplied by **reduce coefficient** for each next stage too.

> For example, with Anti-StopLoss = 50, reduce size = 10 and reduce coeff = 1.1 you will have the following series:
* For the 1st deal SL will be = 50 points
* For 2 deals: 50 - 10 = 40
* For 3 deals: 50 - 10*1.1 = 29
* For 4 deals: 50 - 10 - 10*1.1 - 10*1.1*1.1 = 16.9
* For 5 deals: 50 - 10 - 10*1.1 - 10*1.1*1.1 - 10*1.1*1.1*1.1 = 3.6
* And so on (-11 for 6 deals, -27.2 for 7 deals)

Anti-StopLoss can't be less than **Min Anti-StopLoss size (points)** ([what is a "point"?](/docs/FAQ/what-is-a-point)).

> For example, if you set **Min Anti-StopLoss size** = 20, for all deals from the last example, starting from 4th SL will be = 20 (16.9 is less than 20, so will be replaced).

**Anti-StopLoss size** can be negative.

<br />

### Anti-StopLoss mode

<sup>[*(starting from v2.20)*](/docs/versions-history#20201103-220)</sup>

Anti-StopLoss mode:
* **From average open price**: SL based on weighted average open price of all positions in the series.
* **From last open price**: SL based on the open price of the last position in the series.
* **From first open price**: SL based on the open price of the first position in the series.

<br />

### Anti-StopLoss calc mode

<sup>[*(starting from v2.31)*](/docs/versions-history#20210508-231)</sup>

Can be:
* **In points** ([what is a "point"?](/docs/FAQ/what-is-a-point))
* Like **Coefficient to Volatility** ([volatility parameters](/docs/volatility) must be set correctly)

<br />

### Allow TakeProfit for anti-martin trades

<sup>[*(starting from v2.37)*](/docs/versions-history#20210906-237)</sup>

Set **true** to enable simple TakeProfit for series with anti-martingale trade open.


<br />
<br />

# Allow both Martin and Anti-martin

<sup>[*(starting from v2.32)*](/docs/versions-history#20210605-232)</sup>

Set **true** to allow martingale deals if any anti-martingale deal is opened and vice versa.



