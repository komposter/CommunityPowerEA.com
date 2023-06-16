---
layout: page
title: Main parameters
description: Main parameters
permalink: /docs/main-parameters
---

# Main parameters

### Expert Id

Uniq expert id (magic number).

Use differnt Expert Ids to run several EAs on the same symbol.

<br />

### Expert Comment

Comment for positions.

Leave empty to use "CommunityPower" comment.

<br />

### Trade direction

Allowed direction: buy, sell or both.

EA will not open **first** trade in disabled direction (but will open additional trades).

<br />

### Signal TimeFrame
<sup>[*(starting from v2.09)*](/docs/versions-history#20200512-209)</sup>

Common TimeFrame for the following functions/parameters:
* New deal on the new bar
* Martin: New deal on the end of the bar only
* Martin: Min pause between trades
* Pending entry: Extremum bars
* Pending entry: Cancel after bars
* Pause after loss <br/>
and others..

<br />

### New deal on the new bar
<sup>[*(starting from v2.21)*](/docs/versions-history#20201130-221)</sup>

If **true**, allows opening of the first deal only on the next bar after the previous deal in the same direction was closed.

If **false**, the next deal can be opened on the same bar (if signal allows opening).

<br />

### Max floating loss
<sup>[*(starting from v2.23)*](/docs/versions-history#20201210-223)</sup>

Disables new trades if floating loss of positions opened by this EA (and manual positions, if “Manage manual trades” = true) reaches specified value (in account currency). Set 0 to disable this limit.

<br />

### Min margin level %

<sup>[*(starting from v2.31)*](/docs/versions-history#20210508-231)</sup>

Disables new trades if Account margin level reaches specified value (in %). Set 0 to disable this limit.

<br />

### Custom commission

<sup>[*(starting from v2.27)*](/docs/versions-history#20210302-227)</sup>

Commission size (in account currency per lot) for all calculations in the EA (including BE level, current profit, etc).

Overrides real commission size. Can be used for MT5 accounts with commission taken on opening and closing to help the EA calculate current profit correctly.

Set 0 to use real commission size.

<br />

### Manage manual trades

If **true**, EA manages trades opened by hands (with magic number = 0).

EA considers manual trades as its own, takes them into account for Max trades limit, manages them by TrailingStop and BreakEven, etc.

If **false**, EA doesn't take into account manual trades.
