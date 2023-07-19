---
layout: page
title: Lot
description: Lot size parameters
permalink: /docs/lot
---

# Lot parameters

### Lot type

<sup>*([starting from v2.10](/docs/versions-history#20200518-210), [improved in v2.47](/docs/versions-history#20220520-247))*</sup>

Lot size calculation type (applies to first trade in each series): <br/>
* **Fixed lot**: lot is fixed and regulated by Lot size parameter
* **Risk per trade**: deal closed by SL will damage the account by a specified % of balance. Percent is regulated by the "Lot risk %" parameter.
  _This mode will work correctly only with  disabled martingale and enabled StopLoss!_
* **Margin percent use**: lot calculates to use specified % of margin. Percent is regulated by the "Lot risk %" parameter.
* **Fixed size per 1000**: lot size is specified for every 1000 units of your account balance. For example, with Start lot = 0.1 you’ll have: <br/>
  - for balance $2000: 0.2 lots
  - for balance $1980: 0.1 lots (only 1 full thousand is available)
  - for balance $700: 0.01 lots (min lot used because balance size < 1000)
  - for balance 112 342: 11.20 lots
* **Fixed size per 1000 USD**: the same as Fixed size per 1000, but converted to USD. So, if your account is in EUR or GBP you’ll have a greater lot.
* **Amount in base currency**: lot calculates as Lot size / current symbol price. Suitable for cryptocurrencies, when you want to invest fixed amount of USD in each trade

<br />

### Lot size

Lot size for **Fixed lot**, **Fixed size per 1000** and **Fixed size per 1000 USD** modes.

<br />

### Lot risk %

<sup>[*(starting from v2.10)*](/docs/versions-history#20200518-210)</sup>

Risk % for **Risk per trade** and **Margin percent use** modes.

<br />

### Max lot

Max lot EA can use for any deal.

If 0, the limit is disabled.

<br />

### Max lot per 1000

<sup>[*(starting from v2.32)*](/docs/versions-history#20210605-232)</sup>

Max lot calculated per 1000 units of account balance.

> For example, with balance 15000 USD and Max lot per 1000 = 0.1, max lot size for EA will be 15 * 0.1 = 1.5

Set 0 to disable the limit.

[Initial discussion is here](https://communitypowerea.userecho.com/en/communities/1/topics/196-max-lot-option-max-lot-per-1000)

<br />
<br />

# Lot size based on previous results

### Apply martin to the new deals

<sup>[*(starting from v2.07)*](/docs/versions-history#20200504-207)</sup>

Increase lot size of the first deal of the new series (opened on signal) after closing the loss. The EA will apply [lot coefficient](/docs/martingale#lot-coefficient--adding--x0) until the profit becomes positive.

To begin again with a Start lot on account with loss, set a new [Magic number](/docs/main-parameters#expert-id).

<br />

### d'Alembert money management system

[Starting from v2.54](/docs/versions-history#20230427-0706-254), you can apply d'Alembert money management system to all first deals of the series.

d'Alembert money management system increases lot size after each loss and decreases after each win, but does this in a more smooth way than martingale:

![]({{site.baseurl}}/assets/img/docs/dAlambert1.png)

The lot size is calculated as:
 * If the last series closed with profit, and account reached a new high, use the standard lot size calculation (fixed lot, risk per trade, etc)
 * If the last series closed with loss, increase the lot by 1 unit (unit = first lot of the first series after account new high)
 * If the last series closed with profit >= 0 and < **Expected loss** in money, keep the same lot as in previous series.
 * If the last series closed with profit >= **Expected loss** in money and < 2\***Expected loss** in money, decrease lot by 1 unit
 * If the last series closed with profit >= 2\***Expected loss** in money and < 3\***Expected loss** in money, decrease lot by 2 units
 * If the last series closed with profit >= 3\***Expected loss** in money and < 4\***Expected loss** in money, decrease lot by 3 units
 * and so on...

<br />

#### d'Alembert: Expected Loss

Expected loss in money for d'Alembert money management system.

Set 0 to disable d'Alembert.

<br />

#### d'Alembert: Units Multiplier

Custom units multiplier for d'Alembert money management system.

> For example, with Units Multiplier = 0.5: <br/>
> if the last series closed with profit >= 3*Expected loss* in money and < 4*Expected loss in money, lot will be decreased by 3*0.5=1.5 units (instead of 3 units)
