---
layout: page
title: Active periods
permalink: /docs/active-periods
---

# Active periods
<sup>[*(starting from v2.52)*](/docs/versions-history#20230211-0324-252)</sup>

Each signal has an **Active period** parameter. It can be **always active** or use 1 of 4 predefined periods.

Active periods are set in this section. Each period can start and end by its own rules.


<br />

### Activation event and Activation value

Event that activates period. Can be one of the following:
* **Activate immediately**: period is active from the very beginning and until the deactivation event occurs. <br />Use this option for periods you use for the first entry signals (otherwise the first trade will never open).

* **Activate after time (seconds)**: period activates after **Activation value** seconds after the first deal of the series opens. If the first deal is closed for any reason (by Partial close, manually, etc), the earliest opened deal in the corresponding direction is used as the "first open time".
* **Activate after trades number >=** and **Activate after trades number <=** [*(starting from v2.55)*](/docs/versions-history#20230720-0818-255): period activates if number of opened trades in the series becomes greater/smaller than **Activation value**.<br />
   For example, you can activate new close signal after certain number of martingale trades and then activate another one when the Partial close closes some trades.
* **Activate on DrawDown >=** and **Activate on DrawDown <=**: period activates if current drawdown of series becomes greater/smaller than **Activation value %**.

Each Active period can be activated **Max activations number** times. After that it will not be activated again after deactivation even if an activation event occurs.

<br />

### Deactivation event and Deactivation value

Deactivation events work the same way as activation events.

Period can't be deactivated if it is not active (all deactivation events will be ignored). But it can be deactivated right after the activation (if a deactivation event occurs). Period can be deactivated only once.

<br />

### Max activations number
<sup>[*(starting from v2.55)*](/docs/versions-history#20230720-0818-255)</sup>

Maximum number of activations of this period. If set to 0, period can be activated unlimited number of times.

Default value is 1, means period can be activated only once.
