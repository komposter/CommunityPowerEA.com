---
layout: page
title: Pending entry
permalink: /docs/pending-entry
---

# Pending entry

<sup>[*(starting from v2.09)](/docs/versions-history#20200512-209)</sup> <sup>[(updated in v2.18)](/docs/versions-history#20200908-218)*</sup>

<br />

### Pending entry type

Type of Pending entry:<br/>
* **Pending entry disabled**: first deal will be opened by market.
* **Entry with STOP order**: buy-stop / sell-stop orders will be set on signal.
* **Entry with LIMIT order**: buy-limit / sell-limit orders will be set on signal.

<br />

### Distance to order

Distance from the current price to the pending order.

<br />

### Extremum bars

If **Extremum bars** > 0, pending order open price will be based on the price extremum (instead of current price):<br/>
* Buy-stop and sell-limit orders will be set on "**Highest** price of last **Extremum bars** + **Distance to order**",
* Sell-stop and buy-limit orders will be set on "**Lowest** price of last **Extremum bars** - **Distance to order**".

<br />

### Trail pendings mode

Trailing mode for pendings:
* **Disabled**: pendings will not be moved<br/>
* **Trail on signal**: pendings will be moved only while signal is active (oscillator in zone, filters allow this direction, etc.)
* **Trail always**: pendings will be moved till cancelation or execution.

Order level calculates using **Distance to order** and **Extremum bars** parameters and order moves to the new level only if the new level is better than the previous one (lower — for buy-stops and sell-limits, or higher — for sell-stops and buy-limits).

<br />

### Cancel on opposite signal

<sup>[*(starting from v2.10)*](/docs/versions-history#20200518-210)</sup>

Cancel order on the opposite oscillator signal. In 2.09 this behavior was regulated by the **Close on opposite signal** parameter.

<br />

### Cancel after distance

Pending order will be canceled if distance to the current price is greater than specified distance.<br/>
Pending order will not be placed if the distance to current price is too big.<br/>

Set 0 to disable cancelation after distance.

<br />

### Cancel after bars

Pending order will be canceled after specified number of bars.

Set 0 to disable cancelation after bars.

<br />

### Distance calc mode

**Distance to order** and **Cancel after distance** can be set:<br/>
* **In points** ([What is a "point" in CP?](https://communitypowerea.userecho.com/en/communities/7/topics/384-what-is-a-point-in-cp-what-does-stoploss-250-points-mean))
* Like **Coefficient to Volatility** ([volatility parameters](https://docs.google.com/document/d/1ww1M97H54IBwtCKZDhxtqsTsrtEMKofXHMEWMGCyZNs/edit#heading=h.sx27nza3heuj) must be set correctly)

<br />

### Enter by market if opposite trade is open

<sup>[*(starting from v2.37)*](/docs/versions-history#20210906-237)</sup>

Set **true** to disable Pending entry for buys if any sell position is open and vice versa (buy will be opened **by market** if signal appears).

<br />

### Delete if opposite trade is open

<sup>[*(starting from v2.42)*](/docs/versions-history#20220122-242)</sup>

Set **true** to delete pending buy-order if any sell position is open and vice versa. New buy-order can be opened when the sell-position is closed.


### Delete on position close

<sup>[*(starting from v2.50)*](/docs/versions-history#20221014-20230107-250)</sup>

Enable this option if you want to cancel existing pending order if another position is closed:<br/>
* **Delete on any close**: delete pending order if it was set before last position of any direction is closed
* **Delete on co-dir close***: delete pending order if it was set before last position of the same direction is closed (buy-limit and buy-stop will be canceled only after close of buy position)
* **Disable**: function disabled