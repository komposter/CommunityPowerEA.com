---
layout: page
title: News
description: News parameters
permalink: /docs/news
---

# News parameters

[*(starting from v2.29)*](/docs/versions-history#20210403-229)

[How to set up the News filter?](https://communitypowerea.userecho.com/en/communities/7/topics/393-how-to-set-up-the-news-filter)

<hr>

## News filter mode

Can be one of the following:<br/>
* **News disabled** - news filter disabled, news don’t draw on the chart.
* **News time as a filter** - news filter active, news can be drawn on the chart. News time applied as a filter.<br/>For example, if you set Open on, EA will trade in specified time intervals around news releases and will not trade out of these intervals (example)
* **No news time as a filter** - news filter active, news can be drawn on the chart. No news time applied as a filter.<br/>For example, if you set Open on, EA will NOT trade in specified time intervals around news releases and will trade out of these intervals.


## Currencies

Currencies to filter the news. For example, “GBP,AUD,CAD”.
Set “auto” to automatically select currencies from the symbol expert is working on.


## High-impact

Use news with high impact


## Medium-impact

Use news with medium impact


## Low-impact

Use news with low impact


## Holidays

Use news with none impact (Holidays and non-economic news)


## Include key-words

Key-words separated by comma to filter the news. Case sensitive.<br/>
For example, "Nonfarm,Speech,Trade Balance".<br/>
Leave empty not to filter the news by name.


## Minutes before, Minutes after

Time interval around the news release when “news time” is active.

<hr>

# Visualization properties

## Show on chart

**true** - draw news lines on the chart by default<br/>
**false** - don’t draw


## Previous events line style, Future events line style

Lines style for past and future news


## High impact color, Medium impact color, Low impact color, No impact (holidays) color

Colors for different news impact