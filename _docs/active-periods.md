---
layout: page
title: Active periods
permalink: /docs/active-periods
---

# Active periods
<span class="badge badge-secondary">[*(starting from v2.52)*](/docs/versions-history#20230211-0324-252)</span>

Each signal has an **Active period** parameter. It can be "always active" or use 1 of 3 predefined periods.

Active periods are set in this section. Each period can start and end by its own rules.


<hr>

## Activation event, Activation value

Event that activates period. Can be one of the following:
* **Activate immediately**: period is active from the very beginning and until the deactivation event occurs. Use this option for periods you use for the first entry signals (otherwise the first trade will never open).
* **Activate after time (seconds)**: period activates after **Activation value** seconds after the first deal of the series opens. If the first deal is closed for any reason (by Partial close, manually, etc), the earliest opened deal in the corresponding direction is used as the "first open time".
* **Activate after trade #**: period activates when deal # **Activation value** in the series is opened.
* **Activate on DrawDown >=** and **Activate on DrawDown <=**: period activates if current drawdown of series becomes greater/smaller than Activation value %.

Each Active period can be activated only once. Means, it will not be activated again after deactivation even if an activation event occurs.


## Deactivation event, Deactivation value

Deactivation events work the same way as activation events.<br/>
Period can't be deactivated if it is not active (all deactivation events will be ignored). But it can be deactivated right after the activation (if a deactivation event occurs). Period can be deactivated only once.
