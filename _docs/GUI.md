---
layout: page
title: GUI
description: GUI parameters
permalink: /docs/gui
---

# GUI

<sup>[*(starting from v2.14)*](/docs/versions-history#20200722-214)</sup>

You can activate the trading and signals panel in the EA settings:

![GUI.png](..%2Fassets%2Fimg%2Fdocs%2FGUI.png)

<br />

You can use expert panel for one click trading (with and without confirmation). EA will manage orders opened by panel as its own orders:

![one-click-trading.gif](..%2Fassets%2Fimg%2Fdocs%2Fone-click-trading.gif)

<br />

### Close checkboxes

<sup>[*(starting from v2.56)*](/docs/versions-history#20230818-1025-256)</sup>

If the Close checkbox is unchecked, closing by [StopLoss](/docs/follow-up#stoploss), [TakeProfit](/docs/follow-up#takeprofit), 
[BreakEven](/docs/follow-up#breakeven), [TrailingStop](/docs/follow-up#trailingstop), [Partial close](/docs/partial-close) and 
any [Signal](/docs/signals-and-filters) **is disabled for corresponding direction**.

[Sum StopLoss](/docs/follow-up#sum-stoploss-in-account-currency), [Sum TakeProfit](/docs/follow-up#sum-takeprofit-account-currency) and 
[Partial close in the 'Any with any' mode](/docs/partial-close#close-any-with-any) work if the Close checkboxes are checked **for both Buy and Sell**.

[Global Account Closing](/docs/global-account-properties) and closing by GUI buttons work with **any state of Close checkboxes**.

<br />
<br />

# GUI parameters

### Enable panel

Show panel on chart

<br />

### Font name

Font name for all text labels and buttons

<br />

### Window transparency

Transparency for all elements of the panel (0-255)

<br />

### Show signals

Show signals panel.

Only activated signals and filters will be shown.

Click on signal label to show indicator and switch to signal TF [*(starting from v2.26)*](/docs/versions-history#20210202-226):

![show-indy.gif](..%2Fassets%2Fimg%2Fdocs%2Fshow-indy.gif)

<br />

### Signals background color, Signals text color

Signals background and text color

<br />

### Buy/Sell block colors

All colors used in Buy and Sell trading blocks (background, buttons (pressed and unpressed), borders and text).

<br />
<br />

# Lines

<sup>[*(starting from v2.04)*](/docs/versions-history#20200416-204)</sup>

You are able to draw StopLoss, TakeProfit, BreakEven and NextOrder levels on the chart. Each level can be configured with following parameters.

<br />

### Width

Line width.

Set 0 to disable drawing this type of lines.

<br />

### Style

Line style (works with width = 1 only)

<br />

### Color BUY

Color for the line corresponding to BUY orders

<br />

### Color SELL

Color for the line corresponding to SELL orders

<br />

### Allow dragging the lines to modify SL/TP

<sup>[*(starting from v2.50)*](/docs/versions-history#20221014-20230107-250)</sup>

Allow modification of SL and TP by dragging the lines on the chart.

To restore original SL or TP, just delete the line.

<br />
<br />

# Orders on chart

<sup>[*(starting from v2.28)*](/docs/versions-history#20210303-228)</sup>

You can enable drawing of the EA orders on the chart and toggle it by button on the expert panel.

EA draws only trades with a magic number equal to the Expert Id set in the properties (and manually opened trades, if Manage manual = true):

![show_orders.gif](..%2Fassets%2Fimg%2Fdocs%2Fshow_orders.gif)

<br />

### Main properties

Show OPENED deals:
* **Disabled** - don't draw any opened positions on chart,
* **Trend lines from open to current price** - draw trend line for every open position,
* **Horizontal lines like in MT** - draw horizontal line for every open position,
* **Trend lines + Horizontal lines** - draw both horizontal and trend lines for every open position.

Show CLOSED deals - true / false.

Show PENDING orders - true / false.

Max history deals - draw only last X deals from history (0 - disable limit).

<br />

### Color properties

Color for:
* Open arrows,
* Profitable trades (lines and arrows),
* Losing trades (lines and arrows).

Each color can be set for Buys and Sells separately.

<br />

### Profit properties

Profit labels properties:
* **Show profit in money** - show profit in account currency,
* **Show profit in points** - show profit in points,
* **Show profit in percent** - show profit in percent to account balance,
* **Aggregate profit for opened positions** - aggregate all opened positions into one profit label,
* **Number of digits to show** - decimal digits for profit in points
* **Font name and size** - font properties.

<br />

### Style properties

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

