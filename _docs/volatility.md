---
layout: page
title: Volatility
permalink: /docs/volatility
---

# Volatility for all parameters nominated in points

> [What is a "point" in CommunityPower EA?](/docs/FAQ/what-is-a-point)

Starting from [v2.31](/docs/versions-history#20210508-231), you can set **Volatility for all parameters nominated in points**, as well as limit volatility **min and max size**:

![]({{site.baseurl}}/assets/img/docs/volatility1.png)

Then you can set **calculation mode** for any parameter to **Volatility Coefficient**:

![]({{site.baseurl}}/assets/img/docs/volatility2.png)

In this example, **TrailingStop size** will be calculated as **ATR * 1.5**, and **Trailing Step** will be **ATR * 0.1**.

Calculation mode is available for almost all parameters in the EA.

<br />

### Percentage of Price

Starting from [v3.0.19](/docs/versions-history#20241116-20250122-301-3019), you can choose **Percentage of Price** calculation mode: distance will be calculated as **asset price * Percentage / 100**.

Asset price is usually series average open price or order open price (for Individual Follow-up and Pending orders). 

<br />

### Volatility Indicator

Indicator used for the Volatility calculation.

Can be one of the following:
* ATR
* StDev
* ATR (Close-Open): average candle body size (`abs(Close - Open)`) for the last N bars
* WATR
* Volume (don't use for this block!)
* OBV (don't use for this block!)
* Price Range: highest high - lowest low for the last N bars
* Percent Change: average change (`abs(close_curr - close_prev)`) for the last N bars

<br />

### 2nd Volatility Indicator
<sup>[*(starting from v3.0.19)*](/docs/versions-history#20241116-20250122-301-3019)</sup>

If set, volatility value is calculated as `max(volatility_1, volatility_2)`.

> For example, you can set **Volatility Indicator** = ATR, and **2nd Volatility Indicator** = StDev, and Distance will be the maximum of ATR and StDev.

<br />

### TimeFrame and Period

TimeFrame and Period of volatility indicator

<br />

### Invert/Smooth Period
<sup>[*(starting from v3.0.19)*](/docs/versions-history#20241116-20250122-301-3019)</sup>

If **Invert/Smooth Period** > 0, indicator value will be inverted against the MA with this period based on the indicator value.

> For example, if **Invert/Smooth Period** = 5, MA(5) will be applied to the indicator value, and the final value will be calculated as **MA(5) - (indicator value - MA(5))**.

If **Invert/Smooth Period** < 0, indicator value will be smoothed with the MA with this period.

> For example, if **Invert/Smooth Period** = -5, MA(5) will be applied to the indicator value, and the final value will be equal to **MA(5)**.

To understand this parameter better, you can use the **iVolatility** indicator: [for MT4]({{site.baseurl}}/assets/Indicators/iVolatility.ex4) and [for MT5]({{site.baseurl}}/assets/Indicators/iVolatility.ex5).

<br />

### Min and Max volatility to use (points)

Indicator value will be limited by these Min and Max values defined in **Points** ([what is a "point"?](/docs/FAQ/what-is-a-point)).

> For example, if current StDev value is 0.00203 (20.3 points for EURUSD), and you set **Min volatility to use** = 25, EA will use 25 points as volatility size (and TrailingStop with Volatility Coefficient = 1.5 will be 25 * 1.5 = 37.5 points (not 20.3 * 1.5 = 30.45)).

Set 0 to disable the limit.

<br />

### Min volatility to use (spreads)
<sup>[*(starting from v3.0.19)*](/docs/versions-history#20241116-20250122-301-3019)</sup>

Indicator value will be limited by this Min value defined as a number of ['normal' spreads](/docs/signals-and-filters#m1-bars-to-calculate-normal-spread).

> For example, if current StDev value is 0.00203 (20.3 points for EURUSD), and current 'normal' spread is 1.5 points, and you set **Min volatility to use (spreads)** = 20, EA will use 20 * 1.5 = 30 points as volatility size (and TrailingStop with Volatility Coefficient = 1.5 will be 30 * 1.5 = 45 points (not 20.3 * 1.5 = 30.45)).

Set 0 to disable the limit.

<br />

### Fix at the 1st position opening
<sup>[*(starting from v2.50)*](/docs/versions-history#20221014-20230107-250)</sup>

Set **true** to use the same volatility over the lifetime of the series.

Set **false** to refresh volatility every bar.
