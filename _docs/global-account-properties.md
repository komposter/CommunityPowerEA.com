---
layout: page
title: Global account properties
permalink: /docs/global-account-properties
---

# Global account properties

GlobalAccount functions manage **all open positions** (with any magic number, opened by any EA or manually).

{% include alert.html type="warning" title="Warning" content="Don't trade symbols with different trading sessions on the same account with GlobalAccount closings enabled!" %}

Be careful — **other EAs can't cooperate with CP EA correctly**, so you have a small chance of new positions opening before all positions are closed by GlobalAccount signal (in case a new opening signal of another EA happens simultaneously with GA close signal). So, please, test your EAs on demo-accounts first.

<br />

# Global Account StopLoss

<sup>[*(starting from v2.48)*](/docs/versions-history#20220702-248)</sup>

### GA StopLoss (account currency)

Loss of all **opened positions** (with all magic numbers, opened by any EA or manually) that should be closed as soon as it is reached.

    Don't activate this option for several EAs, you need to activate it only once!

Set 0 to disable GA StopLoss.

<br />

### GA StopLoss (% from balance)

The same as GA StopLoss (account currency) but in % from current account balance.

    Don't activate this option for several EAs, you need to activate it only once!

Set 0 to disable.

<br />

# Global Account TrailingStop

<sup>[*(starting from v2.34)*](/docs/versions-history#20210612-234)</sup>

### GA TrailingStop

Equity Trailing Stop (in account currency / in % from account balance).
Activates when profit of all **opened positions** (with all magic numbers, opened by any EA or manually) reaches some value. Follows new equity highs. Closes all opened positions when equity rolls back by the same value.

> For example, if you start with $1000 and set GA TrailingStop (account currency) = 35, trailing is activated when equity becomes $1035. If equity continues to grow, trailing follows. Let’s say equity becomes $1095 and then go down. EA closes all positions when equity is $1060 (1095 - 35).

    Don't activate this option for several EAs, you need to activate it only once!

Set 0 to disable GA TrailingStop.

<br />

# Global Account TakeProfit

<sup>[*(starting from v2.31)*](/docs/versions-history#20210508-231)</sup>

### GA TakeProfit (account currency)

Profit of all **opened positions** (with all magic numbers, opened by any EA or manually) that should be closed as soon as it is reached.

    Don't activate this option for several EAs, you need to activate it only once!

Set 0 to disable GA TakeProfit.

<br />

### GA TakeProfit (% from balance)

The same as GA TakeProfit (account currency) but in % from current account balance.

    Don't activate this option for several EAs, you need to activate it only once!

Set 0 to disable.

<br />

# Global Account TargetProfit

<sup>*([starting from v2.31](/docs/versions-history#20210508-231), [improved in v2.34](/docs/versions-history#20210612-234))*</sup>

### GA TargetProfit (account currency)

Target profit for the entire account. EA will close all positions when the target level is reached. Then the target level will be moved by the TargetProfit size (to the next level).

Thus, EA will close positions every X dollars earned.

Restarts if all positions are closed (starting from v2.34).

> For example, if you start with $1000 and set GA TargetProfit = 25, EA closes all positions as soon as equity becomes $1025, then at $1050, $1075, $1100, and so on. Equity will not be exactly rounded to the TargetProfit size because of price moves, slippages and execution speed. So, progression could be like 1000 - 1026 - 1050 - 1074 - 1110.

    Don't activate this option for several EAs, you need to activate it only once!


Set 0 to disable GA TakeProfit.

<br />

### GA TargetProfit (% from balance)

The same as GA TargetProfit (account currency) but in % from the last equity high.

    Don't activate this option for several EAs, you need to activate it only once!

Set 0 to disable.

<br />

# Stop Till Tomorrow After Close

<sup>[*(starting from v2.45)*](/docs/versions-history#20220421-245)</sup>

Set **true** to disable trading till the next day (server time) after any close by Global Account functions
