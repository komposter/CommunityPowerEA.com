---
layout: page
title: Pending entry
permalink: /docs/pending-entry
---

# Pending entry

*(starting from v2.09) (updated in v2.18)*


## Pending entry type

Type of Pending entry:<br/>
* **Pending entry disabled**: first deal will be opened by market.<br/>
* **Entry with STOP order**: buy-stop / sell-stop orders will be set on signal.<br/>
* **Entry with LIMIT order**: buy-limit / sell-limit orders will be set on signal.


## Distance to order

Distance from the current price to the pending order.


## Extremum bars

If **Extremum bars** > 0, pending order open price will be based on the price extremum (instead of current price):<br/>
* Buy-stop and sell-limit orders will be set on "**Highest** price of last **Extremum bars** + **Distance to order**",<br/>
* Sell-stop and buy-limit orders will be set on "**Lowest** price of last **Extremum bars** - **Distance to order**".


## Trail pendings mode

Trailing mode for pendings:
* **Disabled**: pendings will not be moved<br/>
* **Trail on signal**: pendings will be moved only while signal is active (oscillator in zone, filters allow this direction, etc.)<br/>
* **Trail always**: pendings will be moved till cancelation or execution.

Order level calculates using **Distance to order** and **Extremum bars** parameters and order moves to the new level only if the new level is better than the previous one (lower — for buy-stops and sell-limits, or higher — for sell-stops and buy-limits).


## Cancel on opposite signal

*(starting from v2.10)*

Cancel order on the opposite oscillator signal. In 2.09 this behavior was regulated by the **Close on opposite signal** parameter.


## Cancel after distance

Pending order will be canceled if distance to the current price is greater than specified distance.<br/>
Pending order will not be placed if the distance to current price is too big.<br/>

Set 0 to disable cancelation after distance.


## Cancel after bars

Pending order will be canceled after specified number of bars.

Set 0 to disable cancelation after bars.


## Distance calc mode

**Distance to order** and **Cancel after distance** can be set:<br/>
* **In points** ([What is a "point" in CP?](https://communitypowerea.userecho.com/en/communities/7/topics/384-what-is-a-point-in-cp-what-does-stoploss-250-points-mean))<br/>
* Like **Coefficient to Volatility** ([volatility parameters](https://docs.google.com/document/d/1ww1M97H54IBwtCKZDhxtqsTsrtEMKofXHMEWMGCyZNs/edit#heading=h.sx27nza3heuj) must be set correctly)

## Enter by market if opposite trade is open

*(starting from v2.37)*

Set **true** to disable Pending entry for buys if any sell position is open and vice versa (buy will be opened **by market** if signal appears).


## Delete if opposite trade is open

*(starting from v2.42)*

Set **true** to delete pending buy-order if any sell position is open and vice versa. New buy-order can be opened when the sell-position is closed.


## Delete on position close

*(starting from v2.50)*

Enable this option if you want to cancel existing pending order if another position is closed:<br/>
* **Delete on any close**: delete pending order if it was set before last position of any direction is closed<br/>
* **Delete on co-dir close***: delete pending order if it was set before last position of the same direction is closed (buy-limit and buy-stop will be canceled only after close of buy position)<br/>
* **Disable**: function disabled