---
layout: page
title: Signals and filters
description: Parameters of all Signals and filters
permalink: /docs/signals-and-filters
---

# Signals and filters

# Directional change filter

## Directional change filter type

[*(starting from v2.44)*](/docs/versions-history#20220312-244)

* **Disabled**: filter disabled
* **Change dir after loss**:
*   allows BUYs after profitable BUYs/after losing SELLs
*   allows SELLs after profitable SELLs/after losing BUYs


<hr>

# Big candle filter

## Big candle filter type, Big candle min size, Big candle max size, Big candle TimeFrame, Analyze current bar

[*(starting from v2.12)*](/docs/versions-history#20200624-212)
*(added in v2.44)*

Big candle filter analyzes candle size (current or previous, depending on **Analyze current bar** parameter) from the specified timeframe.

Can work in one of following modes:
* **Disabled**: filter disabled
* **Big candle in any direction**:
    * both BUYs and SELLs are allowed only if High - Low >= **Big candle min size** and High - Low <= **Big candle max size** (or max size = 0)
* **Co-directional big candle only**:
    * BUYs are allowed if High - Open >= **Big candle min size** and High - Open <= **Big candle max size** (or max size = 0)
    * SELLs are allowed if Open - Low >= **Big candle min size** and Open - Low <= **Big candle max size** (or max size = 0)
* **Opposite big candle only**:
    * BUYs are allowed if Open - Low >= **Big candle min size** and Open - Low <= **Big candle max size** (or max size = 0)
    * SELLs are allowed if High - Open >= **Big candle min size** and High - Open <= **Big candle max size** (or max size = 0)


<hr>

# Oscillator filters #1-3

## Filter type

Type of oscillator signal:
* **Disabled**: filter disabled.
* **Inside zone**:
    * BUYs are allowed if oscillator <= LevelDn
    * SELLs are allowed if oscillator >= LevelUp
* **Cross In**:
    * BUYs are allowed when oscillator crosses LevelDn downwards
    * SELLs are allowed when oscillator crosses LevelUp upwards
* **Cross Out**:
    * BUYs are allowed when oscillator crosses LevelDn upwards
    * SELLs are allowed when oscillator crosses LevelUp downwards
* **Cross MA**:
    * BUYs are allowed when oscillator crosses MA based on it's line below the LevelDn
    * SELLs are allowed when oscillator crosses MA based on it's line above the LevelUp ([Example](https://communitypowerea.userecho.com/en/communities/1/topics/113-cross-ma-mode-oscillators?redirect_to_reply=567#comment-567))
* **Above/below MA** *(starting from 2.35)*:
    * BUYs are allowed if oscillator > MA based on it's line and <= LevelDn
    * SELLs are allowed when oscillator < MA based on it's line and >= LevelUp
* **Reversal** *(starting from 2.52)*:
    * BUYs are allowed if oscillator turns UP below the LevelDn (middle bar should be below the level)
    * SELLs are allowed if oscillator turns DOWN above the LevelUp (middle bar should be above the level)


## Indicator

Indicator used to find the signal.
Can be one of the following:
* CCI
* WPR
* RSI
* Stochastic K
* Stochastic D [*(starting from v2.21)*](/docs/versions-history#20201130-221)
* Momentum [*(starting from v2.16)*](/docs/versions-history#20200819-216)


## TimeFrame

TimeFrame to calculate signal.


## Main Period

Period of oscillator (K period for Stochastic)


## Applied price

Applied price for CCI and RSI


## MA Period

MA period for **Cross MA** mode


## MA Method

MA method for **Cross MA** mode


## Stochastic Slowing period and Price

Stochastic parameters


## Level UP

Signal level for **sell** signals


## Level DN

*(-999 - calculate automatically)*

Signal level for buy signals.

Set -999 to calculate it automatically based on Level Up (for faster optimization). For Stochastic and RSI level is mirrored from 50:
* Up = 90 ---> Dn = 10
* Up = 70 ---> Dn = 30
* Up = 50 ---> Dn = 50
For WPR - from -50:
* Up = -10 ---> Dn = -90
* Up = -20 ---> Dn = -80
* Up = -50 ---> Dn = -50
For CCI - from 0:
* Up = 100 ---> Dn = -100
* Up = 150 ---> Dn = -150
* Up = 0 ---> Dn = 0


## Reverse mode

If true, buy signals replaced by sell signals and vice versa


## Use closed bars only

[*(starting from v2.35)*](/docs/versions-history#20210715-235)

Use only closed (formed) bars. If true, the signal can't change in the middle of the bar.<br/>
Default value for Oscillator filters is True


<hr>

# IdentifyTrend filter

## Enable IdentifyTrend filter

[*(starting from v2.03)*](/docs/versions-history#20200414-203)

* BUYs are allowed if IdentifyTrend is blue
* SELLs are allowed if IdentifyTrend is red
* Indicator values are taken from the previous (formed) bar of **IdentifyTrend TimeFrame**.

Set false to disable this filter.

You don’t need the IdentifyTrend indicator file for the correct work of EA. However, you can get it [here](https://drive.google.com/drive/folders/1VXsedtTLt2Tp27CQ1nfsGpdm-Z57IZ0v?usp=sharing), if you want.


## IdentifyTrend TimeFrame

TimeFrame for the IdentifyTrend filter


## IdentifyTrend Price, IdentifyTrend Period

Price and period for IdentifyTrend calculation


## IdentifyTrend Reverse mode

[*(starting from v2.14)*](/docs/versions-history#20200722-214)

Reverse all IdentifyTrend signals (Buy on Red and Sell on Blue)


## IdentifyTrend use closed bars only

[*(starting from v2.14)*](/docs/versions-history#20200722-214)

Use only closed (formed) bars. If true, the signal can’t change in the middle of the bar.<br/>
Default value for IdentifyTrend is False.


<hr>

# TDI filter

*(starting from v1.01)*


## TDI filter mode

[*(starting from v2.27)*](/docs/versions-history#20210302-227)

**TDI** filter type, can be one of the following:
* **Disabled** - TDI filter is disabled
* **Market Base Line > Signal Level**:
    * BUYs are allowed if TDI yellow line is >= **Signal level**
    * SELLs are allowed if TDI yellow line is <= **Signal level**

You don't need the TDI indicator file for the correct work of EA. However, you can get it [here](https://drive.google.com/drive/folders/1VXsedtTLt2Tp27CQ1nfsGpdm-Z57IZ0v?usp=sharing), if you want


## TDI TimeFrame

TimeFrame for the TDI filter


## Signal level

[*(starting from v2.27)*](/docs/versions-history#20210302-227)

Signal level for signal calculation


## RSI period and price, RSI smoothing period and method, Signal smoothing period and method, Volatility bands period, Standard Deviations,

[*(starting from v2.27)*](/docs/versions-history#20210302-227)

TDI indicator parameters


## TDI Reverse mode

[*(starting from v2.14)*](/docs/versions-history#20200722-214)

Reverse all TDI signals (Buy <= 50 and Sell >= 50)


## TDI use closed bars only

[*(starting from v2.14)*](/docs/versions-history#20200722-214)

Use only closed (formed) bars. If true, the signal can't change in the middle of the bar.<br/>
Default value for TDI is True.


<hr>

# MACD filter

## MACD filter Type

[*(starting from v2.16)*](/docs/versions-history#20200819-216)

Type of MACD filter:
* **Disabled**: MACD filter disabled
* **Buy on Main > 0** / **Sell on Main < 0**:
    * BUYs are allowed if MACD histogram > **Signal Level**
    * SELLs are allowed if MACD histogram < **-Signal Level**
* **Buy on 2 growing bars** / **Sell on 2 reducing bars**:
    * BUYs are allowed if MACD is growing (value on the last bar is greater than previous one)
    * SELLs are allowed if MACD is reducing (value on the last bar is less than previous one)
* **Buy on 3 growing bars** / **Sell on 3 reducing bars**:
    * BUYs are allowed if MACD is growing 3 bars in a row
    * SELLs are allowed if MACD is reducing 3 bars in a row
* **Buy on Main > Signal** / **Sell on Main < Signal**:
    * BUYs are allowed if MACD histogram > MACD Signal line
    * SELLs are allowed if MACD histogram < MACD Signal line
* **Main and Signal cross**:
    * BUYs are allowed on the bar where MACD histogram crosses MACD Signal line upwards
    * SELLs are allowed on the bar where MACD histogram crosses MACD Signal line downwards
* **Main and Signal cross >/< 0**:
    * BUYs are allowed on the bar where MACD histogram crosses MACD Signal line upwards below the **-Signal Level**
    * SELLs are allowed on the bar where MACD histogram crosses MACD Signal line downwards above the **Signal Level**
* **Buy on Signal > 0** / **Sell on Signal < 0** *(starting from 2.35)*:
    * BUYs are allowed if MACD signal line > **Signal Level**
    * SELLs are allowed if MACD signal line < **-Signal Level**
* **Buy on Main > Signal and Signal < 0 / Sell on Main < Signal and Signal > 0** *(starting from 2.35)*:
    * BUYs are allowed if MACD histogram > MACD Signal line and MACD signal line < **-Signal Level**
    * SELLs are allowed if MACD histogram < MACD Signal line and MACD signal line > **Signal Level**
* **Main cross 0** [*(starting from v2.48)*](/docs/versions-history#20220702-248):
    * BUYs are allowed on the bar where MACD histogram crosses **Signal Level** upwards
    * SELLs are allowed on the bar where MACD histogram crosses **-Signal Level** downwards
* **Signal cross 0** [*(starting from v2.48)*](/docs/versions-history#20220702-248):
    * BUYs are allowed on the bar where MACD Signal line crosses **Signal Level** upwards
    * SELLs are allowed on the bar where MACD Signal line crosses **-Signal Level** downwards


## MACD TimeFrame

TimeFrame for the MACD filter


## MACD Signal Level

[*(starting from v2.53)*](/docs/versions-history#20230412-0426-253)

Signal level for all filter types where level 0 is used.<br/>
Thus, **> 0** means **> Signal Level** and **< 0** means **< -Signal Level**


## MACD Fast period, MACD Fast method, MACD Slow period, MACD Slow method, MACD Signal period, MACD Signal method, MACD Applied price

MACD indicator parameters


## MACD Reverse mode

[*(starting from v2.14)*](/docs/versions-history#20200722-214)

Reverse all MACD signals


## MACD use closed bars only

[*(starting from v2.14)*](/docs/versions-history#20200722-214)


<hr>

# ADX filter

## Type

Type of ADX filter:
* **Disabled**: filter disabled
* **Buy on +DI <= level / Sell on -DI <= level**:
    * BUYs are allowed if +DI value <= **Signal level**
    * SELLs are allowed if -DI value <= **Signal level**
* **Buy on +DI >= level / Sell on -DI >= level** [[*(starting from v2.52)*](/docs/versions-history#20230211-0324-252)](/docs/versions-history#20230211-0324-252):
    * BUYs are allowed if +DI value >= **Signal level**
    * SELLs are allowed if -DI value >= **Signal level**
* **Buy/sell on +DI crosses -DI up/down when ADX >= level**:
    * BUYs are allowed if ADX >= **Signal level** and +DI line crosses -DI line up
    * SELLs are allowed if ADX >= **Signal level** and +DI line crosses -DI line down
* **Buy/sell when ADX >= level** [[*(starting from v2.52)*](/docs/versions-history#20230211-0324-252)](/docs/versions-history#20230211-0324-252):
    both BUYs and SELLs are allowed if ADX >= **Signal level**
    [Signals examples](https://t.me/CommunityPowerNews/5)


## TimeFrame

TimeFrame for the ADX filter


## Period Applied price *(for MT4 only)*

ADX indicator parameters


## Signal level

Signal level value


## Reverse mode

Reverse all ADX signals


## Use closed bars only

Use only closed (formed) bars. If true, the signal can't change in the middle of the bar.<br/>
Default value for ADX is True.


<hr>

# DTrend filter

[*(starting from v2.35)*](/docs/versions-history#20210715-235)

## Type

Type of DTrend filter:
* **Disabled**: filter disabled
* **Buy > level / Sell < -level**:
    * BUYs are allowed if indicator value > **Signal level**
    * SELLs are allowed if indicator value < **-Signal level**
* **Buy on rise / Sell on fall**:
    * BUYs are allowed if indicator grows
    * SELLs are allowed if indicator falls
* **Buy on bottom / Sell on top**:
    * BUYs are allowed if indicator starts to grow
    * SELLs are allowed if indicator starts to fall

## TimeFrame

TimeFrame for the DTrend filter


## MA1 period, MA2 period, D period, Scalar

DTrend indicator parameters


## Signal level

Level value for **Buy > level / Sell < -level** mode


## Reverse mode

Reverse all DTrend signals


## Use closed bars only

Use only closed (formed) bars. If true, the signal can’t change in the middle of the bar.<br/>
Default value for DTrend is False.


<hr>

# Parabolic SAR filter

[*(starting from v2.29)*](/docs/versions-history#20210403-229)

## Signal Type

Type of Parabolic filter:
* **Disabled**: filter disabled
* **Direction**:
    * BUYs are allowed if price is above the Parabolic
    * SELLs are allowed if price is below the Parabolic
* **Signal**:
    * BUYs are allowed if price crosses the Parabolic upward
    * SELLs are allowed if price crosses the Parabolic downward


## TimeFrame

TimeFrame for the Parabolic filter


## Step Maximum

Parabolic indicator parameters


## Reverse mode

Reverse all Parabolic signals


<hr>

# MA Filters

[*(starting from v2.15)*](/docs/versions-history#20200806-215)


## MA Filter Type

*(changed in v2.53)*

Type of MA filter:
* **Disabled**: MA filter disabled
* **Buy below MA / Sell above MA**:
    * BUYs are allowed if MA - Ask >= **Distance**
    * SELLs are allowed if Bid - MA >= **Distance**
* **Buy above MA / Sell below MA**:
    * BUYs are allowed if Ask - MA >= **Distance**
    * SELLs are allowed if MA - Bid >= **Distance**
* **Buy on cross DN / Sell on cross UP**:
    * BUYs are allowed if:
        * MA - Ask >= **Distance** [on current bar];
        * MA - Low < **Distance** [on previous bar].
    * SELLs are allowed if:
        * Bid - MA >= **Distance** [on current bar];
        * High - MA < **Distance** [on previous bar].
* **Buy on cross UP / Sell on cross DN**:
    * BUYs are allowed if:
        * Ask - MA >= **Distance** [on current bar];
        * High - MA < **Distance** [on previous bar].
    * SELLs are allowed if:
        * MA - Bid >= **Distance** [on current bar];
        * MA - Low < **Distance** [on previous bar].
* **Buy on rising MA / Sell on falling MA**:
    * BUYs are allowed if the MA rises with a slope >= **Angle**
    * SELLs are allowed if the MA falls with a slope >= **Angle**


## TimeFrame

TimeFrame for MA filter


## MA Period, MA Method, Applied price

Moving Average (MA) properties


## Distance / angle calculation type

**Distance / angle** calculation type:
* **In points**: fixed distance in points / fixed angle in points per bar is used ([What is a "point" in CP?](https://communitypowerea.userecho.com/en/communities/7/topics/384-what-is-a-point-in-cp-what-does-stoploss-250-points-mean))
* **Volatility * Coefficient**: distance is calculated as "current volatility * Coefficient" / angle is calculated as "current volatility * Coefficient" per bar
[Example](https://communitypowerea.userecho.com/en/communities/7/topics/325-how-to-use-bollingerbands-bb-as-an-entry-filter) - How to use BollingerBands (BB) as an entry filter


## Distance / angle value

Distance or angle value for signal calculation.

Distance can be negative (so, in **Buy below MA** mode, BUYs will be allowed if Ask above the MA, but not more than by distance points).

Angle is set in points per bar (for example, 1.5 points per bar means MA changed by 1.5 points), or as  "current volatility * Coefficient" per bar (for example, if volatility = 20 points, and **Distance / angle** value = 0.1, MA should change by 20*0.1 = 2 points per bar to generate signal).

Angle value also can be negative, so in **Buy on rising MA** mode BUY will be allowed on falling MA, but it shouldn’t fall too fast (slope still should be >= **Angle**).


## Reverse mode

[*(starting from v2.53)*](/docs/versions-history#20230412-0426-253)

Reverse all Moving Average (MA) signals


## Use closed bars only

[*(starting from v2.53)*](/docs/versions-history#20230412-0426-253)

Use only closed (formed) bars.<br/>
If true, the signal can’t change in the middle of the bar.


<hr>

# ZigZag Filter

[*(starting from v2.30)*](/docs/versions-history#20210419-230)


## ZZ filter type

Type of ZZ filter:
* **Disabled**: ZZ filter disabled
* **Extremum break**
    * BUYs are allowed on the bar breaking UP the last formed extremum of ZZ:
    IMAGE HERE
    * SELLs are allowed on the bar breaking DOWN the last formed extremum of ZZ:
    IMAGE HERE
* **Trend continue (last broken extremum direction)**
    Can be used as a filter to other signals.
    * BUYs are allowed after the last UP-break and till the next peak of ZZ is formed:
    IMAGE HERE
    * SELLs are allowed after the last DOWN-break and till the next bottom is formed:
    IMAGE HERE
* **Reversion point**
    * BUYs are allowed when the DOWN-section of ZZ is forming and the distance between the last top and the current price becomes big enough:
    IMAGE HERE
    * SELLs are allowed when the UP-section of ZZ is forming and the distance between the last bottom and the current price becomes big enough:
    IMAGE HERE
* **Counter-trend (distance from last extremum)**
    Can be used as a filter to other signals
    * BUYs are allowed when the DOWN-section of ZZ is forming and the distance between the last top and the current price is big enough:
    IMAGE HERE
    * SELLs are allowed when the UP-section of ZZ is forming and the distance between the last bottom and the current price is big enough
    IMAGE HERE


## TimeFrame

TimeFrame for ZZ filter


## Period, Min Amplitude, Min Motion

ZZ properties


## Distance type

**Distance** calculation type:
* **In points**: fixed distance in points is used ([What is a "point" in CP?](https://communitypowerea.userecho.com/en/communities/7/topics/384-what-is-a-point-in-cp-what-does-stoploss-250-points-mean))
* **Volatility * Coefficient**: distance is calculated as "current volatility * Coefficient":
    IMAGE HERE
* **Average ZZ size * coefficient**: distance is calculated as "average size of 10 last ZZ segments * Coefficient"
* **Extremum bar size * coefficient** [*(starting from v2.43)*](/docs/versions-history#20220202-243): distance is calculated as *"extremum bar size * Coefficient"*, where *extremum bar size* for UP extremums = high - min(open, close), *extremum bar size* for DN extremums = max(open, close) - low:
    IMAGE HERE


## Distance size (Points / Coefficient)

Distance size for signal calculation.

Distance can be set negative (so, in **Extremum break** mode trade will be opened **before X points** before extremum break)


## Use previous unbroken extremums

[*(starting from v2.43)*](/docs/versions-history#20220202-243)

If enabled, previous (unbroken) extremums will be used after the last extremum is broken:
IMAGE HERE


## Reverse mode

Reverse all ZZ signals


## Use closed bars only

Use only closed (formed) bars. If true, the signal can't change in the middle of the bar.


## Visualize levels, Fill rectangle, Color UP, Color DN

[*(starting from v2.43)*](/docs/versions-history#20220202-243)

ZZ signal visualization parameters.<br/>
Enable visualization to understand signals better.


<hr>

# Volatility for MA and ZZ Filters distance

[*(starting from v2.15)*](/docs/versions-history#20200806-215)


## Volatility Indicator

Indicator used for the Distance calculation for the MA and ZZ Filters.
Can be one of the following:
* ATR
* StDev
* ATR based on “Close-Open” (high and low prices not used)
* WATR

[Example of ATR/StDev using.](https://communitypowerea.userecho.com/en/communities/1/topics/509-how-to-properly-use-the-volatility-filter?redirect_to_reply=3383#comment-3383)


## TimeFrame and Period

TimeFrame and Period of volatility indicator


<hr>

# Volatility Filter

## Volatility Filter Indicator

[*(starting from v2.15)*](/docs/versions-history#20200806-215)

Indicator for the Volatility Filter:
Disabled: Volatility Filter disabled
* ATR
* StDev
* ATR based on **Close-Open** (high and low prices not used)
* WATR
* Tick volume [*(starting from v2.29)*](/docs/versions-history#20210403-229)


## Volatility Filter TimeFrame

TimeFrame for the Volatility Filter


## Indicator Period

Selected Volatility indicator period


## Min Volatility

Min volatility (in points) ([What is a "point" in CP?](https://communitypowerea.userecho.com/en/communities/7/topics/384-what-is-a-point-in-cp-what-does-stoploss-250-points-mean)) to allow new trade (both buy and sell).

Set 0 to disable minimum volatility value.


## Max Volatility

Max volatility (in points) ([What is a "point" in CP?](https://communitypowerea.userecho.com/en/communities/7/topics/384-what-is-a-point-in-cp-what-does-stoploss-250-points-mean)) to allow new trade (both buy and sell).

Set 0 to disable maximum volatility value.


## Smoothing Filter

Smoothing Volatility filter. Can be one of following:
* **Disable Smoothing Filter**: filter disabled
* **Allow trade on growth** (Volatility > MA): new trade is allowed only if the Volatility indicator is greater than MA based on it.
* **Allow trade on reduce** (Volatility < MA): new trade is allowed only if the Volatility indicator is lower than MA based on it.


## Smoothing Period

MA period for Smoothing Volatility filter


<hr>

# Fibo Filters

[*(starting from v2.17)*](/docs/versions-history#20200826-217) *(improved in v2.24 and v2.25)*


## Type

Type of Fibo filter:
* **Disabled**: Fibo filter disabled
* **On retracement**:
    * BUYs are allowed if **Trend is Bullish** and Price <= FiboLevel
    * SELLs are allowed if **Trend is Bearish** and Price >= FiboLevel
* **On retracement + opposite direction**:
    * BUYs are allowed if **Trend is Bullish** and Price <= FiboLevel or **Trend is Bearish**
    * SELLs are allowed if **Trend is Bearish** and Price >= FiboLevel or **Trend is Bullish***
* **On trend reversal**:
    * BUYs are allowed if **Trend is Bearish** and Price <= FiboLevel
    * SELLs are allowed if **Trend is Bullish** and Price >= FiboLevel

Fibo retracement is placed automatically from lowest Low to highest High based on specified **Bars number** and **TimeFrame**.

**Trend is Bullish** means highest High happened after lowest Low:
IMAGE HERE

**Trend is Bearish** means highest High happened before lowest Low:
IMAGE HERE

**FiboLevel** is set by parameter.


## Check Interval

Signal check frequency and price used:
* **Every bar of indy TF**: check signal on every bar of the FIBO TimeFrame, use Close price of the last bar;
* **Every tick**: check signal on every tick, use Bid price;
* **Every M1 bar**: check signal every M1 bar, use Close price of the last M1 bar;
* **Every M5 bar**: check signal every M5 bar, use Close price of the last M5 bar;
and so on...


## Bars for range calculation

The number of bars used to find extremums.


## Fibo level

Fibo level used for signal


## Use closed bars only

If **Use closed bars only** = true, FIBO levels recalculate every bar of selected TimeFrame. Otherwise, FIBO recalculates every tick.


<hr>

# Custom Indicators

[*(starting from v2.49)*](/docs/versions-history#20221007-249)


## Custom label

Short and understandable name of your custom indy to draw on the GUI, write to the expert logs and send via Grammy to your Telegram


## Type

Custom indicator signal type. Can be one of the following:
* **Disabled**: custom indicator signal disabled.
* **On arrow (non empty buffer)**:
    * BUYs are allowed **on every bar** with some value in the Buy-buffer
    * SELLs are allowed **on every bar** with some value in the Sell-buffer
    * **Non-empty** means any value. It can look like an arrow, like a line, like a histogram or even be invisible (calculation buffer).

* **On new arrow (non empty after empty)**:
    * BUYs are allowed **on the bar** with some value in the Buy-buffer that follows a bar with an empty value the Buy-buffer
    * SELLs are allowed **on the bar** with some value in the Sell-buffer that follows a bar with an empty value in the Sell-buffer
    * It can be an arrow, beginning of the line, first bar of histogram (after emptiness), etc..

* **In the direction of the last arrow**:
    * BUYs are allowed if the last bar with some value in the Buy-buffer was later than the last bar with some value in the Sell-buffer
    * SELLs are allowed if the last bar with some value in the Sell-buffer was later than the last bar with some value in the Buy-buffer
    * If both buffers are not empty on the same bar, both BUYs and SELLs are allowed after it.
    * For example, if the latest arrow is UP, buys are allowed, if the latest arrow is DN, sells are allowed, and if there are both arrows on the same bar, both buys and sells are   allowed after it.

* Buy above the last arrow / Sell below the last arrow: coming soon
* Buy below the line / Sell above the line: coming soon

* **On lines cross**:
    * BUYs are allowed on the bar where line from the Buy-buffer crosses above the line from the Sell-buffer
    * SELLs are allowed on the bar where line from the Buy-buffer crosses below the line from the Sell-buffer


* **On lines position**:
    * BUYs are allowed on every bar where line from the Buy-buffer is above the line from the Sell-buffer
    * SELLs are allowed on every bar where line from the Buy-buffer is below the line from the Sell-buffer


## TimeFrame

TF for the signal


## Indicator path and name

Name of the indicator you want to use.<br/>
If it is located not in the "MQL5\Indicators\" folder, the path should be specified too.

For example, if your indicator "SuperTrend.ex5" is in the "MQL5\Indicators\Market\" folder, you should set the **Indicator path and name = "Market\SuperTrend"**.


## Indicator parameters

Indicator parameters separated by commas.

Order and type of parameters must match the original order and type of indicator parameters.<br/>
String parameters must be enclosed in single quotes.

**Warning!** Indicators with "parameters groups" can't be used with parameters specified!


## Buy buffer number

**Buy-buffer** - is an indicator buffer with index Buy buffer number (numeration starts from 0)


## Sell buffer number

Sell-buffer — is an indicator buffer with index Sell buffer number (numeration starts from 0)

Set -1 to use the same buffer index as for Buy.

## Buy color buffer number, Buy color index
## Sell color buffer number, Sell color index

If both **Buy color buffer number** and **Buy color index** are set (>= 0), color filtering is applied for all values in Buy-buffer: if the value in the **Buy color buffer number** differs from **Buy color index**, value in Buy-buffer is considered as empty.

For example, if the indicator draws arrows for both buy and sell signals using buffer #0, and applies colors to these arrows using buffer #1 (first is green, means buy, second is red, means sell), you should set:
* **Signal type = On arrow / On new arrow**
* **Buy buffer number** = 0
* **Sell buffer number** = 0
* **Buy color buffer number** = 1
* **Sell color buffer number** = 1
* **Buy color index** = 0
* and **Sell color index** = 1
Thus, buy-signal will appear after the green arrow, and sell-signal — after red.


## Buy max/min level, Sell max/min level

If the value in the **Buy-buffer** is greater than **Buy max level**, it is considered as empty.
If the value in the **Buy-buffer** is less than **Buy min level**, it is considered as empty.

The same for Sell-buffer.

Levels can be used:
* for Oscillator signals:
    * Stochastic in **On new arrow (non empty after empty)** mode with **Buy max** = 20 / **Sell min** = 80 will generate signals on Main line cross levels 80 (sell) and 20 (buy)
* for Trend filter signals:
    * MACD in **On arrow (non empty buffer)** mode with **Buy min** = 0 / **Sell max** = 0 will filter all buys below 0 line and all sells above 0 level.

Set -999 to disable filtering by levels.


## Reverse mode

Reverse all CustomIndy signals


## Use closed bars only

Use only closed (formed) bars. If true, the signal can’t change in the middle of the bar.<br/>
Default value for CustomIndy is True.


## Short indicator name, Draw in subwindow

These parameters should be set for correct work of the CP GUI (show/hide indicator by clicking on signal label).<br/>
**Short indicator name** must match the indicator name as it is shown in the Data window.

**Draw in subwindow** must be set to **True** for all indicators that draw in sub-windows (oscillators, MACD, ADX, etc) and to **False** for others.


## Allow negative and zero values

Set **True** for indicators that can contain 0 or negative value by design (for example, MACD).

Set **False** for indicators that draw arrows and fill empty values with zeros (not EMPTY_VALUE constant).


<hr>

# Spread Filter

## Max current spread

[*(starting from v2.05)*](/docs/versions-history#20200421-205)

Max spread (in points) ([What is a "point" in CP?](https://communitypowerea.userecho.com/en/communities/7/topics/384-what-is-a-point-in-cp-what-does-stoploss-250-points-mean)) for positions opening.

Set 0 to disable the filter.


## Max average spread, Seconds for averaging

[*(starting from v2.05)*](/docs/versions-history#20200421-205)

Max average spread (in points) ([What is a "point" in CP?](https://communitypowerea.userecho.com/en/communities/7/topics/384-what-is-a-point-in-cp-what-does-stoploss-250-points-mean)) for positions opening and the number of seconds to calculate it.

Set 0 to disable the filter.


## Apply to first open

[*(starting from v2.49)*](/docs/versions-history#20221007-249)

Set **true** to apply the spread filter to the open of the first position in a series.


## Apply to martin

[*(starting from v2.49)*](/docs/versions-history#20221007-249)

Set **true** to apply the spread filter to the open of the martingale and anti-martingale positions.
