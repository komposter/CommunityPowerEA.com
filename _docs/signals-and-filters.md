---
layout: page
title: Signals and filters
description: Parameters of all Signals and filters
permalink: /docs/signals-and-filters
---

# Signals and filters

## Directional change filter

<sup>[*(starting from v2.44)*](/docs/versions-history#20220312-244)</sup>

Directional change filter allows to filter entries based on previous closed trade direction and its profit.


### Directional change filter type

**Disabled**: filter disabled

**Change dir after loss**:
*   allows BUYs after profitable BUYs / after losing SELLs
*   allows SELLs after profitable SELLs / after losing BUYs


<br />
<br />

## Big candle filter
<sup>[*(starting from v2.12)*](/docs/versions-history#20200624-212)</sup>

Big candle filter analyzes candle (current or previous, depending on **Analyze current bar** parameter) from the specified timeframe and allows entry only if candle size is in the specified range.

<br />

### Big candle filter type

* **Disabled**: filter disabled
* **Big candle in any direction**:
    * both BUYs and SELLs are allowed only if High - Low >= **Big candle min size** and High - Low <= **Big candle max size** (or max size = 0)
* **Co-directional big candle only**:
    * BUYs are allowed if High - Open >= **Big candle min size** and High - Open <= **Big candle max size** (or max size = 0)
    * SELLs are allowed if Open - Low >= **Big candle min size** and Open - Low <= **Big candle max size** (or max size = 0)
* **Opposite big candle only**:
    * BUYs are allowed if Open - Low >= **Big candle min size** and Open - Low <= **Big candle max size** (or max size = 0)
    * SELLs are allowed if High - Open >= **Big candle min size** and High - Open <= **Big candle max size** (or max size = 0)

<br />

### Big candle min size

Min candle size in points to activate signal ([what is a "point"?](/docs/FAQ/what-is-a-point)).

<br />

### Big candle max size
<sup>[*(starting from v2.44)*](/docs/versions-history#20220312-244)</sup>

Max candle size in points to activate signal ([what is a "point"?](/docs/FAQ/what-is-a-point)).

Set 0 to disable max size check.

<br />

### Big candle TimeFrame

TimeFrame to analyze candle size.

<br />

### Analyze current bar

Set **true** to analyze current bar, **false** to analyze previous (formed) bar.

<br />
<br />

# Oscillator filters #1-3

### Filter type

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
    * BUYs are allowed when oscillator crosses MA based on its line below the LevelDn
    * SELLs are allowed when oscillator crosses MA based on its line above the LevelUp

> For example:<br />![oscillator_cross_ma.png](..%2Fassets%2Fimg%2Fdocs%2Foscillator_cross_ma.png)

* **Above/below MA** [*(starting from v2.35)*](/docs/versions-history#20210715-235):
    * BUYs are allowed if oscillator > MA based on its line and <= LevelDn
    * SELLs are allowed when oscillator < MA based on its line and >= LevelUp
* **Reversal** [*(starting from v2.52)*](/docs/versions-history#20230211-0324-252):
    * BUYs are allowed if oscillator turns UP below the LevelDn (middle bar should be below the level)
    * SELLs are allowed if oscillator turns DOWN above the LevelUp (middle bar should be above the level)

<br />

### Indicator

Indicator used for oscillator signal.

Can be one of the following:
* CCI
* WPR
* RSI
* Stochastic K
* Stochastic D [*(starting from v2.21)*](/docs/versions-history#20201130-221)
* Momentum [*(starting from v2.16)*](/docs/versions-history#20200819-216)

<br />

### TimeFrame

TimeFrame to calculate signal.

<br />

### Main Period

Period of oscillator (K period for Stochastic)

<br />

### Applied price

Applied price for CCI and RSI

<br />

### MA Period

MA period for **Cross MA** mode

<br />

### MA Method

MA method for **Cross MA** mode

<br />

### Stochastic Slowing period and Price

Stochastic parameters

<br />

### Level UP

Signal level for **sell** signals

<br />

### Level DN

Signal level for **buy** signals.

Set **-999** to calculate it automatically based on Level Up (for faster optimization).

For Stochastic and RSI, level is mirrored from 50:
* Up = 90 ---> Dn = 10
* Up = 70 ---> Dn = 30
* Up = 50 ---> Dn = 50

For WPR -- from **-50**:
* Up = -10 ---> Dn = -90
* Up = -20 ---> Dn = -80
* Up = -50 ---> Dn = -50

For CCI -- from **0**:
* Up = 100 ---> Dn = -100
* Up = 150 ---> Dn = -150
* Up = 0 ---> Dn = 0

<br />

### Reverse mode

Reverse all Oscillator signals.

<br />

### Use closed bars only

<sup>[*(starting from v2.35)*](/docs/versions-history#20210715-235)</sup>

Use only closed (formed) bars. If **true**, the signal can't change in the middle of the bar.

Default value for Oscillator filters is **true**

<br />
<br />

# IdentifyTrend filter

### Enable IdentifyTrend filter

<sup>[*(starting from v2.03)*](/docs/versions-history#20200414-203)</sup>

If true:
* BUYs are allowed if IdentifyTrend is blue
* SELLs are allowed if IdentifyTrend is red

Set **false** to disable this filter.

You don't need the IdentifyTrend indicator file for the correct work of EA. However, you can get it [here](https://drive.google.com/drive/folders/1VXsedtTLt2Tp27CQ1nfsGpdm-Z57IZ0v?usp=sharing), if you want.

<br />

### IdentifyTrend TimeFrame

TimeFrame for the IdentifyTrend filter

<br />

### IdentifyTrend Price, IdentifyTrend Period

Price and period for IdentifyTrend calculation

<br />

### IdentifyTrend Reverse mode

<sup>[*(starting from v2.14)*](/docs/versions-history#20200722-214)</sup>

Reverse all IdentifyTrend signals (Buy on Red and Sell on Blue)

<br />

### IdentifyTrend use closed bars only

<sup>[*(starting from v2.14)*](/docs/versions-history#20200722-214)</sup>

Use only closed (formed) bars. If **true**, the signal can't change in the middle of the bar.

Default value for IdentifyTrend is **false**.


<br />
<br />

# TDI filter

<sup>[*(starting from v1.01)*](/docs/versions-history#20200404-101)</sup>

TDI -- is a well-known oscillator based on RSI:

![]({{site.baseurl}}/assets/img/docs/iTDI.png)

You don't need the TDI indicator file for the correct work of EA. However, you can get it [here](https://drive.google.com/drive/folders/1VXsedtTLt2Tp27CQ1nfsGpdm-Z57IZ0v?usp=sharing), if you want

<br />

### TDI filter mode

<sup>[*(starting from v2.27)*](/docs/versions-history#20210302-227)</sup>

**TDI** filter type, can be one of the following:
* **Disabled** - TDI filter is disabled
* **Market Base Line > Signal Level**:
    * BUYs are allowed if TDI yellow line is >= **Signal level**
    * SELLs are allowed if TDI yellow line is <= **Signal level**

<br />

### TDI TimeFrame

TimeFrame for the TDI filter

<br />

### Signal level

<sup>[*(starting from v2.27)*](/docs/versions-history#20210302-227)</sup>

Signal level for signal calculation

<br />

### TDI indicator parameters

<sup>[*(starting from v2.27)*](/docs/versions-history#20210302-227)</sup>

 * RSI period and price
 * RSI smoothing period and method
 * Signal smoothing period and method
 * Volatility bands period
 * Standard Deviations


<br />

### TDI Reverse mode

<sup>[*(starting from v2.14)*](/docs/versions-history#20200722-214)</sup>

Reverse all TDI signals

<br />

### TDI use closed bars only

<sup>[*(starting from v2.14)*](/docs/versions-history#20200722-214)</sup>

Use only closed (formed) bars. If **true**, the signal can't change in the middle of the bar.

Default value for TDI is **true**.


<br />
<br />

# MACD filter

### MACD filter Type

<sup>[*(starting from v2.16)*](/docs/versions-history#20200819-216)</sup>

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

<br />

### MACD TimeFrame

TimeFrame for the MACD filter

<br />

### MACD Signal Level

<sup>[*(starting from v2.53)*](/docs/versions-history#20230412-0426-253)</sup>

Signal level for all filter types where it is used

<br />

### MACD indicator parameters

 * MACD Fast period
 * MACD Fast method
 * MACD Slow period
 * MACD Slow method
 * MACD Signal period
 * MACD Signal method
 * MACD Applied price


<br />

### MACD Reverse mode

<sup>[*(starting from v2.14)*](/docs/versions-history#20200722-214)</sup>

Reverse all MACD signals

<br />

### MACD use closed bars only

<sup>[*(starting from v2.14)*](/docs/versions-history#20200722-214)</sup>

Use only closed (formed) bars. If **true**, the signal can't change in the middle of the bar.

<br />
<br />

# ADX filter

### Type

Type of ADX filter:
* **Disabled**: filter disabled
* **Buy on +DI <= level / Sell on -DI <= level**:
    * BUYs are allowed if +DI value <= **Signal level**
    * SELLs are allowed if -DI value <= **Signal level**

  ![]({{site.baseurl}}/assets/img/docs/ADX-signal-1.jpg)

* **Buy on +DI >= level / Sell on -DI >= level** [*(starting from v2.52)*](/docs/versions-history#20230211-0324-252):
    * BUYs are allowed if +DI value >= **Signal level**
    * SELLs are allowed if -DI value >= **Signal level**
* **Buy/sell on +DI crosses -DI up/down when ADX >= level**:
    * BUYs are allowed if ADX >= **Signal level** and +DI line crosses -DI line up
    * SELLs are allowed if ADX >= **Signal level** and +DI line crosses -DI line down

  ![]({{site.baseurl}}/assets/img/docs/ADX-signal-2.jpg)

* **Buy/sell when ADX >= level** [*(starting from v2.52)*](/docs/versions-history#20230211-0324-252):
    * Both BUYs and SELLs are allowed if ADX >= **Signal level**

<br />

### TimeFrame

TimeFrame for the ADX filter

<br />

### Period Applied price

ADX indicator parameters (for MT4 only)

<br />

### Signal level

Signal level value

<br />

### Reverse mode

If **true**, buy signals replaced by sell signals and vice versa.

<br />

### Use closed bars only

Use only closed (formed) bars. If **true**, the signal can't change in the middle of the bar.

Default value for ADX is **true**.


<br />
<br />

# DTrend filter

<sup>[*(starting from v2.35)*](/docs/versions-history#20210715-235)</sup>

### Type

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

<br />

### TimeFrame

TimeFrame for the DTrend filter

<br />

### DTrend indicator parameters

 * MA1 period
 * MA2 period
 * D period
 * Scalar

<br />

### Signal level

Level value for **Buy > level / Sell < -level** mode

<br />

### Reverse mode

Reverse all DTrend signals

<br />

### Use closed bars only

Use only closed (formed) bars. If **true**, the signal can't change in the middle of the bar.

Default value for DTrend is **false**.


<br />
<br />

# Parabolic SAR filter

<sup>[*(starting from v2.29)*](/docs/versions-history#20210403-229)</sup>

### Signal Type

Type of Parabolic filter:
* **Disabled**: filter disabled
* **Direction**:
    * BUYs are allowed if price is above the Parabolic
    * SELLs are allowed if price is below the Parabolic
* **Signal**:
    * BUYs are allowed if price crosses the Parabolic upward
    * SELLs are allowed if price crosses the Parabolic downward

<br />

### TimeFrame

TimeFrame for the Parabolic filter

<br />

### Step Maximum

Parabolic indicator parameters

<br />

### Reverse mode

Reverse all Parabolic signals


<br />
<br />

# MA Filters

<sup>*([starting from v2.15](/docs/versions-history#20200806-215), [refactored in 2.53](/docs/versions-history#20230412-0426-253))*</sup>

### MA Filter Type

Type of MA filter:
* **Disabled**: MA filter disabled
* **Buy below MA / Sell above MA**:
    * BUYs are allowed if MA - Ask >= **Distance**
    * SELLs are allowed if Bid - MA >= **Distance**
* **Buy on cross DN / Sell on cross UP**:
    * BUYs are allowed if:
        * MA - Ask >= **Distance** [on current bar];
        * MA - Low < **Distance** [on previous bar].
    * SELLs are allowed if:
        * Bid - MA >= **Distance** [on current bar];
        * High - MA < **Distance** [on previous bar].
* **Buy on rising MA / Sell on falling MA**:
    * BUYs are allowed if the MA rises with a slope >= **Angle**
    * SELLs are allowed if the MA falls with a slope >= **Angle**

<br />

### TimeFrame

TimeFrame for MA filter

<br />

### Moving Average properties

 * MA Period
 * MA Method
 * Applied price

<br />

### Distance / angle calculation type

**Distance / angle** calculation type:
* **In points**: fixed distance in points / fixed angle in points per bar is used ([what is a "point"?](/docs/FAQ/what-is-a-point))
* **Volatility * Coefficient**: distance is calculated as "current volatility * Coefficient" / angle is calculated as "current volatility * Coefficient" per bar



<br />

### Distance / angle value

Distance or angle value for signal calculation.

Distance can be negative (so, in **Buy below MA** mode, BUYs will be allowed if Ask above the MA, but not more than by distance points).

Angle is set in points per bar (for example, 1.5 points per bar means MA changed by 1.5 points), or as  "current volatility * Coefficient" per bar (for example, if volatility = 20 points, and **Distance / angle** value = 0.1, MA should change by 20*0.1 = 2 points per bar to generate signal).

Angle value also can be negative, so in **Buy on rising MA** mode BUY will be allowed on falling MA, but it shouldn't fall too fast (slope still should be >= **Angle**).

<br />

### Reverse mode

<sup>[*(starting from v2.53)*](/docs/versions-history#20230412-0426-253)</sup>

Reverse all Moving Average (MA) signals

<br />

### Use closed bars only

<sup>[*(starting from v2.53)*](/docs/versions-history#20230412-0426-253)</sup>

Use only closed (formed) bars.

If true, the signal can't change in the middle of the bar.


<br />
<br />

# ZigZag Filter

<sup>[*(starting from v2.30)*](/docs/versions-history#20210419-230)</sup>

### ZZ filter type

Type of ZZ filter:
* **Disabled**: ZZ filter disabled
* **Extremum break**
    * BUYs are allowed on the bar breaking UP the last formed extremum of ZZ:
    ![]({{site.baseurl}}/assets/img/docs/zz1.png)

    * SELLs are allowed on the bar breaking DOWN the last formed extremum of ZZ:
    ![]({{site.baseurl}}/assets/img/docs/zz2.png)

* **Trend continue (last broken extremum direction)**
    Can be used as a filter to other signals.
    * BUYs are allowed after the last UP-break and till the next peak of ZZ is formed:
    ![]({{site.baseurl}}/assets/img/docs/zz3.png)

    * SELLs are allowed after the last DOWN-break and till the next bottom is formed:
    ![]({{site.baseurl}}/assets/img/docs/zz4.png)

* **Reversion point**
    * BUYs are allowed when the DOWN-section of ZZ is forming and the distance between the last top and the current price becomes big enough:
    ![]({{site.baseurl}}/assets/img/docs/zz5.png)

    * SELLs are allowed when the UP-section of ZZ is forming and the distance between the last bottom and the current price becomes big enough:
    ![]({{site.baseurl}}/assets/img/docs/zz6.png)

* **Counter-trend (distance from last extremum)**
    Can be used as a filter to other signals
    * BUYs are allowed when the DOWN-section of ZZ is forming and the distance between the last top and the current price is big enough:
    ![]({{site.baseurl}}/assets/img/docs/zz7.png)

    * SELLs are allowed when the UP-section of ZZ is forming and the distance between the last bottom and the current price is big enough
    ![]({{site.baseurl}}/assets/img/docs/zz8.png)

<br />

### TimeFrame

TimeFrame for ZZ filter

<br />

### ZZ indicator properties

 * Period
 * Min Amplitude
 * Min Motion

<br />

### Distance type

**Distance** calculation type:
* **In points**: fixed distance in points is used ([what is a "point"?](/docs/FAQ/what-is-a-point))
* **Volatility * Coefficient**: distance is calculated as "current volatility * Coefficient":
    ![]({{site.baseurl}}/assets/img/docs/zz9.png)

* **Average ZZ size * coefficient**: distance is calculated as "average size of 10 last ZZ segments * Coefficient"
* **Extremum bar size * coefficient** [*(starting from v2.43)*](/docs/versions-history#20220202-243): distance is calculated as *"extremum bar size * Coefficient"*, where *extremum bar size* for UP extremums = high - min(open, close), *extremum bar size* for DN extremums = max(open, close) - low:
    ![]({{site.baseurl}}/assets/img/docs/zz10.png)

<br />

### Distance size (Points / Coefficient)

Distance size for signal calculation.

Distance can be set negative (so, in **Extremum break** mode trade will be opened **before X points** before extremum break)

<br />

### Use previous unbroken extremums

<sup>[*(starting from v2.43)*](/docs/versions-history#20220202-243)</sup>

If enabled, previous (unbroken) extremums will be used after the last extremum is broken:
![]({{site.baseurl}}/assets/img/docs/zz11.png)

<br />

### Reverse mode

Reverse all ZZ signals

<br />

### Use closed bars only

Use only closed (formed) bars. If **true**, the signal can't change in the middle of the bar.

<br />

### Visualization parameters

<sup>[*(starting from v2.43)*](/docs/versions-history#20220202-243)</sup>

 * Visualize levels (true/false)
 * Fill rectangle (true/false)
 * Color UP
 * Color DN

Enable visualization to understand signals better.


<br />
<br />

# Volatility for MA and ZZ Filters

<sup>[*(starting from v2.15)*](/docs/versions-history#20200806-215)</sup>

### Volatility Indicator

Indicator used for the Distance calculation for the MA and ZZ Filters.

Can be one of the following:
* ATR
* StDev
* ATR based on **Close-Open** (high and low prices not used)
* WATR
* Volume (don't use for this block!)

<br />

### TimeFrame and Period

TimeFrame and Period of volatility indicator


<br />
<br />

# Volatility Filter

### Volatility Filter Indicator

<sup>[*(starting from v2.15)*](/docs/versions-history#20200806-215)</sup>

Indicator for the Volatility Filter:
* Disabled: Volatility Filter disabled
* ATR
* StDev
* ATR based on **Close-Open** (high and low prices not used)
* WATR
* Volume [*(starting from v2.29)*](/docs/versions-history#20210403-229)

<br />

### Volatility Filter TimeFrame

TimeFrame for the Volatility Filter

<br />

### Indicator Period

Selected Volatility indicator period

<br />

### Min Volatility

Min volatility (in points) ([what is a "point"?](/docs/FAQ/what-is-a-point)) to allow new trade (both buy and sell).

Set 0 to disable minimum volatility value.

<br />

### Max Volatility

Max volatility (in points) ([what is a "point"?](/docs/FAQ/what-is-a-point)) to allow new trade (both buy and sell).

Set 0 to disable maximum volatility value.

> For example, if you set **Volatility Indicator** = ATR, and **Volatility Period** = 20, and **Min Volatility (in points)** = 10, you'll have trades in the green zones only:
![]({{site.baseurl}}/assets/img/docs/volatility3.png)

<br />

### Smoothing Filter

Smoothing Volatility filter. Can be one of following:
* **Disable Smoothing Filter**: filter disabled
* **Allow trade on growth** (Volatility > MA): new trade is allowed only if the Volatility indicator is greater than MA based on it.
* **Allow trade on reduce** (Volatility < MA): new trade is allowed only if the Volatility indicator is lower than MA based on it.

<br />

### Smoothing Period

MA period for Smoothing Volatility filter


<br />
<br />

# Fibo Filters

<sup>*([starting from v2.17](/docs/versions-history#20200826-217), [improved in v2.24](/docs/versions-history#20201231-224), [improved in v2.25](/docs/versions-history#20210115-225))*</sup>

### Type

Type of Fibo filter:
* **Disabled**: Fibo filter disabled
* **On retracement**:
    * BUYs are allowed if **Trend is Bullish** and Price <= FiboLevel
    * SELLs are allowed if **Trend is Bearish** and Price >= FiboLevel
* **On retracement + opposite direction**:
    * BUYs are allowed if **Trend is Bullish** and Price <= FiboLevel or **Trend is Bearish**
    * SELLs are allowed if **Trend is Bearish** and Price >= FiboLevel or **Trend is Bullish**
* **On trend reversal**:
    * BUYs are allowed if **Trend is Bearish** and Price <= FiboLevel
    * SELLs are allowed if **Trend is Bullish** and Price >= FiboLevel

Fibo retracement is placed automatically from the lowest Low to the highest High based on specified **Bars number** and **TimeFrame**.

**Trend is Bullish** means the highest High happened after the lowest Low:
![]({{site.baseurl}}/assets/img/docs/fibo1.png)

**Trend is Bearish** means the highest High happened before the lowest Low:
![]({{site.baseurl}}/assets/img/docs/fibo2.png)

**FiboLevel** is set by parameter.

<br />

### Check Interval

Signal check frequency and price used:
* **Every bar of indy TF**: check signal on every bar of the FIBO TimeFrame, use Close price of the last bar
* **Every tick**: check signal on every tick, use Bid price
* **Every M1 bar**: check signal every M1 bar, use Close price of the last M1 bar
* **Every M5 bar**: check signal every M5 bar, use Close price of the last M5 bar
* and so on...

<br />

### Bars for range calculation

The number of bars used to find extremums.

<br />


### MACD bars for extremums detection

<sup>[*(starting from v2.54)*](/docs/versions-history#20230427-0706-254)</sup>

You can use MACD for price extremums detection:
 - High extremum will be located on positive MACD waves,
 - Low extremums will be located on negative MACD waves.

Minimum wave width is defined by this parameter.

Set 0 to disable MACD extremums detection.

<br />

### Fibo level

Fibo level used for signal

<br />

### Use closed bars only

If **Use closed bars only** = true, FIBO levels recalculate every bar of selected TimeFrame. Otherwise, FIBO recalculates every tick.

<br />
<br />

# Custom Indicators

<sup>[*(starting from v2.49)*](/docs/versions-history#20221007-249)</sup>

### Custom label

Short and understandable name of your custom indy to draw on the GUI, write to the expert logs and send via Grammy to your Telegram

<br />

### Type

Custom indicator signal type. Can be one of the following:
* **Disabled**: custom indicator signal disabled.
* **On arrow (non empty buffer)**:
    * BUYs are allowed **on every bar** with some value in the Buy-buffer
    * SELLs are allowed **on every bar** with some value in the Sell-buffer

  **Non-empty** means any value. It can look like an arrow, like a line, like a histogram or even be invisible (calculation buffer).


* **On new arrow (non-empty after empty)**:
    * BUYs are allowed **on the bar** with some value in the Buy-buffer that follows a bar with an empty value the Buy-buffer
    * SELLs are allowed **on the bar** with some value in the Sell-buffer that follows a bar with an empty value in the Sell-buffer
  
  It can be an arrow, beginning of the line, first bar of histogram (after emptiness), etc..


* **In the direction of the last arrow**:
    * BUYs are allowed if the last bar with some value in the Buy-buffer was later than the last bar with some value in the Sell-buffer
    * SELLs are allowed if the last bar with some value in the Sell-buffer was later than the last bar with some value in the Buy-buffer
  
  If both buffers are not empty on the same bar, both BUYs and SELLs are allowed after it.
  
> For example, if the latest arrow is UP, buys are allowed, if the latest arrow is DN, sells are allowed, and if there are both arrows on the same bar, both buys and sells are   allowed after it.

* **On lines cross**:
    * BUYs are allowed on the bar where line from the Buy-buffer crosses above the line from the Sell-buffer
    * SELLs are allowed on the bar where line from the Buy-buffer crosses below the line from the Sell-buffer


* **On lines position**:
    * BUYs are allowed on every bar where line from the Buy-buffer is above the line from the Sell-buffer
    * SELLs are allowed on every bar where line from the Buy-buffer is below the line from the Sell-buffer

<br />

### TimeFrame

TF for the signal

<br />

### Indicator path and name

Name of the indicator you want to use.

If it is located not in the "MQL5\Indicators\" folder, the path should be specified too.

> For example, if your indicator "SuperTrend.ex5" is in the "MQL5\Indicators\Market\" folder, you should set the **Indicator path and name = "Market\SuperTrend"**.

<br />

### Indicator parameters

Indicator parameters separated by commas.

Order and type of parameters must match the original order and type of indicator parameters.

String parameters must be enclosed in single quotes.

{% include alert.html type="warning" title="Warning" content="Indicators with **parameters groups** can't be used with parameters specified!" %}

<br />

### Buy buffer number

**Buy-buffer** - is an indicator buffer with index Buy buffer number (numeration starts from 0)

<br />

### Sell buffer number

Sell-buffer — is an indicator buffer with index Sell buffer number (numeration starts from 0)

Set -1 to use the same buffer index as for Buy.

<br />

### Buy color buffer number, Buy color index<br />

### Sell color buffer number, Sell color index

If both **Buy color buffer number** and **Buy color index** are set (>= 0), color filtering is applied for all values in Buy-buffer: if the value in the **Buy color buffer number** differs from **Buy color index**, value in Buy-buffer is considered as empty.

> For example, if the indicator draws arrows for both buy and sell signals using buffer #0, and applies colors to these arrows using buffer #1 (first is green, means buy, second is red, means sell), you should set:
* **Signal type = On arrow / On new arrow**
* **Buy buffer number** = 0
* **Sell buffer number** = 0
* **Buy color buffer number** = 1
* **Sell color buffer number** = 1
* **Buy color index** = 0
* and **Sell color index** = 1
Thus, buy-signal will appear after the green arrow, and sell-signal — after red.

<br />

### Buy max/min level, Sell max/min level

If the value in the **Buy-buffer** is greater than **Buy max level**, it is considered as empty.
If the value in the **Buy-buffer** is less than **Buy min level**, it is considered as empty.

The same for Sell-buffer.

Levels can be used:
* for Oscillator signals:
    * Stochastic in **On new arrow (non empty after empty)** mode with **Buy max** = 20 / **Sell min** = 80 will generate signals on Main line cross levels 80 (sell) and 20 (buy)
* for Trend filter signals:
    * MACD in **On arrow (non empty buffer)** mode with **Buy min** = 0 / **Sell max** = 0 will filter all buys below 0 line and all sells above 0 level.

Set -999 to disable filtering by levels.

<br />

### Reverse mode

Reverse all CustomIndy signals

<br />

### Use closed bars only

Use only closed (formed) bars. If **true**, the signal can't change in the middle of the bar.

Default value for CustomIndy is **true**.

<br />

### Short indicator name, Draw in subwindow

These parameters should be set for correct work of the CP GUI (show/hide indicator by clicking on signal label).

**Short indicator name** must match the indicator name as it is shown in the Data window.

**Draw in subwindow** must be set to **True** for all indicators that draw in sub-windows (oscillators, MACD, ADX, etc) and to **False** for others.

<br />

### Allow negative and zero values

Set **True** for indicators that can contain 0 or negative value by design (for example, MACD).

Set **False** for indicators that draw arrows and fill empty values with zeros (not EMPTY_VALUE constant).


<br />
<br />

# Spread Filter
<br />

### Max current spread

<sup>[*(starting from v2.05)*](/docs/versions-history#20200421-205)</sup>

Max spread (in points) ([what is a "point"?](/docs/FAQ/what-is-a-point)) for positions opening.

Set 0 to disable the filter.

<br />

### Max average spread, Seconds for averaging

<sup>[*(starting from v2.05)*](/docs/versions-history#20200421-205)</sup>

Max average spread (in points) ([what is a "point"?](/docs/FAQ/what-is-a-point)) for positions opening and the number of seconds to calculate it.

Set 0 to disable the filter.

<br />

### Apply to first open

<sup>[*(starting from v2.49)*](/docs/versions-history#20221007-249)</sup>

Set **true** to apply the spread filter to the open of the first position in a series.

<br />

### Apply to martin

<sup>[*(starting from v2.49)*](/docs/versions-history#20221007-249)</sup>

Set **true** to apply the spread filter to the open of the martingale and anti-martingale positions.
