---
layout: page
title: Global account properties
permalink: /docs/global-account-properties
---

# Global account properties

GlobalAccount functions manage **all open positions** (with any magic number, opened by any EA or manually).

Don't trade symbols with **different trading sessions** on the same account with GlobalAccount closings enabled!

Be careful — **other EAs can't cooperate with CP EA correctly**, so you have a small chance of new positions opening before all positions are closed by GlobalAccount signal (in case a new opening signal of another EA happens simultaneously with GA close signal). So, please, test your EAs on demo-accounts first.

<hr>

# Global Account StopLoss

*(starting from v2.48)*

## GA StopLoss (account currency)

Loss of all **opened positions** (with all magic numbers, opened by any EA or manually) that should be closed as soon as it is reached.

*Don’t activate this option for several EAs, you need to activate it only once!*

Set 0 to disable GA StopLoss.


## GA StopLoss (% from balance)

The same as GA StopLoss (account currency) but in % from current account balance.

Set 0 to disable.

<hr>

# Global Account TrailingStop

[*(starting from v2.34)*](/docs/versions-history#20210612-234)

## GA TrailingStop

Equity Trailing Stop (in account currency / in % from account balance).
Activates when profit of all **opened positions** (with all magic numbers, opened by any EA or manually) reaches some value. Follows new equity highs. Closes all opened positions when equity rolls back by the same value.

For example, if you start with $1000 and set GA TrailingStop (account currency) = 35, trailing is activated when equity becomes $1035. If equity continues to grow, trailing follows. Let’s say equity becomes $1095 and then go down. EA closes all positions when equity is $1060 (1095 - 35).

*Don’t activate this option for several EAs, you need to activate it only once!*

Set 0 to disable GA TrailingStop.

<hr>

# Global Account TakeProfit

[*(starting from v2.31)*](/docs/versions-history#20210508-231)

## GA TakeProfit (account currency)

Profit of all **opened positions** (with all magic numbers, opened by any EA or manually) that should be closed as soon as it is reached.

*Don’t activate this option for several EAs, you need to activate it only once!*

Set 0 to disable GA TakeProfit.


## GA TakeProfit (% from balance)

The same as GA TakeProfit (account currency) but in % from current account balance.

Set 0 to disable.

<hr>

# Global Account TargetProfit

[*(starting from v2.31)*](/docs/versions-history#20210508-231)

## GA TargetProfit (account currency)

Target profit for the entire account. EA will close all positions when the target level is reached. Then the target level will be moved by the TargetProfit size (to the next level).<br/>Thus, EA will close positions every X dollars earned. Restarts if all positions are closed (starting from v2.34).

For example, if you start with $1000 and set GA TargetProfit = 25, EA closes all positions as soon as equity becomes $1025, then at $1050, $1075, $1100, and so on. Equity will not be exactly rounded to the TargetProfit size because of price moves, slippages and execution speed. So, progression could be like 1000 - 1026 - 1050 - 1074 - 1110.

*Don’t activate this option for several EAs, you need to activate it only once!*

Set 0 to disable GA TakeProfit.


## GA TargetProfit (% from balance)

The same as GA TargetProfit (account currency) but in % from the last equity high.

Set 0 to disable.

<hr>

# Stop Till Tomorrow After Close

*(starting from v2.45)*

## Stop Till Tomorrow After Close

Set **true** to disable trading till the next day (server time) after any close by Global Account functions
