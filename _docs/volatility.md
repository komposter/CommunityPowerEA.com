---
layout: page
title: Volatility
permalink: /docs/volatility
---

# Volatility for all parameters nominated in points

[What is a "point" in CP?](https://communitypowerea.userecho.com/en/communities/7/topics/384-what-is-a-point-in-cp-what-does-stoploss-250-points-mean)

Starting from v2.31, you can set **Volatility for all parameters nominated in points**, as well as limit volatility **min and max size**:

(IMAGE HERE)

Then you can set **calculation mode** for any parameter to **Coefficient to Volatility**:

(IMAGE HERE)

In this example, TrailingStop size will be calculated as *"Current ATR * 1.5"*, Trailing Step will be *"ATR * 0.1"*.

You can set "calculation mode" for the following parameters:
* Pending entry: Distance to order and Cancel after distance
* StopLoss size
* TakeProfit size
* Min profit to close on signal
* Martingale Step size
* Anti-martingale Step size
* Anti-StopLoss size
* TrailingStop size
* Trailing Step
* Start trailing after


## Volatility Indicator

Indicator used for the Volatility calculation.
Can be one of the following:
* ATR
* StDev
* ATR based on "Close-Open" (high and low prices not used)
* WATR
* (don’t use Volume mode for this block!)

[Example of ATR/StDev using.](https://communitypowerea.userecho.com/en/communities/1/topics/509-how-to-properly-use-the-volatility-filter?redirect_to_reply=3383#comment-3383)


## TimeFrame and Period

TimeFrame and Period of volatility indicator


## Min and Max volatility to use (points)

Indicator value will be limited by these Min and Max values defined **in points** ([What is a "point" in CP?](https://communitypowerea.userecho.com/en/communities/7/topics/384-what-is-a-point-in-cp-what-does-stoploss-250-points-mean)). For example, if current StDev value is 0.00203 (20.3 points for EURUSD), and you set **Min volatility to use** = 25, EA will use 25 points as volatility size (and TrailingStop with coefficient to volatility = 1.5 will be 25 * 1.5 = 37.5 points (not 20.3 * 1.5 = 30.45).

Set 0 to disable the limit.


## Fix volatility on 1st position open

*(starting from v2.50.4)*

Set **true** to use the same volatility over the lifetime of the series.
Set **false** to refresh volatility every bar.
