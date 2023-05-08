---
layout: page
title: Lot
description: Lot size parameters
permalink: /docs/lot
---

# Lot parameters

## Lot type

*(starting from v2.10)*

Lot size calculation type (applies to first trade in each series): <br/>
* **Fixed lot**: lot is fixed and regulated by Lot size parameter
* **Risk per trade**: deal closed by SL will damage the account by a specified % of balance. Percent is regulated by the Lot risk % parameter. This mode will work correctly only with  disabled martingale and enabled StopLoss!
* **Margin percent use**: lot calculates to use specified % of margin. Percent is regulated by the Lot risk % parameter.
* **Fixed size per 1000**: lot size is specified for every 1000 units of your account balance. For example, with Start lot = 0.1 you’ll have: <br/>
- for balance $2000: 0.2 lots <br/>
- for balance $1980: 0.1 lots (only 1 full thousand is available) <br/>
- for balance $700: 0.01 lots (min lot used because balance size < 1000) <br/>
- for balance 112 342: 11.20 lots <br/>
* **Fixed size per 1000 USD**: the same as Fixed size per 1000, but converted to USD. So, if your account is in EUR or GBP you’ll have a greater lot.
* **Amount in base currency**: lot calculates as Lot size / current symbol price. Suitable for cryptocurrencies, when you want to invest fixed amount of USD in each trade *(starting from v2.47)*


## Lot size

Lot size for **Fixed lot**, **Fixed size per 1000** and **Fixed size per 1000 USD** modes.


## Lot risk %

*(starting from v2.10)*

Risk % for **Risk per trade** and **Margin percent use** modes.


## Max lot

Max lot EA can use for any deal.

If 0, the limit is disabled.


## Max lot per 1000

*(starting from v2.32)*

Max lot calculated per 1000 units of account balance.<br/>
For example, with balance 15000 USD and Max lot per 1000 = 0.1, max lot size for EA will be 15 * 0.1 = 1.5<br/>
Set 0 to disable the limit.<br/>
([details are here](https://communitypowerea.userecho.com/en/communities/1/topics/196-max-lot-option-max-lot-per-1000?))

