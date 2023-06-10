---
layout: page
title: Hedge
description: Hedge parameters
permalink: /docs/hedge
---

# Hedge parameters

Hedge -- is a position in the opposite direction to the existing (main) position.

If you already have a main series started (for example, buy), hedge (sell) can be opened only if all hedge-rules are passed (details in the table below).

Main series remains main, as long as the first order open time is less than the open time of the first hedge order. Thus, if your main series is closed, and the hedge is still open, the hedge series becomes main. For example, you had 3 sell orders in the main series, one buy order in the hedge series, and all sells were closed by TakeProfit. Now your buy-order -- is the first order of the new main series.

Hedge series can also become main, if the first main order is closed and the first hedge order open time becomes smallest within all open trades. This can be done by Partial close or manually, for example.

If you want to replace **Auto-hedge after order #**, that was available before v2.50, set:
* Allow hedge on its own signal only = False
* Allow hedge only right after main position open = True
* Allow hedge only after main order # = desired value

If you want to replace **Auto-hedge on DrawDown**, set:
* Allow hedge on its own signal only = False
* Allow hedge only right after main position open = False
* Max hedge orders number = 1
* Allow hedge only on main DrawDown % = desired value

More details / your comments and suggestions are welcome [here](https://t.me/CommunityPowerNews/60).

<br />

### Allow hedge

If **true**:
* allows open buy when sell is opened,
* allows open sell when buy is opened.

If **false**:<br/>
* skips all buy signals (first and martingale) when sell is opened,
* skips all sell signals (first and martingale) when buy is opened.

<br />

### Allow hedge on its own signal only

<sup>[*(starting from v2.50)*](/docs/versions-history#20221014-20230107-250)</sup>

If **true**, allows a new hedge order only on its own signal (one of the signals with “Open hedge on” = Open on individual/collective signal).
All next hedge positions are opened by the same signals, martingale/anti-martingale sections are not used.

If **false**, allows a new hedge series to start by regular signals (those used to open the main series).
After the first entry, hedge-series works like the main series (with martingale, SL/TP/TS, close signals, etc)

<br />

### Increase hedge lot after order #, Increase lot coefficient, Apply coefficient to

<sup>[*(starting from v2.32)*](/docs/versions-history#20210605-232)</sup>

If there are X sell trades opened and buy signal appears, lot for the new buy order will be calculated using these parameters.

Depending on **Apply coefficient to**:<br/>
* **First opposite lot** mode: lot for the first buy will be calculated as "lot of first sell-order * Increase lot coefficient"
* ~~**Corresponding lot** mode: lot for buy order #X will be calculated as "corresponding sell lot * Increase lot coefficient" where ‘corresponding sell’ - is a sell number Increase hedge after # - X + 1~~ <sup><sub>[*(removed in v2.50)*](/docs/versions-history#20221014-20230107-250)</sub></sup>
* **Last opposite lot mode**: lot for the first buy will be calculated as *lot of last sell-order * Increase lot coefficient*
* **Sum opposite lot mode**: lot for the first buy will be calculated as *sum lot of all sell-orders * Increase lot coefficient*

Set **Increase hedge lot after order = 0** to disable this feature.

<br />

### Allow hedge only after main order #

<sup>*([starting from v2.25](/docs/versions-history#20210115-225) , [refactored in 2.50](/docs/versions-history#20221014-20230107-250))*</sup>

Allows to open a hedge series (buy, if sell is already active, or sell, if buy is already active) only if there are X open orders of main series.

> For example, if **Allow hedge only after main order # = 3**, buy can be opened if there are 3 sell-positions.

Hedge is opened with or without signal (depends on **Allow hedge on its own signal only**) and after check of all other hedge filters (details below).

<br />

### Max hedge orders number

Max number of hedge orders opened.

Set 0 to disable the limit.

<br />

### Allow hedge only on main DrawDown %

Allows to open a new hedge (buy, if sell is already active, or sell, if buy is already active) only if loss of the main series is >= X% from the current balance.

Set 0 to disable this filter.

<br />

### Allow hedge only right after main position open

<sup>[*(starting from v2.50)*](/docs/versions-history#20221014-20230107-250)</sup>

Allows to open a hedge order only within 60 seconds after main order opening.

If **true**, a new hedge can be opened only right after the main order (all other hedge filters and signals are also applied).

If **false**, hedge can be opened at any time while the main series exists (all hedge filters and signals are also applied).

<br />

### Allow hedge on new bar only

<sup>[*(starting from v2.50)*](/docs/versions-history#20221014-20230107-250)</sup>

Allows to open a hedge order if there were no hedge-orders opened or closed on this bar of Signal TimeFrame. This means that a new hedge can be opened only on the next bar after the previous one.

If **false**, multiple hedge orders can be opened one after another on the same signal or after the same main order.

