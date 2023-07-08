---
layout: page
title: Versions history
description: Here you can find the list of all versions of the bot and the list of changes in each version.
permalink: /docs/versions-history
---

# Versions history

### 2020.04.03 (1.0)
* [+] First release

<br />

### 2020.04.04 (1.01)
* [+] TDI Filter

<br />

### 2020.04.07 (2.0)
* [+] Trade direction
* [+] Start lot per 1000 of balance
* [+] Max lot
* [+] Max trades, Lot coefficient, Step (martingale)
* [+] Close on opposite signal

<br />

### 2020.04.09 (2.01)
* [+] Close on filter
* [+] Martingale type (dynamic step between orders)
* [*] Commissions and swaps are taken into account

<br />

### 2020.04.09 (2.02)
* [+] MA below and MA above filters

<br />

### 2020.04.14 (2.03)
* [+] FXGAL3 filter replaced by IdentifyTrend filter
* [*] StopLoss fixed in "Martingale disabled" mode

<br />

### 2020.04.16 (2.04)
* [+] Expert Comment
* [+] Allow hedge
* [+] Manage manual trades
* [+] Every Day schedule, Friday stop time, Friday close time, Monday start time. All parameters are in GMT! For correct testing proper GMT shift and DST mode must be set.
* [+] Last December day to trade / First January day to trade

<br />

