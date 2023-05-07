---
layout: page
title: Period limits
permalink: /docs/period-limits
---

# Period limits

Starting from v2.48, you can limit trades per day, as well as Max DD and Max profit per day, per week and per month. When several EAs work on the same account, only trades with the same Magic number (Expert Id) are taken into account, so you can set independent limits for each group of CP EAs.

# Daily limits

## Max trades per day (current symbol)

Max number of trades for the current symbol (where EA works) that can be opened during the day. When the limit is reached, new trades for this symbol are disabled until the next day (pending orders are also deleted).

Only trades with the same Expert Id (magic number) opened during the current day are taken into account.

Please, note: EA will not disable trading for other EAs! If you want to disable any new trades, set the same **Max trades per day** for all EAs.

Set 0 to disable the limit.


## Max trades per day (all symbols)

Max number of trades (for all symbols) that can be opened during the day. When the limit is reached, new trades are disabled until the next day (pending orders are also deleted).

Only trades with the same Expert Id (magic number) opened during the current day are taken into account.

Please, note: EA will not disable trading for other EAs! If you want to disable any new trades, set the same **Max trades per day** for all EAs.

Set 0 to disable the limit


## Max DrawDown per day (%)

Max DrawDown (as a percentage of the max balance level of the day) caused by trades with the same Expert Id (magic number) during the current day. When it is reached, new trades are disabled until the next day (pending orders are also deleted).

Open trades are taken into account, but DD is calculated from the last balance peak (not equity).

Please, note: EA will not disable trading for other EAs! If you want to disable any new trades, set the same **Max DrawDown** for all EAs.

Set 0 to disable the limit.


## Max DrawDown per day (account currency)

Max DrawDown (from the max balance level) caused by trades with the same Expert Id (magic number) during the current day. When it is reached, new trades are disabled until the next day (pending orders are also deleted).

Open trades are taken into account, but DD is calculated from the last balance peak (not equity).

Please, note: EA will not disable trading for other EAs! If you want to disable any new trades, set the same **Max DrawDown** for all EAs.

Set 0 to disable the limit.


## Max Profit per day (%)

Max Profit (as a percentage of the start balance of the day) caused by trades with the same Expert Id (magic number) during the current day. When it is reached, new trades are disabled until the next day (pending orders are also deleted).

Please, note: EA will not disable trading for other EAs! If you want to disable any new trades, set the same **Max Profit** for all EAs.

Set 0 to disable the limit.


## Max Profit per day (account currency)

Max Profit (from the start balance of the day) caused by trades with the same Expert Id (magic number) during the current day. When it is reached, new trades are disabled until the next day (pending orders are also deleted).

Please, note: EA will not disable trading for other EAs! If you want to disable any new trades, set the same **Max Profit** for all EAs.

Set 0 to disable the limit.


# Weekly and Monthly limits

Weekly and Monthly limits are exactly the same as the daily limits (max DD and max profit limits are available). Also take a look at the "Common limits properties" below for some more details.

# Common limits properties

## Week start day

First day of the week for the "per week" periods calculations.<br/>For example, if **Week start day** is Wednesday, only positions opened since the last Wednesday will be counted for the **Max trades per week** limit.


## Day start hour

Start hour of the day for all time periods.
For example, if **Day start hour** = 3:<br/>
* Daily period starts at 03:00,<br/>
* Weekly period starts at 03:00 on **Week start day**,<br/>
* And Monthly period starts at 03:00 on the 1st day of the month.


## Close open trades on profit/DD

If **true**, EA will close all open positions when profit or DD is reached.<br/>
If **false**, EA will not close existing positions (new openings will be disabled, of course).

Please, note: EA will not close positions of other EAs! If you want to close all positions on Profit/DD, set the same Period Limits for all EAs.

