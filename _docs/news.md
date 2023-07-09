---
layout: page
title: News
description: News parameters
permalink: /docs/news
---

# News parameters

<sup>[*(starting from v2.29)*](/docs/versions-history#20210403-229)</sup>

News filter allows you to avoid trading during news releases, or the opposite, to trade only during news releases.

You can specify the currencies and the impact of news to be used in trading and the time interval around news releases.

News calendar is downloaded from [Forex factory](https://www.forexfactory.com/calendar.php).
 
[How to set up the News filter?](https://communitypowerea.userecho.com/en/communities/7/topics/393-how-to-set-up-the-news-filter)


<br />

### News filter mode

Can be one of the following:
* **News disabled** - news filter disabled, news don't draw on the chart.


* **News time as a filter** - news filter active, news can be drawn on the chart. Time interval around the news release applied as a filter.

> For example, if you set _Open on_ in this mode, EA will **only** trade in specified time intervals around news releases and **will not** trade out of these intervals.

* **No news time as a filter** - news filter active, news can be drawn on the chart. Time interval free of news releases applied as a filter.

> For example, if you set _Open on_ in this mode, EA will **not** trade in specified time intervals around news releases and **will** trade out of these intervals.

<br />

### Currencies

Currencies to filter the news. For example, “**GBP,AUD,CAD**”.

Set “**auto**” to automatically select currencies from the symbol expert is working on.

<br />

### High-impact

Use news with high impact

<br />

### Medium-impact

Use news with medium impact

<br />

### Low-impact

Use news with low impact

<br />

### Holidays

Use news with **none** impact (Holidays and non-economic news)

<br />

### Include key-words

Key-words separated by comma to filter the news. Case-sensitive.

> For example, "**Nonfarm,Speech,Trade Balance**".

Leave empty not to filter the news by name.

<br />

### Minutes before, Minutes after

Time interval around the news release when “news time” is active.


<br />

# Visualization properties

### Show on chart

**true** - draw news lines on the chart by default, **false** - don't draw

[Starting from v2.29](/docs/versions-history#20210403-229), you can toggle news lines visibility on the chart using the button on the panel:

![show_orders.gif](..%2Fassets%2Fimg%2Fdocs%2Fshow_orders.gif)

<br />

### Previous events line style, Future events line style

Lines style for past and future news

<br />

### Lines color

Lines color for different news impact
