---
layout: page
title: Risk per currency
permalink: /docs/risk-per-currency
---

# Risk per currency

<sup>[*(starting from v2.49)*](/docs/versions-history#20221007-249)</sup>

Risk manager allows you to control the risks in your account by prohibiting the opening of new positions if you already have much enough.

You can set a restriction by positions number or by sum lot.

You can also decide how to manage opposite positions -- limit only netto position number/size, set limits for buys and sells separately, or sum all positions and limit the total number/size.

By default, only positions with magic number equals Expert Id are taken into account, but you can specify additional magics in settings.

[More detailts](https://forum.communitypowerea.com/communities/1/topics/775-risk-per-currency-function)

<br />

### Type

Type of risk management:

**Disabled**: risk management disabled.

**By positions number**: limit is set as positions number.

> For example, if Max risk value = 3, and you have 3 open positions (lot doesn't matter), new opens will be prohibited.

**By lots**: limit is set as sum lot size.

> For example, if Max risk value = 3, and you have 5 open positions with sum lot 1.5 + 1.0 + 0.4 + 0.03 + 0.05 = 2.95, a new open will be allowed for lot 0.05 or less.

<br />

### Opposite positions calc mode

Opposite positions calculation mode:

**Netto mode**: opposite positions decrease sum lot.

> For example, 2 buy + 1 sell = +1. With Max risk value = 3 and Type = By positions number, you’ll be able to open 2 new buys (netto will be +3) or 4 new sells (netto will be -3).

**Hedge mode**: opposite positions are managed separately.

> For example, 2 buy + 1 sell = +2/-1. With Max risk value = 3 and Type = By positions number, you’ll be able to open 1 new buy (buys will be +3) and 2 new sells (sells will be -3).

**Summ mode**: all positions are managed together regardless of type.

> For example, 2 buy + 1 sell = 3. With Max risk value = 4 and Type = By positions number, you’ll be able to open 1 new position of any type.

<br />

### Max risk value

Max sum lot (in **By lots** mode) or max positions number (in **By positions number** mode).

<br />

### Additional magic numbers list (comma separated)

By default, only positions with magic number equals Expert Id are taken into account by Risk manager, but you can specify additional magics by this parameter.

<br />

### Use semaphore

Set true to avoid opening 2 or more positions at the same time and guarantee risk management. Make sense if you use several EAs on the same symbol.

