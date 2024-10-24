---
layout: page
title: Versions history
description: Here you can find the list of all versions of the bot and the list of changes in each version.
permalink: /docs/versions-history
---

# Versions history

### 2024.10.24 (3.0)
* [+] [Multi-symbol](/docs/multi-symbol) version

[<button class="btn btn-success">Download v3.0 beta 1 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 3.0 beta 1.ex5)
[<button class="btn btn-primary">Download v3.0 beta 1 for MT4</button>]({{site.baseurl}}/assets/EAs/CommunityPower 3.0 beta 1.ex4)
[<button class="btn btn-info">Download v3.0 MultiSymbol beta 1 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 3.0 MS beta 1.ex5)

<br />

### 2024.09.15-10.15 (2.61)
* [+] Spread: [Apply to close](/docs/signals-and-filters#apply-to-close) parameter
* [*] Lot: [Risk per trade mode](/docs/lot#lot-type) takes into account Individual StopLoss first, and only if it is disabled, the series StopLoss is used
* [+] News: [Consider weekend](/docs/news#consider-weekend) parameter
* [*] PartialClose [refactored](https://t.me/CommunityPowerNews/238), speed [increased](https://t.me/CommunityPowerNews/246)
* [*] ActivePeriods and CollectiveSignal refactored
* [+] Backtesting and optimization speed increased
* [+] [Individual TakeProfit](/docs/individual-follow-up#individual-takeprofit) with "coefficient to SL" mode

{% include alert.html type="warning" title="Warning" content="All set-files with active Individual TP must be reviewed!" %}

[<button class="btn btn-success">Download v2.61 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.61.ex5)
[<button class="btn btn-primary">Download v2.61 for MT4</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.61.ex4)

<br />

### 2024.04.28-09.03 (2.60)
* [+] Volatility Filter with negative [Transformation Period](/docs/signals-and-filters#transformation-period) calculates Ratio of volatilities ("indicator 1 / indicator 2")
* [+] MA filter with [2nd Volatility](/docs/signals-and-filters#2nd-volatility-indicator-for-ma-filter)
* [+] Time: [GMT mode](/docs/time#gmt-mode)
* [+] [Individual StopLoss](/docs/individual-follow-up#individual-stoploss) with several different modes
* [*] Individual SL and TP are canceled if the [Close checkbox](/docs/gui#close-checkboxes) is unchecked
* [*] [Allow hedge](/docs/hedge#allow-hedge) behavior fixed for some specific cases
* [*] [GUI](/docs/gui): tooltips improved and fixed
* [+] [News filter](/docs/news): dynamic pause after download error
* [*] [Time filter](/docs/time) is applied to hedge orders
* [+] Spread: [Apply to hedge](/docs/signals-and-filters#apply-to-hedge) parameter
* [+] MT5: 70 non-optimisable parameters such as colors and styles have been moved to an external set-file. Specify [Set file with additional parameters](/docs/main-parameters#set-file-with-additional-parameters) to load your specific set, or leave it empty to use default values

{% include alert.html type="warning" title="Warning" content="All set-files with active Individual SL and TP must be reviewed!" %}

[<button class="btn btn-success">Download v2.60 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.60.ex5)
[<button class="btn btn-primary">Download v2.60 for MT4</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.60.ex4)
[<button class="btn btn-info">Download v2.60.a for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.60.a.ex5)


<br />

### 2024.01.18-04.26 (2.59)
* [+] [Partial Close](/docs/partial-close): Close any with any and Close any with any on signal parameters are replaced with [Close any with any mode](/docs/partial-close#close-any-with-any-mode)
* [+] PartialClose: [Close only with opposite](/docs/partial-close#close-any-with-any-mode) mode
* [+] Volatility Filter: [Transformation Period](/docs/signals-and-filters#transformation-period) and [Volatility Coefficient](/docs/signals-and-filters#volatility-coefficient)
* [+] Volatility: [OBV as a base indicator](/docs/signals-and-filters#volatility-filter-indicator)
* [+] [FastOptimization](/docs/backtesting-and-optimization#fast-optimization): Max DD and Min Trades per year
* [+] Time on the signals panel
* [+] Tester: [Custom Start and End dates](/docs/backtesting-and-optimization#custom-start-and-end-dates)
* [+] Tester: [Profit to Max Relative Drawdown ratio](/docs/backtesting-and-optimization#custom-optimization-criterion) optimization criterion
* [+] Martingale: [Keep the correct series](/docs/martingale#keep-the-correct-series)
* [+] CustomIndy: [UseBar](/docs/signals-and-filters#use-bar) instead of UseClosedBars
* [*] [CustomIndy](/docs/signals-and-filters#custom-indicators) works correctly with "Indicators" in the sub-folder name
* [+] "Manage manual trades" replaced with [Manage magic numbers](/docs/main-parameters#manage-magic-numbers)
* [+] GlobalAccountClose: [Magic numbers list](/docs/global-account-properties#magic-numbers-list) and [Magic numbers group name](/docs/global-account-properties#magic-numbers-list)

{% include alert.html type="warning" title="Warning" content="All set-files with PartialClose must be reviewed!" %}

[<button class="btn btn-success">Download v2.59 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.59.ex5)
[<button class="btn btn-primary">Download v2.59 for MT4</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.59.ex4)
[<button class="btn btn-info">Download v2.59.a for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.59.a.ex5)


<br />

### 2023.11.27-12.26 (2.58)
* [+] [Directional change filter](/docs/signals-and-filters#directional-change-filter) : Change dir after profit
* [*] [Max Current Spread](/docs/signals-and-filters#max-current-spread) filter allows to trade if spread is equal to max allowed
* [+] PartialClose: [Max profitable orders to close](/docs/partial-close#max-profitable-orders-to-close)
* [+] PartialClose: [Min profit to close (points)](/docs/partial-close#min-profit-to-close-points)
* [+] Anti-martin: [New deal on the end of the bar only](/docs/anti-martingale#new-deal-on-the-end-of-the-bar-only)
* [+] Individual FollowUp: [Apply to Anti-martin orders only](/docs/individual-follow-up#apply-to-anti-martin-orders-only) works for both Individual BE and Individual TS
* [+] Backtesting and optimization: [Lowest margin level](/docs/backtesting-and-optimization#custom-optimization-criterion) criterion
* [+] Lot: [Max first lot](/docs/lot#max-first-lot)
* [+] CustomIndy: [Optimization Inputs](/docs/signals-and-filters#optimization-inputs)
* [+] Fibo and Pivot lines have a price value in description (set "Show object description" in chart settings), News line has no description not to overload the chart

{% include alert.html type="warning" title="Warning" content="All set-files with active Individual BE and TS must be reviewed!" %}

[<button class="btn btn-success">Download v2.58 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.58.ex5)
[<button class="btn btn-primary">Download v2.58 for MT4</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.58.ex4)
[<button class="btn btn-info">Download v2.58.a for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.58.a.ex5)


<br />

### 2023.11.27 (2.57)
* [*] [Active Periods](/docs/active-periods): Bug fix

[<button class="btn btn-success">Download v2.57 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.57.ex5)
[<button class="btn btn-primary">Download v2.57 for MT4</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.57.ex4)
[<button class="btn btn-info">Download v2.57.a for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.57.a.ex5)


<br />

### 2023.08.18-11.24 (2.56)
* [+] New default parameters (thanks Sai for contribution!)
* [+] GUI improved with [Close checkboxes](/docs/gui#close-checkboxes), new colors and logo
* [+] [Individual StopLoss, TakeProfit and TrailingStop](/docs/individual-follow-up#individual-stoploss)
* [+] Individual BreakEven: [Apply to Anti-martin orders only](/docs/individual-follow-up#apply-to-anti-martin-orders-only)
* [+] 2 more [CustomIndy signals](/docs/signals-and-filters#custom-indicators)
* [+] [Pivot Filter](/docs/signals-and-filters#pivot-filter) with 4 separate signals
* [+] CustomIndy: ["Above/below the line/last arrow" and "On line/last arrow cross" modes](/docs/signals-and-filters#type-4)
* [+] Hedge: [Main series detection by sum volume](/docs/hedge#main-series-detection-by-sum-volume)
* [+] Optimization: [Trades per year: min and good](/docs/backtesting-and-optimization#trades-per-year-min-and-good)
* [+] ActivePeriod for [martingale](/docs/martingale#activeperiod), [anti-martingale](/docs/anti-martingale#activeperiod) and  [Partial Close](/docs/partial-close#activeperiod)
* [+] PartialClose: [Close any with any on signal](/docs/partial-close#close-any-with-any-on-signal)
* [+] Hedge: [Max difference in the number of trades](/docs/hedge#max-difference-in-the-number-of-trades)
* [+] [Oscillator filter](/docs/signals-and-filters#oscillator-filters-1-3): Force Index indicator
* [*] [Global Account Closing](/docs/global-account-properties): "Stop Till Tomorrow" works correct if it was set by another EA
* [*] [Line Filters](/docs/signals-and-filters#line-filters): Max Distance bug fixed
* [*] [Individual StopLoss and TakeProfit](/docs/individual-follow-up#individual-stoploss) fixed for pending orders
* [*] [R squared](/docs/backtesting-and-optimization#custom-optimization-criterion) calculation fixed for backtests with million and more equity points
* [*] [Active Periods](/docs/active-periods): Save/load state on reload
* [*] [Active Periods](/docs/active-periods): Correct activation for <= trades number or dd
* [*] [Enable alert on first signal](/docs/notifications#enable-alert-on-first-signal) disables Grammy message as well, if disabled
* [*] Manually created objects do not lose focus immediately after creation (MT5)

{% include alert.html type="warning" title="Warning" content="This version contains new default values of parameters, including Expert ID! If you use the EA with default parameters, wait until all open trades are closed before updating!" %}

[<button class="btn btn-success">Download v2.56 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.56.ex5)
[<button class="btn btn-primary">Download v2.56 for MT4</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.56.ex4)
[<button class="btn btn-info">Download v2.56.a for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.56.a.ex5)


<br />

### 2023.07.20-08.18 (2.55)
* [+] [Cancel TakeProfit if both buy and sell are open]({{site.baseurl}}/docs/follow-up#cancel-takeprofit-if-both-buy-and-sell-are-open)
* [+] [Disable TrailingStop if both buy and sell are open]({{site.baseurl}}/docs/follow-up#disable-trailingstop-if-both-buy-and-sell-are-open)
* [+] Lot increasing mode: [Last deal lot * distance * coeff]({{site.baseurl}}/docs/martingale#lot-increasing-mode)
* [+] [d'Alembert]({{site.baseurl}}/docs/lot#dalembert-money-management-system): Units Multiplier is also applied after loss
* [*] [Risk per currency](/docs/risk-per-currency): invalid pointer access error fixed
* [+] Active Periods: [Max activations number]({{site.baseurl}}/docs/active-periods#max-activations-number)
* [+] Active Periods: [Activate after trades number <=]({{site.baseurl}}/docs/active-periods#activation-event-and-activation-value)
* [*] Partial close: [Close profit itself]({{site.baseurl}}/docs/partial-close#close-profit-itself) works with anti-martingale orders
* [+] [Line Filters]({{site.baseurl}}/docs/signals-and-filters#line-filters) #1-3
* [+] Risk Per Currency: [Max Positions Total (all symbols)](/docs/risk-per-currency#max-positions-total-all-symbols)
* [+] Risk Per Currency: [Consider only one position per EA (symbol/magic/type)](/docs/risk-per-currency#consider-only-one-position-per-ea-symbolmagictype)
* [*] [Apply martin after closed loss]({{site.baseurl}}/docs/lot#apply-martin-after-closed-loss), [d'Alembert]({{site.baseurl}}/docs/lot#dalembert-money-management-system): new account high detection fixed
* [+] Partial Close: [Sort By Profit]({{site.baseurl}}/docs/partial-close#sort-by-profit) parameter
* [*] Lot increasing mode: [Sum: previous lot + adding]({{site.baseurl}}/docs/martingale#lot-increasing-mode) fixed
* [*] [Period Limits](/docs/period-limits) fixed
* [+] MA Filters: [Max Distance / Angle value]({{site.baseurl}}/docs/signals-and-filters#max-distance--angle-value)
* [+] Line Filters: [Max Distance value]({{site.baseurl}}/docs/signals-and-filters#max-distance-value)

[<button class="btn btn-success">Download v2.55 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.55.ex5)
[<button class="btn btn-primary">Download v2.55 for MT4</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.55.ex4)

<br />

### 2023.04.27-07.06 (2.54)
* [+] [Individual BreakEven](/docs/individual-follow-up#individual-breakeven)
* [+] 3rd [CustomIndy signal](/docs/signals-and-filters#custom-indicators)
* [+] 4th ActivePeriod
* [+] ActivePeriod for BreakEven, TrailingStop, and Individual BreakEven
* [*] Open trade by panel button: if price is above the highest buy open price / below the lowest sell open price, anti-martingale trade is open (with the corresponding settings)
* [*] BE lines are drawn on background, so SL line can be selected even if it is on the same level
* [+] Fibo signals: MACD bars for extremums detection (0 - don't use MACD)
* [*] Martin and anti-martin: Step increase coefficient can be disabled by setting it to 0
* [+] Hedge: Min distance from the main order (points)
* [+] d'Alembert money management system
* [+] d'Alembert: Units Multiplier

[<button class="btn btn-success">Download v2.54 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.54.ex5)
[<button class="btn btn-primary">Download v2.54 for MT4</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.54.ex4)

<br />

### 2023.04.12-04.26 (2.53)
* [+] ADX: Buy/sell when ADX >= level
* [+] ADX: Buy on +DI >= level / Sell on -DI >= level
* [+] StopLoss reduce every bar K (0 - disable)
* [+] StopLoss: Start reducing after bars
* [+] StopLoss min size (points)
* [*] "Buy above MA / Sell below MA" and "Buy on cross UP / Sell on cross DN" modes were deprecated. Use "Buy below MA / Sell above MA" and "Buy on cross DN / Sell on cross UP" with "Reverse mode" = true instead.
* [*] "Buy on cross DN / Sell on cross UP" mode is refactored to work correctly (in the previous version, the whole previous bar had to be above/below the MA).
* [+] "Buy on rising MA / Sell on falling MA" mode added
* [+] "Reverse mode" and "Use closed bars only" parameters added for all signal types
* [+] MACD filters: Signal Level

{% include alert.html type="warning" title="Warning" content="All sets using MA filters with these 2 modes must be updated!!!" %}

[<button class="btn btn-success">Download v2.53 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.53.ex5)
[<button class="btn btn-primary">Download v2.53 for MT4</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.53.ex4)

<br />

### 2023.02.11-03.24 (2.52)
* [+] Max profit to close on signal
* [+] [Active Periods](/docs/active-periods)
* [+] Min profit to close on signal fix
* [*] TDI fix (MT5 tester only)
* [*] TrailingStop works correctly with enabled "Allow dragging the lines to modify SL/TP" in the visual mode of MT5
* [*] "... line has been moved to 0" message fixed
* [+] Oscillators: Reversal signal type
* [+] Anti-martingale: Min pause between trades (in bars of Signal TF)
* [+] Anti-martingale: Use martingale signal for anti-martin trades

[<button class="btn btn-success">Download v2.52 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.52.ex5)
[<button class="btn btn-primary">Download v2.52 for MT4</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.52.ex4)

<br />

### 2022.10.14-2023.01.07 (2.50)
* [+] Pending entry: Delete on position close
* [+] Lot increasing mode: 1st deal lot * distance * coeff
* [*] SL and TP are not changed by EA after manual modification until the next recalculation (opening a new order, changing swap, etc.)
* [*] SL and TP are executed by market in UseVirtualSL/TP mode only
* [+] Fix volatility on 1st position open
* [+] Allow dragging the lines to modify SL/TP
* [+] Expert Comment is shown in the panel header
* [*] [Apply martin after closed loss]({{site.baseurl}}/docs/lot#apply-martin-after-closed-loss) works correctly with pending orders
* [+] Hedge works like a main series with common management rules but with its own entry rules

{% include alert.html type="warning" title="Warning" content="All sets with enabled Auto-hedge must be reviewed!" %}

[<button class="btn btn-success">Download v2.50 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.50.ex5)
[<button class="btn btn-primary">Download v2.50 for MT4</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.50.ex4)

<br />

### 2022.10.07 (2.49)
* [+] EveryDay session duration (mins) (0 - use end hour and minute)
* [+] 2 [CustomIndy signals](/docs/signals-and-filters#custom-indicators)
* [+] Spread filter: apply to first/apply to martin
* [+] BreakEven
* [+] [Risk per currency](/docs/risk-per-currency)
* [*] [GUI](/docs/gui): refresh is fixed for enabled Stop Till Tomorrow After Close
* [*] AutoHedge deals are closed with main series if it is closed by non-virtual SL or TP
* [*] [News filter](/docs/news): testing works correct for the last month

[<button class="btn btn-success">Download v2.49 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.49.ex5)
[<button class="btn btn-primary">Download v2.49 for MT4</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.49.ex4)

<br />

### 2022.07.02 (2.48)
* [+] GlobalAccount StopLoss
* [+] Period Limits
* [+] "Set description" parameter
* [+] MACD filter: "Main cross 0" and "Signal cross 0" modes

[<button class="btn btn-success">Download v2.48 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.48.ex5)
[<button class="btn btn-primary">Download v2.48 for MT4</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.48.ex4)

<br />

### 2022.05.20 (2.47)
* [*] First order can be opened on the same tick when the "Partial close" closes all open orders (works like v2.43 and earlier versions)
* [+] Lot: "Amount in base currency" mode
* [+] "Use only opened trades for time filters" (set true to make "New deal on the end of the bar only" and "Min pause between trades" working like in 2.45)

[<button class="btn btn-success">Download v2.47 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.47.ex5)
[<button class="btn btn-primary">Download v2.47 for MT4</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.47.ex4)

<br />

### 2022.04.28 (2.46)
* [*] "New deal on the end of the bar only" and "Min pause between trades" work correctly even if last martin trade was closed (and some of previous ones are still opened)
* [+] Partial close: Close profit itself
* [+] TrailingStop: Decrease every minutes, Decrease coefficient and Decrease start after minutes
* [*] TrailingStop: Min/max size parameter replaced with 2 separate parameters: Min size and Max size
* [+] Martin: "Change step after order #" and "Change step by coefficient"

{% include alert.html type="warning" title="Warning" content="Set files from version 2.45 with non-zero 'Min/max size' must be revised!" %}

[<button class="btn btn-success">Download v2.46 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.46.ex5)
[<button class="btn btn-primary">Download v2.46 for MT4</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.46.ex4)

<br />

### 2022.04.21 (2.45)
* [+] TrailingStop: Increase every, Increase size
* [+] TrailingStop: Min/max size
* [+] GlobalAccountClose: Stop Till Tomorrow After Close
* [+] ADX filter

[<button class="btn btn-success">Download v2.45 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.45.ex5)
[<button class="btn btn-primary">Download v2.45 for MT4</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.45.ex4)

<br />

### 2022.03.12 (2.44)
* [+] Partial close: Close any with any
* [+] Directional change filter
* [*] “Delete if opposite trade is open” works with enabled pending entry only
* [+] Big candle max size

[<button class="btn btn-success">Download v2.44 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.44.ex5)
[<button class="btn btn-primary">Download v2.44 for MT4</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.44.ex4)

<br />

### 2022.02.02 (2.43)
* [+] Improved ZZ signal with visualization
* [+] Binance: more stable connection to the Binance Trade Manager

[<button class="btn btn-success">Download v2.43 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.43.ex5)

<br />

### 2022.01.22 (2.42)
* [*] Binance: correct work with MT connected to netting account
* [*] Correct volatility values on start
* [*] Pending entry: "Disable if opposite trade is open" renamed to "Enter by market if opposite trade is open"
* [+] Pending entry: Delete if opposite trade is open
* [*] MACD and HMA indicators fixed (MT5)

[<button class="btn btn-success">Download v2.42 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.42.ex5)
[<button class="btn btn-primary">Download v2.42 for MT4</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.42.ex4)

<br />

### 2021.12.10 (2.40-2.41)
* [+] Ready to trade crypto on Binance (MT5 only, [details are here](https://t.me/BinanceMT5))
* [*] Fix for Roboforex accounts with empty Orders history (MT5)

[<button class="btn btn-success">Download v2.40 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.40.ex5)
[<button class="btn btn-success">Download v2.41 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.41.ex5)

<br />

### 2021.11.14 (2.39)
* [+] Max floating loss and Min margin level % for 1st trade
* [+] Virtual StopLoss can be executed only on good spread (if Spread filter enabled)
* [*] Volatility calculation on different time frames fixed
* [*] "Min TakeProfit size" and "Anti-StopLoss min size" fixed
* [*] Global Account TrailingStop and TargetProfit: withdrawals and deposits are handled correctly
* [*] Global Account TrailingStop works correctly after closed loss
* [*] Global Account Close works correctly with separate in/out commission

[<button class="btn btn-success">Download v2.39 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.39.ex5)
[<button class="btn btn-primary">Download v2.39 for MT4</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.39.ex4)

<br />

### 2021.09.23 (2.38)
* [+] Max step size (points) for martingale and anti-martingale
* [*] Recompiled with correct MT5 build

[<button class="btn btn-success">Download v2.38 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.38.ex5)
[<button class="btn btn-primary">Download v2.38 for MT4</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.38.ex4)

<br />

### 2021.09.06 (2.37)
* [+] Pending entry: Disable if opposite trade is open
* [+] Anti-martingale: Allow TakeProfit for anti-martin trades
* [+] Tester withdrawal
* [+] "Signal to open" message is sent if neither a market order nor a pending order is open
* [*] Smart "Max floating loss" and "Min margin level %" alerts
* [*] Testing speed improvement
* [*] Safer default settings

[<button class="btn btn-success">Download v2.37 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.37.ex5)
[<button class="btn btn-primary">Download v2.37 for MT4</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.37.ex4)

<br />

### 2021.08.04 (2.36)
* [+] Custom step coefficients
* [+] Auto-hedge on DrawDown %
* [+] "Open hedge on" parameter for each filter
* [+] Hedge: Close main series by opposite main series
* [*] Hedge: Allow close both ways fixed

[<button class="btn btn-success">Download v2.36 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.36.ex5)
[<button class="btn btn-primary">Download v2.36 for MT4</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.36.ex4)

<br />

### 2021.07.15 (2.35)
* [+] DTrend filter
* [*] "Custom lot coefficients" fixed
* [+] Sum TakeProfit (account currency)
* [+] HMA as MA mode in MA filters
* [+] 2nd MACD filter
* [+] MACD filters with customizable MA methods
* [+] Sum TakeProfit works if both buy and sell are open (new parameter)
* [+] Oscillators: MA above/below signal type
* [+] Oscillators: UseClosedBars parameter
* [+] MACD: "Buy on Signal > 0 / Sell on Signal < 0" mode
* [+] MACD: "Buy on Main > Signal and Signal < 0 / Sell on Main < Signal and Signal > 0" mode

[<button class="btn btn-success">Download v2.35 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.35.ex5)
[<button class="btn btn-primary">Download v2.35 for MT4</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.35.ex4)

<br />

### 2021.06.12 (2.34)
* [+] GlobalAccount TrailingStop
* [+] GlobalAccount TargetProfit restarts if all positions are closed

[<button class="btn btn-success">Download v2.34 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.34.ex5)
[<button class="btn btn-primary">Download v2.34 for MT4</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.34.ex4)

<br />

### 2021.06.10 (2.33)
* [+] Hedge deal with separate magic
* [+] Auto-hedge works with any "Trade direction"
* [*] Hedge deal opening with disabled GUI fixed
* [*] Martingale and Anti-martingale: max trades, lot and step are calculated using its own orders (not all orders)
* [+] "Custom lot coefficients" Lot increasing mode

{% include alert.html type="warning" title="Warning" content="All sets with enabled 'Auto-hedge after order' or 'Allow both Martin and Anti-martin' must be reviewed!" %}

[<button class="btn btn-success">Download v2.33 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.33.ex5)
[<button class="btn btn-primary">Download v2.33 for MT4</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.33.ex4)

<br />

### 2021.06.05 (2.32)
* [+] [GUI](/docs/gui) works in tester visual mode!
* [+] [Soft Martin](https://communitypowerea.userecho.com/en/communities/1/topics/318-position-cutter-pc-reduce-the-lot-size-by-previous-lot-size-in-the-sequence) Lot increasing mode
* [+] [Max lot per 1000](https://communitypowerea.userecho.com/en/communities/1/topics/196-max-lot-option-max-lot-per-1000)
* [+] Partial close: [Min part of losing order to close (%)](https://communitypowerea.userecho.com/en/communities/1/topics/242-split-an-order-for-partial-close)
* [+] [Allow both Martin and Anti-martin](https://communitypowerea.userecho.com/en/communities/1/topics/71-anti-martingale-and-martingale-combination) — allows new martingale deals if anti-marin is opened and vice versa. "TakeProfit", "BreakEven after order #" and "PartialClose" work if the last deal is not anti-martingale only.
* [+] Hedge: Increase lot after order #
* [+] Hedge: Close partial after order #
* [+] Hedge: Allow individual close
* [+] Hedge: Close with main series
* [+] Hedge: Max auto-hedge orders number
* [+] Hedge: Max profitable orders to close at the same time
* [+] Hedge: Allow close both ways (long series can close short series)
* [+] Hedge: Min profit to close (% from opposite loss)
* [*] [News filter](/docs/news) modes renamed
* [*] Global StopLoss and Global TakeProfit renamed to Sum StopLoss and Sum TakeProfit
* [*] Global Account Close works in tester

[<button class="btn btn-success">Download v2.32 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.32.ex5)
[<button class="btn btn-primary">Download v2.32 for MT4</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.32.ex4)

<br />

### 2021.05.08 (2.31)
* [+] Min margin level %
* [*] Trades made in 1 second are analyzed by the EA correctly.
* [*] BreakEven button moves SL/TP to the BreakEven level even if it is worse (less profitable) than current SL/TP level
* [+] Global Account TakeProfit (in account currency / in %)
* [+] Global Account TargetProfit (in account currency / in %)
* [+] All pips parameters can be set like coefficient to volatility (min/max value accepted):

  * Pending entry: Distance to order and Cancel after distance
  * StopLoss size
  * TakeProfit size
  * Min profit to close on signal
  * Martingale Step size
  * Anti-martingale Step size
  * Anti-StopLoss size
  * TrailingStop size
  * Trailing Step
  * Start trailing after
  <br/><br/>

  ATR for martingale and anti-martingale steps removed (use Volatility instead of ATR).

  Martingale and anti-martingale mode now can be enabled or disabled only.

  To use Step like volatility use the "Step size calc mode" parameter.

  To increase step size with every order use the "Step increase coefficient" parameter (set 1 to use fixed step).

{% include alert.html type="warning" title="Warning" content="All sets with martingale or anti-martingale modes enabled must be reviewed!<br/>
 - 'ATR * coefficient' mode must be replaced with 'Martingale enabled', 'Step size calc mode' must be set to 'Coefficient to volatility', ATR parameters must be set in the corresponding section.<br/>
 - 'Previous step * coefficient' mode must be replaced with 'Martingale enabled'. No other changes are needed.<br/>
 - 'Step increase coefficient' for 'Fixed step' mode must be set 1.
" %}

[<button class="btn btn-success">Download v2.31 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.31.ex5)
[<button class="btn btn-primary">Download v2.31 for MT4</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.31.ex4)

<br />

### 2021.04.19 (2.30)
* [+] ZigZag Filter
* [+] "Open on", "Open martin on", "Close on" and "Partial close on" options for the [News filter](/docs/news)
* [+] Alert on first signal
* [+] First signal sound is played (alert is shown, Grammy message is sent) even if trading is disabled (or checkbox is unchecked)
* [+] "Logistic Growth" Lot increasing mode
* [+] "Auto-hedge after order" always executes like market-order

{% include alert.html type="warning" title="Warning" content="All sets with 'Auto-hedge after order' and Pending entry enabled must be reviewed!" %}

[<button class="btn btn-success">Download v2.30 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.30.ex5)
[<button class="btn btn-primary">Download v2.30 for MT4</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.30.ex4)

<br />

### 2021.04.03 (2.29)
* [+] [News filter](/docs/news)
* [+] [Max Relative DD](/docs/backtesting-and-optimization#custom-optimization-criterion) as optimization criterion
* [*] BreakEven button works with non-virtual SL/TP too
* [+] Orders on chart: aggregated profits on history
* [+] Lot increasing mode "Martin Sum": previous lots sum * coefficient [1-2-6-18-54-...]
* [+] Volatility Filter based on tick volume
* [+] Parabolic SAR filter
* [+] 3rd Oscillator filter
* [+] Lot: "Fixed size per 1000", "per 1000 USD": thousands are rounded down
* [+] TEMA as MA type for all MA filters
* [+] Min step size (for ATR based step size calculation)
* [*] Visual testing speed increased

[<button class="btn btn-success">Download v2.29 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.29.ex5)
[<button class="btn btn-primary">Download v2.29 for MT4</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.29.ex4)

<br />

### 2021.03.03 (2.28)
* [+] Automatic orders drawing and "Show orders" button on panel

[<button class="btn btn-success">Download v2.28 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.28.ex5)
[<button class="btn btn-primary">Download v2.28 for MT4</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.28.ex4)

<br />

### 2021.03.02 (2.27)
* [+] Use virtual StopLoss
* [+] Custom commission (in account currency per lot) (0 - disable)
* [*] AntiStopLoss works if AntiMartingale is enabled only
* [*] PauseAfterLoss fixed for some cases
* [+] Use virtual TakeProfit
* [+] "[R squared](/docs/backtesting-and-optimization#custom-optimization-criterion)" as custom optimization criterion
* [+] BreakEven After Order: MinProfit (points)
* [+] New TDI filter with all inputs

{% include alert.html type="warning" title="Warning" content="All sets with disabled TDI filter must be updated (now it is enabled by default)!" %}

[<button class="btn btn-success">Download v2.27 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.27.ex5)
[<button class="btn btn-primary">Download v2.27 for MT4</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.27.ex4)

<br />

### 2021.02.02 (2.26)
* [+] Indicator showing by click on signal
* [+] Parameters grouped for easier optimization
* [+] Sounds on position opening and closing added
* [*] Loading after terminal crash is fixed (MT4)

[<button class="btn btn-success">Download v2.26 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.26.ex5)
[<button class="btn btn-primary">Download v2.26 for MT4</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.26.ex4)

<br />

### 2021.01.15 (2.25)
* [+] "Close on" parameter for Big candle filter
* [+] 3 new types of MACD filter:
    * Buy on Main > Signal / Sell on Main < Signal
    * Main and Signal cross
    * Main and Signal cross >/< 0
* [+] "Partial close on" parameter for each filter
* [+] Individual schedule for each day of week (set equal start and end hour/minute to disable the whole day)
* [+] Fibo filter: "Check Interval” parameter added, "Use closed bars" parameter is now manage FIBO recalculation frequency 
* [+] Fibo filter: "On trend reversal" mode
* [+] EveryDay close time
* [+] "Apply schedule to" parameter
* [+] Auto-hedge after order

{% include alert.html type="warning" title="Warning" content="Please, review all set-files with Fibo-filter activated!" %}

[<button class="btn btn-success">Download v2.25 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.25.ex5)
[<button class="btn btn-primary">Download v2.25 for MT4</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.25.ex4)

<br />

### 2020.12.31 (2.24)
* [*] Increased testing speed for strategies with huge number of trades
* [*] TMA and FRAMA can work without indicator installed
* [+] Fibo filter: "On retracement + opposite direction" mode added
* [+] [GUI](/docs/gui): concept updated: pending entry has a lower priority than market entry
* [+] [GUI](/docs/gui): profit in % added
* [+] [GUI](/docs/gui): anti-martingale lines added
* [*] PauseAfterLoss fixed
* [*] MartingailOnTheBarEnd fixed
* [+] One more Fibo retracement filter added

[<button class="btn btn-success">Download v2.24 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.24.ex5)
[<button class="btn btn-primary">Download v2.24 for MT4</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.24.ex4)

<br />

### 2020.12.10 (2.23)
* [+] Pause after loss (in bars of Signal TF)
* [+] Reduce TakeProfit after minutes
* [+] Max floating loss
* [+] Global StopLoss in account currency
* [+] TMA, FRAMA and JMA as base indicators for MA filters 
  * Indicators for visualization can be downloaded [here]({{site.baseurl}}/docs/FAQ/indicators)
  * To visualize "TMA channel" you can use [this indy](https://www.mql5.com/en/code/22350). But it is only one possible option from hundreds available in the EA.
* [+] Partial close: Min profit to close (% from balance)
* [*] Partial close trying to close as many trades as possible
* [*] [GUI](/docs/gui): visual testing speed increased
* [+] [GUI](/docs/gui): "refresh interval" parameter for even faster visual test (try values between 60-300)

[<button class="btn btn-success">Download v2.23 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.23.ex5)
[<button class="btn btn-primary">Download v2.23 for MT4</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.23.ex4)

<br />

### 2020.12.03 (2.22)
* [+] [GUI](/docs/gui): tooltips in status-bar
* [*] Volatility Filter fixed (didn't work since 2.19)

[<button class="btn btn-success">Download v2.22 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.22.ex5)
[<button class="btn btn-primary">Download v2.22 for MT4</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.22.ex4)

<br />

### 2020.11.30 (2.21)
* [+] [GUI](/docs/gui): One click trading with Shift button pressed
* [+] New deal on the new bar (for first deal)
* [+] Trade both sides if all signals are disabled
* [+] Oscillators: Stochastic D as an indicator

[<button class="btn btn-success">Download v2.21 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.21.ex5)
[<button class="btn btn-primary">Download v2.21 for MT4</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.21.ex4)

<br />

### 2020.11.03 (2.20)
* [+] Min profit to close on signal (points)
* [+] Anti-StopLoss mode, reduce size, reduce coefficient, min size,
* [+] Negative Anti-StopLoss values accepted
* [+] "Allow martingale deals on signal only" replaced with "Open martin on" parameter for each filter.
* [+] Close partial after order # and Min profit to close (in account currency)
* [+] TP, TS and AntiSL: "From first open price" mode
* [+] "StopLoss mode" parameter
* [+] [GUI](/docs/gui): One click trading without confirmation (enables by left button on the top of the panel)
* [+] Martingale: "New deal on the end of the bar only"
* [+] "Lot increasing mode" for Martin and Anti-martin
* [*] Fixed lot per 1000 USD mode fixed
* [*] Checkboxes save their states on chart symbol and Expert Id change

[<button class="btn btn-success">Download v2.20 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.20.ex5)
[<button class="btn btn-primary">Download v2.20 for MT4</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.20.ex4)

<br />

### 2020.10.14 (2.19)
* [+] "Open on" parameter for each filter. Can be Individual/Collective.
* [+] Allow martingale deals on signal only
* [+] Window transparency parameter
* [+] [GUI](/docs/gui): scaling for 4K monitors
* [*] "Too long GV name" error fixed
* [*] "Ticket #xxx disappeared from the terminal" error fixed
* [+] "Trade is disabled" and "Not enough money" alerts only once per 5 minutes

{% include alert.html type="warning" title="Warning" content="All sets using non-default open signals must be updated!!!" %}

[<button class="btn btn-success">Download v2.19 for MT5</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.19.ex5)
[<button class="btn btn-primary">Download v2.19 for MT4</button>]({{site.baseurl}}/assets/EAs/CommunityPower 2.19.ex4)

<br />

### 2020.09.08 (2.18)
* [+] MA filter: "on cross" mode added
* [+] Min pause between trades (in bars of Signal TF)
* [+] Close on BreakEven after order #
* [+] Pending entry by LIMIT orders added
* [*] Pending buy-orders cancellation by opposite signal fixed for "in profit only" modes
* [*] [GUI](/docs/gui): blinking fixed
* [*] BreakEven button moves TP in both sides (up and down)
* [+] "Join the Community" button added

{% include alert.html type="warning" title="Warning" content="Pending entry is controlled by parameter 'Pending entry type' starting from this version. All sets that use Pending entry must be updated ('Pending entry type' must be set = 'Entry with STOP order')!!!" %}

<br />

### 2020.08.26 (2.17)
* [+] Global TakeProfit (% from balance)
* [+] Fibo retracement filter

<br />

### 2020.08.19 (2.16)
* [+] "Close on" parameter for each filter. Can be Individual/Collective.
* [+] Momentum indy available in Oscillator filters
* [+] Peace filter renamed to MACD and improved with 2 growing modes
* [+] TrailingStep parameter added

{% include alert.html type="warning" title="Warning" content="All sets using 'Close on signal', 'Close on filter' mode or Peace filter must be updated!!!" %}

<br />

### 2020.08.06 (2.15)
* [+] Volatility filter
* [+] MA below/above filters are replaced by 3 universal MA filters
* [+] Distance for MA filters can be calculated using Volatility indicator

{% include alert.html type="warning" title="Warning" content="All sets using MA filters must be updated!!!" %}

<br />

### 2020.07.22 (2.14)
* [+] [GUI](/docs/gui)
* [+] Reverse mode and Use only closed bars for IdentifyTrend, TDI and Peace filters
* [+] Extended info messages
* [*] Pending entry works correctly with stop-level
* [*] "Manage manual trades" mode fixed

<br />

### 2020.06.24 (2.12)
* [+] Anti-martingale mode
* [+] Big candle filter

<br />

### 2020.05.28 (2.11)
* [*] Zero divide error fixed for instruments with empty TickValue
* [+] StopLoss, TakeProfit, BreakEven and NextOrder levels on chart
* [+] BreakEven Alert after order
* [+] TakeProfit reduce size, reduce coefficient and Min TakeProfit size

<br />

### 2020.05.18 (2.10)
* [+] Cancel on opposite signal
* [+] First lot type: fixed, risk %, margin % (in addition to current "lot per 1000")

<br />

### 2020.05.12 (2.09)
* [*] Signal TimeFrame parameter added.
* [+] Pending entry

{% include alert.html type="warning" title="Warning" content="Please, set Signal TimeFrame equal to Oscillator TimeFrame in all your set-files from previous versions!" %}

<br />

### 2020.05.06 (2.08)
* [*] TrailngStop fixed. 

{% include alert.html type="warning" title="Warning" content="Check all your sets with TrailingStop activated before launching EA live!" %}

<br />

### 2020.05.04 (2.07)
* [-] The third "MA below" and "MA above" filters removed
* [*] Commissions and swaps are taken into account for sell-positions
* [*] "Messages to Grammy" are allowed only if trading is enabled
* [+] [Apply martin after closed loss]({{site.baseurl}}/docs/lot#apply-martin-after-closed-loss)
* [+] Global StopLoss in % from current balance

<br />

### 2020.04.24 (2.06)
* [+] "Allow messages to Grammy" parameter
* [+] One more Oscillator filter
* [*] "MA below" and "MA above" filters renamed to "Price below MA" and "Price above MA"
* [+] Two more "MA below" and “MA above" filters

<br />

### 2020.04.21 (2.05)
* [+] Version [for MT5](https://www.mql5.com/en/market/product/48493)
* [+] [Messages to the Telegram](https://communitypowerea.com/docs/notifications#notifications-settings) on openings and closings
* [+] Spread filter (current and average) on positions opening

<br />

### 2020.04.16 (2.04)
* [+] Expert Comment
* [+] [Allow hedge](/docs/hedge#allow-hedge)
* [+] Manage manual trades
* [+] Every Day schedule, Friday stop time, Friday close time, Monday start time. All parameters are in GMT! For correct testing proper GMT shift and DST mode must be set.
* [+] Last December day to trade / First January day to trade

<br />

### 2020.04.14 (2.03)
* [+] FXGAL3 filter replaced by IdentifyTrend filter
* [*] StopLoss fixed in "Martingale disabled" mode

<br />

### 2020.04.09 (2.02)
* [+] MA below and MA above filters

<br />

### 2020.04.09 (2.01)
* [+] Close on filter
* [+] Martingale type (dynamic step between orders)
* [*] Commissions and swaps are taken into account

<br />

### 2020.04.07 (2.0)
* [+] Trade direction
* [+] Start lot per 1000 of balance
* [+] Max lot
* [+] Max trades, Lot coefficient, Step (martingale)
* [+] Close on opposite signal

<br />

### 2020.04.04 (1.01)
* [+] TDI Filter

<br />

### 2020.04.03 (1.0)
* [+] First release

<br />
