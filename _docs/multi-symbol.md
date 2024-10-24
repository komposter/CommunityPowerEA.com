---
layout: page
title: Multi-symbol
description: Multi-symbol parameters
permalink: /docs/multi-symbol
---

# Multi-symbol

<sup>[*(starting from v3.0)*](/docs/versions-history#20241024-30)</sup>

Starting from [v3.0]((/docs/versions-history#20241024-30)), you can trade multiple symbols with one EA instance (MT5 only).

EA will use the same settings for all symbols, so make sure your strategy is universal and doesn't depend on point size or other symbol-specific parameters.

You can also backtest and optimize the EA on multiple symbols simultaneously. This allows you to check and apply functions designed to manage the entire account, like [Global Account Close](/docs/global-account-properties) or [Risk per currency](/docs/risk-per-currency).

### Multi-symbol limitations

 * Works for MetaTrader 5 only
 * GUI works for the **current chart symbol** only
 * Backtesting is slower even if you use only one symbol (because it needs to check order symbol and magic on each tick, and in a single-symbol version doesn't)


# Multi-symbol parameters

### Symbols list

List of symbols to run EA on (separated by comma). Leave empty to run on the current symbol only (as a single-symbol version).

If your broker uses suffixes for symbols (like `_x` or `.m`), you can specify the suffix in the next parameter (no need to add it to each symbol in the list).

<br />

### Symbol suffix

Suffix for symbols in the list.

> For example, if you set Symbol list to `EURUSD,GBPUSD` and Symbol suffix to `_x`, EA will trade on `EURUSD_x` and `GBPUSD_x`.

<br />
