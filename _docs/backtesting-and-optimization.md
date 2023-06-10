---
layout: page
title: Backtesting and optimization
description: Optimization criteria and other settings
permalink: /docs/backtesting-and-optimization
---

# Backtesting and optimization settings

# Tester withdrawal

<sup>[*(starting from v2.37)*](/docs/versions-history#20210906-237)</sup>


### Withdrawal type

* **Disabled** - don't use tester withdrawal.
* **Withdraw percent of profit** - withdraw specified percent of profit. For example, you set to withdraw 50% every day. If you have a profit of $50 at the end of the day, $25 is withdrawn. Set 100% to withdraw all profits you made.
* **Withdraw fixed amount** - withdraw specified amount of profit (in your account currency). For example, you set to withdraw $45 every day. If you have a profit of $50 at the end of the day, $45 is withdrawn.

Withdrawal amount can't be more than the profit made since the last withdrawal! For example, if you set to withdraw $45 every day but only $10 is made at the end of the day, only $10 is withdrawn.


### Withdrawal frequency

Frequency of withdrawals:

* **Withdraw every day**
* **Withdraw every week**
* **Withdraw every month**
* **Withdraw every quarter**
* **Withdraw every year**


### Withdrawal size (% or amount)

Percent or amount in account currency for each withdrawal.


<hr>

# Optimization criterion

<sup>[*(starting from v2.27)*](/docs/versions-history#20210302-227)</sup>

[How to use it?](https://communitypowerea.userecho.com/en/communities/7/topics/392-how-to-use-custom-optimization-criterion)

### Custom optimization criterion

* **Disabled** - don't use custom criterion.
* **R^2 on equity** - use R-squared as an estimation of quality of the strategy equity curve (read this article for details).<br/>
Greater value is better with 1 as maximum possible value (ideal equity going up-right without any volatility).<br/>
You should use Fixed start lot size when optimizing using the R-squared because of the nature of this criterion.

* **Max Relative DD** *(starting from 2.29*) - use Maximal relative DrawDown (in percent) based on equity.<br>
Result is shown as negative value to make genetic optimization possible (greater value should be better), so -17.5 in the results column means 17.5% DD


### Correlation type

Correlation calculation type for R^2 criterion:
* **Pearson's correlation**
* **Spearman's Rank-Order correlation**

