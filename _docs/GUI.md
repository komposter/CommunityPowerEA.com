---
layout: page
title: GUI
description: GUI parameters
permalink: /docs/gui
---

# GUI parameters

[*(starting from v2.14)*](/docs/versions-history#20200722-214)

You can activate the trading and signals panel (look at GUI user guide for details). Available parameters to customize GUI:

IMAGE HERE

One click trading without confirmation [*(starting from v2.20)*](/docs/versions-history#20201103-220):

IMAGE HERE

Click on signal label to show indicator and switch to signal TF *(starting from v2.26)*:

IMAGE HERE

Show orders *(starting from v2.28)* and show news *(starting from v2.29)*:

<hr>

# Expert panel

## Enable panel

Show panel on chart


## Font name

Font name for all text labels and buttons


## Window transparency

Transparency for all elements of the panel (0-255)


## Show signals

Show signals panel.

Only activated signals and filters will be shown.


## Signals background color, Signals text color

Signals background and text color


## Buy/Sell block colors: background, buttons (pressed and unpressed), borders and text

All colors used in Buy and Sell trading blocks.


<hr>

# Lines

[*(starting from v2.04)*](/docs/versions-history#20200416-204)

You are able to draw StopLoss, TakeProfit, BreakEven and NextOrder levels on the chart. Each level can be configured with following parameters:

## Width

Line width.

Set 0 to disable drawing this type of lines.

## Style

Line style (works with width = 1 only)

## Color BUY

Color for the line corresponding to BUY orders


## Color SELL

Color for the line corresponding to SELL orders

<hr>

Starting from **2.50.4**, you can also enable **Allow dragging the lines to modify SL/TP** to allow modification of SL and TP by dragging the lines on the chart. To restore original SL or TP, just delete the line.

<hr>

# Orders on chart

*(starting from v2.28)*

You can enable drawing of the EA orders on the chart and toggle it by button on the expert panel (look at **GUI user guide** (MISSING LINK) for details). EA draws only trades with a magic number equal to the Expert Id set in the properties (and manually opened trades, if Manage manual = true).

## Main properties

**Show OPENED deals**:
* **Disabled** - don’t draw any opened positions on chart,
* **Trend lines from open to current price** - draw trend line for every open position,
* **Horizontal lines like in MT** - draw horizontal line for every open position,
* **Trend lines + Horizontal lines** - draw both horizontal and trend lines for every open position.

**Show CLOSED deals** - true / false.

**Show PENDING orders** - true / false.

**Max history deals** - draw only last X deals from history (0 - disable limit).


## Color properties

Color for:
* Open arrows,
* Profitable trades (lines and arrows),
* Losing trades (lines and arrows).

Each color can be set for Buys and Sells separately.


## Profit properties

Profit labels properties:
* **Show profit in money** - show profit in account currency,
* **Show profit in points** - show profit in points,
* **Show profit in percent** - show profit in percent to account balance,
* **Aggregate profit for opened positions** - aggregate all opened positions into one profit label,
* **Number of digits to show** - decimal digits for profit in points
* **Font name and size** - font properties.


## Style properties

Draw style properties:
* Open-Close lines width (0 - don't draw)
* Open-Close lines style
* Open price labels width (0 - don't draw)
* Close price labels width (0 - don't draw)
* Show SL and TP dashes
* SL and TP vertical lines width (0 - don't draw)
* SL and TP vertical lines style
* Expiration lines width (0 - don't draw)
* Expiration lines style

