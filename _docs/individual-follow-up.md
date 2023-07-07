---
layout: page
title: Individual follow-up
permalink: /docs/individual-follow-up
---

# Individual BreakEven

<sup>[*(starting from v2.54)*](/docs/versions-history#20230427-0706-254)</sup>

Individual BE can only move SL in profit direction, it is always real (not virtual) and it can be replaced by a group SL, if the last one is set at a better price (for example, by trailing stop).

> **Be careful**, order closed by BE can be immediately reopened (if it is a martingale and all conditions for opening are met)

<br />

### BreakEven after, BreakEven to

If the profit of order reaches **BreakEven after** points ([what is a "point"?](/docs/FAQ/what-is-a-point)), SL will be moved to the level "open price + **BreakEven** to points" (opposite for sell).

Thus, the order will be closed with profit of **BreakEven to** points.

<br />

### ActivePeriod

BreakEven can be **always active** or use 1 of 4 predefined periods.

Each of 4 Active periods can be set in the [Active Periods for signals and filters](docs/active-periods) section.

BreakEven works only if it is active.
