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

<br />

Calculation mode is available for almost all parameters in the EA.

<br />

### Percentage of Price

Starting from [v3.0.15](/docs/versions-history#20241116-20250105-301-3015), you can choose **Percentage of Price** calculation mode: distance will be calculated as **asset price * Percentage / 100**.

Asset price is usually series average open price or order open price (for Individual Follow-up and Pending orders). 

<br />

### Volatility Indicator

Indicator used for the Volatility calculation.
Can be one of the following:
* ATR
* StDev
* ATR based on "Close-Open" (high and low prices not used)
* WATR
* Volume (don't use for this block!)

<br />

### TimeFrame and Period

TimeFrame and Period of volatility indicator

<br />

### Min and Max volatility to use (points)

Indicator value will be limited by these Min and Max values defined in **Points** ([what is a "point"?](/docs/FAQ/what-is-a-point)).

> For example, if current StDev value is 0.00203 (20.3 points for EURUSD), and you set **Min volatility to use** = 25, EA will use 25 points as volatility size (and TrailingStop with Volatility Coefficient = 1.5 will be 25 * 1.5 = 37.5 points (not 20.3 * 1.5 = 30.45).

Set 0 to disable the limit.

<br />

### Fix volatility on 1st position open

<sup>[*(starting from v2.50)*](/docs/versions-history#20221014-20230107-250)</sup>

Set **true** to use the same volatility over the lifetime of the series.

Set **false** to refresh volatility every bar.
