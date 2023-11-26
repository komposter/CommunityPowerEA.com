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
* **Withdraw percent of profit** - withdraw specified percent of profit.

  > For example, you set to withdraw 50% every day. If you have a profit of $50 at the end of the day, $25 is withdrawn. Set 100% to withdraw all profits you made.

* **Withdraw fixed amount** - withdraw specified amount of profit (in your account currency).

  > For example, you set to withdraw $45 every day. If you have a profit of $50 at the end of the day, $45 is withdrawn.

<br />

Withdrawal amount can't be more than the profit made since the last withdrawal!
> For example, if you set to withdraw $45 every day but only $10 is made at the end of the day, only $10 is withdrawn.

<br />

### Withdrawal frequency

Frequency of withdrawals. Can be:
* Withdraw every day
* Withdraw every week
* Withdraw every month
* Withdraw every quarter
* Withdraw every year

<br />

### Withdrawal size (% or amount)

Percent or amount in account currency for each withdrawal.

<br />
<br />

# Optimization criterion

[Starting from v2.27](/docs/versions-history#20210302-227) you can use custom optimization criterion.

To do this, select “Custom max” in the Strategy Tester settings:

![]({{site.baseurl}}/assets/img/docs/custom_criterion_1.png)

and enable corresponding parameter in the EA settings:

![]({{site.baseurl}}/assets/img/docs/custom_criterion_2.png)

Custom criterion value (R-squared or Max Relative DrawDown) will be shown in the “Result” column of Optimization results:

![]({{site.baseurl}}/assets/img/docs/custom_criterion_3.png)

<br />

### Custom optimization criterion

* **Disabled** - don't use custom criterion.
* **R^2 on equity** - use R-squared as an estimation of quality of the strategy equity curve (read [this article](https://www.mql5.com/en/articles/2358) for details).

    Greater value is better with 1 as maximum possible value (ideal equity going up-right without any volatility).

    You should use Fixed start lot size when optimizing using the R-squared because of the nature of this criterion.

* **Max Relative DD** [*(starting from v2.29)*](/docs/versions-history#20210403-229) -- use Maximal relative DrawDown (in percent) based on equity.

  Result is shown as negative value to make genetic optimization possible (greater value should be better), so **-17.5** in the results column means **17.5%** DD

<br />

### Correlation type

Correlation calculation type for R^2 criterion:
* Pearson's correlation
* Spearman's Rank-Order correlation

<br />

### Trades per year: min and good

<sup>[*(starting from v2.56)*](/docs/versions-history#20230818-1124-256)</sup>

Works with R^2 criterion only.

If defined, final result is adjusted by coefficient that calculated as:
* 0 -- if the "fact number of trades per year" < "min"
* 1 -- if the "fact number of trades per year" >= "good"
* in a range [0:1] -- if the "fact number of trades per year" is between "min" and "good"

> For example, if you set "min" to 100 and "good" to 200, and "fact number of trades per year" is 150, then coefficient will be 0.5

If you set only "min" value ("good" = 0, means disabled), then adjustment will be made only if "fact number of trades per year" < "min" (coefficient will be 0).

More examples for different settings:

| R^2 | min | good | trades <br />per year | adjustment <br />coefficient | final <br />result |
| --- |-----| --- |-----------------------|------------------------|--------------|
| 0.9 | 100 | 200 | 50                    | 0                      | 0.0          |
| 0.9 | 100 | 200 | 150                   | 0.5                    | 0.45       |
| 0.9 | 100 | 200 | 250                   | 1                      | 0.9          |
| 0.9 | 100 | 0 | 75                    | 0                      | 0.0            |
| 0.9 | 100 | 0 | 125                   | 1.0                    | 0.9            |
| 0.9 | 100 | 0 | 175                   | 1.0                    | 0.9            |
| 0.5 | 10  | 1000 | 100                   | 0.09                  | 0.045        |
| 0.5 | 10  | 1000 | 505                   | 0.5                   | 0.25          |
| 0.5 | 10  | 1000 | 901                   | 0.9                   | 0.45          |
| 0.5 | 10  | 1000 | 1000                  | 1.0                   | 0.5            |
| 0.5 | 10  | 1000 | 3576                  | 1.0                   | 0.5            |

As you can see, adjustment coefficient can only decrease the final result for low number of trades per year. After "good" value is reached, adjustment coefficient is 1.0 and doesn't change the final result.



