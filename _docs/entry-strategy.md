---
layout: page
title: Entry strategy
permalink: /docs/entry-strategy
---

# Entry strategy


### **Active Period** parameter for each filter

<sup>[*(starting from v2.52)*](/docs/versions-history#20230211-0324-252)</sup>

Each signal has an **Active period** parameter. It can be **always active** or use 1 of 4 predefined periods.

Each of 4 Active periods can be set in the [Active Periods for signals and filters](docs/active-periods) section.

Active signals are shown on the EA panel as usual (gray if there is no signal, and blue/red if there is a signal), non-active signals are shown in light blue and light red if there is a signal:

![active_periods.jpg](..%2Fassets%2Fimg%2Fdocs%2Factive_periods.jpg)

<br />

### **Open on** parameter for each filter

<sup>[*(starting from v2.19)*](/docs/versions-history#20201014-219)</sup>

You can set up opening of the first deal:
* by one or more individual signals/filters,
* by several signals/filters showing the same direction,
* by several signals/filters showing the same direction or just confirming it (not showing the opposite one).

If Open on Individual signal mode is selected for any signal, a deal is opened by this signal any time it happens. So, it is an independent signal for opening.

You can set several individual signals, and deals will be opened on each signal.

In Open on Collective signal mode, all selected “Collective” signals must show the same direction to open the deal. Individual signals are ignored for this set of signals (but continue to work individually).

Open on Collective signal (neutral signals accepted) mode works like previous, but selected filters/signals should just not show the opposite direction to allow the opening.

> For example, if Stochastic Inside zone signal selected with Levels 70/30, Collective signal will allow BUY if Stochastic <= 30, but Collective neutral signal — if Stochastic < 70 (will disable BUYs if Stoch >= 70).

Starting from [v2.21](/docs/versions-history#20201130-221), if all signals are disabled (or none of **Open on** parameters are enabled), EA will trade **both ways**. So, you can open both buy and sell on the same bar and just manage them with trailing, martingale, or any other option.

<br />

### **Open martin on** parameter for each filter

<sup>[*(starting from v2.20)*](/docs/versions-history#20201103-220)</sup>

You can set up the opening of the martingale deals in the same way as the first deals opening. Signals for martingale deals can differ from signals for the first deals.

If all **Open martin on** parameters are set to **Don't use for open**, martingale deals are opened without any signal (but taking into account Step size and other martingale parameters, of course).

<br />

### **Open hedge on** parameter for each filter

<sup>[*(starting from v2.36)*](/docs/versions-history#20210804-236)</sup>

The same as **Open martin on**, but for auto-hedge deals.

<br />

### **Close on** parameter for each filter

<sup>[*(starting from v2.16)*](/docs/versions-history#20200819-216)</sup>

You can set up closing by individual signal/filter or by several filters showing the same signal. Both modes can be used with **in profit only** option.

> For example, you can set Oscillator signal, TDI and MA filters, and close deals in profit on opposite MA signal or on opposite Oscillator + TDI signal with or without profit. To do this, set **Close on = Individual signal, in profit only** for MA filter and **Close on = Collective signal** for Oscillator and TDI.

Close signal - is an opposite signal of the filter. So, buy will be closed when the filter allows sell opening.

<br />

### **Partial close on** parameter for each filter

<sup>[*(starting from v2.25)*](/docs/versions-history#20210115-225)</sup>

* **Partial close** can be activated by any **Individual** or **Collective signal**, as full close.
* **Close signal** - is an opposite signal of the filter. So, buy will be closed when the filter allows sell opening.

<br />