### 2020.04.21 (2.05)
* [+] [Version for MT5](https://www.mql5.com/en/market/product/48493)
* [+] Messages to the Telegram on openings and closings (Grammy must be launched on the same terminal!)
* [+] Spread filter (current and average) on positions opening

<br />

### 2020.04.24 (2.06)
* [+] "Allow messages to Grammy" parameter
* [+] One more Oscillator filter
* [*] "MA below" and "MA above" filters renamed to "Price below MA" and "Price above MA"
* [+] Two more "MA below" and “MA above" filters

<br />

### 2020.05.04 (2.07)
* [-] The third "MA below" and "MA above" filters removed
* [*] Commissions and swaps are taken into account for sell-positions
* [*] "Messages to Grammy" are allowed only if trading is enabled
* [+] New type of martingale — lot coefficient applied after each loss ("Apply after closed loss" parameter)
* [+] Global StopLoss in % from current balance

<br />

### 2020.05.06 (2.08)
* [*] TrailngStop fixed. 

{% include alert.html type="warning" title="Warning" content="Check all your sets with TrailingStop activated before launching EA live!" %}

<br />

### 2020.05.12 (2.09)
* [*] Signal TimeFrame parameter added.
* [+] Pending entry

{% include alert.html type="warning" title="Warning" content="Please, set Signal TimeFrame equal to Oscillator TimeFrame in all your set-files from previous versions!" %}

<br />

### 2020.05.18 (2.10)
* [+] Cancel on opposite signal
* [+] First lot type: fixed, risk %, margin % (in addition to current "lot per 1000")

<br />

### 2020.05.28 (2.11)
* [*] Zero divide error fixed for instruments with empty TickValue
* [+] StopLoss, TakeProfit, BreakEven and NextOrder levels on chart
* [+] BreakEven Alert after order
* [+] TakeProfit reduce size, reduce coefficient and Min TakeProfit size

<br />

### 2020.06.24 (2.12)
* [+] Anti-martingale mode
* [+] Big candle filter

<br />

### 2020.07.22 (2.14)
* [+] GUI
* [+] Reverse mode and Use only closed bars for IdentifyTrend, TDI and Peace filters
* [+] Extended info messages
* [*] Pending entry works correctly with stop-level
* [*] "Manage manual trades" mode fixed

<br />

### 2020.08.06 (2.15)
* [+] Volatility filter
* [+] MA below/above filters are replaced by 3 universal MA filters
* [+] Distance for MA filters can be calculated using Volatility indicator

{% include alert.html type="warning" title="Warning" content="All sets using MA filters must be updated!!!" %}

<br />

### 2020.08.19 (2.16)
* [+] "Close on" parameter for each filter. Can be Individual/Collective.
* [+] Momentum indy available in Oscillator filters
* [+] Peace filter renamed to MACD and improved with 2 growing modes
* [+] TrailingStep parameter added

{% include alert.html type="warning" title="Warning" content="All sets using "Close on signal", "Close on filter" mode or Peace filter must be updated!!!" %}

<br />

### 2020.08.26 (2.17)
* [+] Global TakeProfit (% from balance)
* [+] Fibo retracement filter

<br />

### 2020.09.08 (2.18)
* [+] MA filter: "on cross" mode added
* [+] Min pause between trades (in bars of Signal TF)
* [+] Close on BreakEven after order #
* [+] Pending entry by LIMIT orders added
* [*] Pending buy-orders cancellation by opposite signal fixed for "in profit only" modes
* [*] GUI blinking fixed
* [*] BreakEven button moves TP in both sides (up and down)
* [+] "Join the Community" button added

{% include alert.html type="warning" title="Warning" content="Pending entry is controlled by parameter "Pending entry type" starting from this version. All sets that use Pending entry must be updated ("Pending entry type" must be set = "Entry with STOP order")!!!" %}

<br />

### 2020.10.14 (2.19)
* [+] "Open on" parameter for each filter. Can be Individual/Collective.
* [+] Allow martingale deals on signal only
* [+] Window transparency parameter
* [+] GUI scaling for 4K monitors
* [*] "Too long GV name" error fixed
* [*] "Ticket #xxx disappeared from the terminal" error fixed
* [+] "Trade is disabled" and "Not enough money" alerts only once per 5 minutes

{% include alert.html type="warning" title="Warning" content="All sets using non-default open signals must be updated!!!" %}

<br />

### 2020.11.03 (2.20)
* [+] Min profit to close on signal (points)
* [+] Anti-StopLoss mode, reduce size, reduce coefficient, min size,
* [+] Negative Anti-StopLoss values accepted
* [+] "Allow martingale deals on signal only" replaced with "Open martin on" parameter for each filter.
* [+] Close partial after order # and Min profit to close (in account currency)
* [+] TP, TS and AntiSL: "From first open price" mode
* [+] "StopLoss mode" parameter
* [+] GUI: One click trading without confirmation (enables by left button on the top of the panel)
* [+] Martingale: "New deal on the end of the bar only"
* [+] "Lot increasing mode" for Martin and Anti-martin
* [*] Fixed lot per 1000 USD mode fixed
* [*] Checkboxes save their states on chart symbol and Expert Id change

<br />

### 2020.11.30 (2.21)
* [+] GUI: One click trading with Shift button pressed
* [+] New deal on the new bar (for first deal)
* [+] Trade both sides if all signals are disabled
* [+] Oscillators: Stochastic D as an indicator

<br />

### 2020.12.03 (2.22)
* [+] GUI: tooltips in status-bar
* [*] Volatility Filter fixed (didn't work since 2.19)

<br />

### 2020.12.10 (2.23)
* [+] Pause after loss (in bars of Signal TF)
* [+] Reduce TakeProfit after minutes
* [+] Max floating loss
* [+] Global StopLoss in account currency
* [+] TMA, FRAMA and JMA as base indicators for MA filters
Indicators for visualization can be downloaded from Google Drive (ToDo: add link)
To visualize "TMA channel" you can use this indy (ToDo: add link). But it is only one possible option from hundreds available in the EA.
* [+] Partial close: Min profit to close (% from balance)
* [*] Partial close trying to close as many trades as possible
* [*] GUI: visual testing speed increased
* [+] GUI: "refresh interval" parameter for even faster visual test (try values between 60-300)

<br />

### 2020.12.31 (2.24)
* [*] Increased testing speed for strategies with huge number of trades
* [*] TMA and FRAMA can work without indicator installed
* [+] Fibo filter: "On retracement + opposite direction" mode added
* [+] GUI: concept updated: pending entry has a lower priority than market entry
* [+] GUI: profit in % added
* [+] GUI: anti-martingale lines added
* [*] PauseAfterLoss fixed
* [*] MartingailOnTheBarEnd fixed
* [+] One more Fibo retracement filter added


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

<br />

### 2021.02.02 (2.26)
* [+] Indicator showing by click on signal
* [+] Parameters grouped for easier optimization
* [+] Sounds on position opening and closing added
* [*] Loading after terminal crash is fixed (MT4)

<br />

### 2021.03.02 (2.27)
* [+] Use virtual StopLoss
* [+] Custom commission (in account currency per lot) (0 - disable)
* [*] AntiStopLoss works if AntiMartingale is enabled only
* [*] PauseAfterLoss fixed for some cases
* [+] Use virtual TakeProfit
* [+] "R squared" as custom optimization criterion
* [+] BreakEven After Order: MinProfit (points)
* [+] New TDI filter with all inputs
{% include alert.html type="warning" title="Warning" content="All sets with disabled TDI filter must be updated (now it is enabled by default)!" %}

<br />

### 2021.03.03 (2.28)
* [+] Automatic orders drawing and "Show orders" button on panel

<br />

### 2021.04.03 (2.29)
* [+] News filter
* [+] Max Relative DD as optimization criterion
* [*] BreakEven button works with non-virtual SL/TP too
* [+] Orders on chart: aggregated profits on history
* [+] Lot increasing mode "Martin Sum": previous lots sum * coeff * [1-2-6-18-54-...]
* [+] Volatility Filter based on tick volume
* [+] Parabolic SAR filter
* [+] 3rd Oscillator filter
* [+] Lot: "Fixed size per 1000", "per 1000 USD": thousands are rounded down
* [+] TEMA as MA type for all MA filters
* [+] Min step size (for ATR based step size calculation)
* [*] Visual testing speed increased

<br />

### 2021.04.19 (2.30)
* [+] ZigZag Filter
* [+] "Open on", "Open martin on", "Close on" and "Partial close on" options for the News filter
* [+] Alert on first signal
* [+] First signal sound is played (alert is shown, Grammy message is sent) even if trading is disabled (or checkbox is unchecked)
* [+] "Logistic Growth" Lot increasing mode
* [+] "Auto-hedge after order" always executes like market-order

{% include alert.html type="warning" title="Warning" content="All sets with "Auto-hedge after order" and Pending entry enabled must be reviewed!" %}

<br />

### 2021.05.08 (2.31)
* [+] Min margin level %
* [*] Trades made in 1 second are analyzed by the EA correctly.
* [*] BreakEven button moves SL/TP to the BreakEven level even if it is worse (less profitable) than current SL/TP level
* [+] Global Account TakeProfit (in account currency / in %)
* [+] Global Account TargetProfit (in account currency / in %)
* [+] All pips parameters can be set like coefficient to volatility (min/max value accepted):

Pending entry: Distance to order and Cancel after distance
StopLoss size
TakeProfit size
Min profit to close on signal
Martingale Step size
Anti-martingale Step size
Anti-StopLoss size
TrailingStop size
Trailing Step
Start trailing after
ATR for martingale and anti-martingale steps removed (use Volatility instead of ATR).
Martingale and anti-martingale mode now can be enabled or disabled only.
To use Step like volatility use the "Step size calc mode" parameter.
To increase step size with every order use the "Step increase coefficient" parameter (set 1 to use fixed step).
**Warning! All sets with martingale or anti-martingale modes enabled must be reviewed!**
"ATR * coefficient" mode must be replaced with "Martingale enabled", "Step size calc mode" must be set to "Coefficient to volatility", ATR parameters must be set in the corresponding section.
"Previous step * coefficient" mode must be replaced with "Martingale enabled". No other changes are needed.
"Step increase coefficient" for "Fixed step" mode must be set 1.

<br />

### 2021.06.05 (2.32)
* [+] GUI works in tester visual mode!
* [+] Soft Martin Lot increasing mode
* [+] Max lot per 1000
* [+] Partial close: Min part of losing order to close (%)
* [+] Allow both Martin and Anti-martin — allows new martingale deals if anti-marin is opened and vice versa. "TakeProfit", "BreakEven after order #" and "PartialClose" work if the last deal is not anti-martingale only.
* [+] Hedge: Increase lot after order #
* [+] Hedge: Close partial after order #
* [+] Hedge: Allow individual close
* [+] Hedge: Close with main series
* [+] Hedge: Max auto-hedge orders number
* [+] Hedge: Max profitable orders to close at the same time
* [+] Hedge: Allow close both ways (long series can close short series)
* [+] Hedge: Min profit to close (% from opposite loss)
* [*] News filter modes renamed
* [*] Global StopLoss and Global TakeProfit renamed to Sum StopLoss and Sum TakeProfit
* [*] Global Account Close works in tester

<br />

### 2021.06.10 (2.33)
* [+] Hedge deal with separate magic
* [+] Auto-hedge works with any "Trade direction"
* [*] Hedge deal opening with disabled GUI fixed
* [*] Martingale and Anti-martingale: max trades, lot and step are calculated using its own orders (not all orders)
* [+] "Custom lot coefficients" Lot increasing mode<br/>
**Warning! All sets with enabled "Auto-hedge after order" or "Allow both Martin and Anti-martin" must be reviewed!**

<br />

### 2021.06.12 (2.34)
* [+] GlobalAccount TrailingStop
* [+] GlobalAccount TargetProfit restarts if all positions are closed

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

<br />

### 2021.08.04 (2.36)
* [+] Custom step coefficients
* [+] Auto-hedge on DrawDown %
* [+] "Open hedge on" parameter for each filter
* [+] Hedge: Close main series by opposite main series
* [*] Hedge: Allow close both ways fixed

<br />

### 2021.09.06 (2.37)
* [+] Pending entry: Disable if opposite trade is open
* [+] Anti-martingale: Allow TakeProfit for anti-martin trades
* [+] Tester withdrawal
* [+] "Signal to open" message is sent if neither a market order nor a pending order is open
* [*] Smart "Max floating loss" and "Min margin level %" alerts
* [*] Testing speed improvement
* [*] Safer default settings

<br />

### 2021.09.23 (2.38)
* [+] Max step size (points) for martingale and anti-martingale
* [*] Recompiled with correct MT5 build

<br />

### 2021.11.14 (2.39)
* [+] Max floating loss and Min margin level % for 1st trade
* [+] Virtual StopLoss can be executed only on good spread (if Spread filter enabled)
* [*] Volatility calculation on different time frames fixed
* [*] "Min TakeProfit size" and "Anti-StopLoss min size" fixed
* [*] Global Account TrailingStop and TargetProfit: withdrawals and deposits are handled correctly
* [*] Global Account TrailingStop works correctly after closed loss
* [*] Global Account Close works correctly with separate in/out commission

<br />

### 2021.12.10 (2.40-2.41)
* [+] Ready to trade crypto on Binance (MT5 only, details here)
* [*] Fix for Roboforex accounts with empty Orders history (MT5)

<br />

### 2022.01.22 (2.42)
* [*] Binance: correct work with MT connected to netting account
* [*] Correct volatility values on start
* [*] Pending entry: "Disable if opposite trade is open" renamed to "Enter by market if opposite trade is open"
* [+] Pending entry: Delete if opposite trade is open
* [*] MACD and HMA indicators fixed (MT5)

<br />

### 2022.02.02 (2.43)
* [+] Improved ZZ signal with visualization
* [+] Binance: more stable connection to the Binance Trade Manager

<br />

### 2022.03.12 (2.44)
* [+] Partial close: Close any with any
* [+] Directional change filter
* [*] “Delete if opposite trade is open” works with enabled pending entry only
* [+] Big candle max size

<br />

### 2022.04.21 (2.45)
* [+] TrailingStop: Increase every, Increase size
* [+] TrailingStop: Min/max size
* [+] GlobalAccountClose: Stop Till Tomorrow After Close
* [+] ADX filter

<br />

### 2022.04.28 (2.46)
* [*] "New deal on the end of the bar only" and "Min pause between trades" work correctly even if last martin trade was closed (and some of previous ones are still opened)
* [+] Partial close: Close profit itself
* [+] TrailingStop: Decrease every minutes, Decrease coefficient and Decrease start after minutes
* [*] TrailingStop: Min/max size parameter replaced with 2 separate parameters: Min size and Max size<br/>
**Warning! Set files from version 2.45 with non-zero "Min/max size" must be revised!**
* [+] Martin: "Change step after order #" and "Change step by coefficient"

<br />

### 2022.05.20 (2.47)
* [*] First order can be opened on the same tick when the "Partial close" closes all open orders (works like v2.43 and earlier versions)
* [+] Lot: "Amount in base currency" mode
* [+] "Use only opened trades for time filters" (set true to make "New deal on the end of the bar only" and "Min pause between trades" working like in 2.45)

<br />

### 2022.07.02 (2.48)
* [+] GlobalAccount StopLoss
* [+] Period Limits
* [+] "Set description" parameter
* [+] MACD filter: "Main cross 0" and "Signal cross 0" modes

<br />

### 2022.10.07 (2.49)
* [+] EveryDay session duration (mins) (0 - use end hour and minute)
* [+] 2 CustomIndy signals
* [+] Spread filter: apply to first/apply to martin
* [+] BreakEven
* [+] RiskPerCurrency
* [*] GUI refresh is fixed for enabled Stop Till Tomorrow After Close
* [*] AutoHedge deals are closed with main series if it is closed by non-virtual SL or TP
* [*] News: testing works correct for the last month

<br />

### 2022.10.14-2023.01.07 (2.50)
* [+] Pending entry: Delete on position close
* [+] Lot increasing mode: 1st deal lot * distance * coeff
* [*] SL and TP are not changed by EA after manual modification until the next recalculation (opening a new order, changing swap, etc.)
* [*] SL and TP are executed by market in UseVirtualSL/TP mode only
* [+] Fix volatility on 1st position open
* [+] Allow dragging the lines to modify SL/TP
* [+] Expert Comment is shown in the panel header
* [*] "Apply martin after closed loss" works correctly with pending orders
* [+] Hedge works like a main series with common management rules but with its own entry rules.<br/>
**Warning! All sets with enabled Auto-hedge must be reviewed!**

<br />

### 2023.02.11-03.24 (2.52)
* [+] Max profit to close on signal
* [+] Active Periods
* [+] Min profit to close on signal fix
* [*] TDI fix (MT5 tester only)
* [*] Active Periods are applied to close signals
* [*] TrailingStop works correctly with enabled "Allow dragging the lines to modify SL/TP" in the visual mode of MT5
* [*] "... line has been moved to 0" message fixed
* [+] Oscillators: Reversal signal type
* [+] Anti-martingale: Min pause between trades (in bars of Signal TF)
* [+] Anti-martingale: Use martingale signal for anti-martin trades

<br />

### 2023.04.12-04.26 (2.53)
* [+] ADX: Buy/sell when ADX >= level<br/>
* [+] ADX: Buy on +DI >= level / Sell on -DI >= level<br/>
* [+] StopLoss reduce every bar K (0 - disable)<br/>
* [+] StopLoss: Start reducing after bars<br/>
* [+] StopLoss min size (points)<br/>
* [*] "Buy above MA / Sell below MA" and "Buy on cross UP / Sell on cross DN" modes were deprecated. Use "Buy below MA / Sell above MA" and "Buy on cross DN / Sell on cross UP" with "Reverse mode" = true instead.<br/>
**Warning! All sets using MA filters with these 2 modes must be updated!!!**<br/>
* [*] "Buy on cross DN / Sell on cross UP" mode is refactored to work correctly (in the previous version, the whole previous bar had to be above/below the MA).<br/>
* [+] "Buy on rising MA / Sell on falling MA" mode added<br/>
* [+] "Reverse mode" and "Use closed bars only" parameters added for all signal types<br/>
* [+] MACD filters: Signal Level

<br />

### 2023.04.27-07.06 (2.54)
* [+] Individual BreakEven
* [+] 3rd CustomIndy signal
* [+] 4th ActivePeriod
* [+] ActivePeriod for BreakEven, TrailingStop, and Individual BreakEven
* [*] Open trade by panel button: if price is above the highest buy open price / below the lowest sell open price, anti-martingale trade is open (with the corresponding settings)
* [*] BE lines are drawn on background, so SL line can be selected even if it is on the same level
* [+] Fibo signals: MACD bars for extremums detection (0 - don't use MACD)
* [*] Martin and anti-martin: Step increase coefficient can be disabled by setting it to 0
* [+] Hedge: Min distance from the main order (points)
* [+] d'Alembert money management system (ToDo: add docs!)
* [+] d'Alembert: Units Multiplier
