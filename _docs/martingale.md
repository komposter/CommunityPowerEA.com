---
layout: page
title: Martingale
permalink: /docs/martingale
---

# Martingale

## Martingale type

*(starting from v2.01)*

Type of martingale strategy used. Can be enabled or disabled.

<hr>

## Max trades in one direction

Max deals in series.

<hr>

## New deal on the end of the bar only

*(starting from v2.20)*

If enabled, Step condition is checked using last bar Close price (+ current spread for buy-orders).
So, only 1 trade per bar is allowed and all trades are opened on the beginning of the bar.

