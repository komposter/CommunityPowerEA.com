---
layout: page
title: What is a point?
permalink: /docs/FAQ/what-is-a-point
---

# What is a "point" in CommunityPower EA?

What does "StopLoss = 250 points" mean?

All parameters nominated in points use standard **4-digits points** (for 4- and 5-digits symbols) and **2-digits points** (for 2- and 3-digits symbols).

> For example, point size for EURUSD and GBPUSD is **0.0001**0. Point size for EURJPY and USDJPY is **0.01**0.

<br />

StopLoss = 250 points means that SL will be set 250 points (250*0.0001 = 0.02500) away from the deal open price (or from the last martingale deal open price, if martingale is enabled).

> For example, if you have Buy EURUSD at 1.23456, StopLoss will be at 1.20956 (1.23456 - 250*0.0001 = 1.20956).

<br />

If you have Sell USDJPY at 110.220, StopLoss will be at 112.72 (110.220 + 250*0.01 = 112.72).

StopLoss is drawn on the chart by magenta line, zoom out to find the line:
![what-is-a-point.gif](..%2F..%2Fassets%2Fimg%2Fdocs%2Fwhat-is-a-point.gif)
