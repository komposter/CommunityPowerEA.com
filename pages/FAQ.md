---
layout: page
title: FAQ
permalink: /docs/FAQ/
---

# Frequently Asked Questions

### [What is a "point" in CommunityPower EA?](/docs/FAQ/what-is-a-point)

<br />

### [How to set the correct GMT and DST for your broker?](/docs/FAQ/gmt-and-dst)

<br />

#### I’ve installed and launched the EA as described above. Is it working?

Yes, it is. Just check the smile in the right upper corner of the chart:

![]({{site.baseurl}}/assets/img/faq/faq1.png)
![]({{site.baseurl}}/assets/img/faq/faq2.png)

<br />

#### So when I launch the EA it automatically already has the indicators built in, right?

Yes, all indicators are built into EA. You don’t need to install anything else.

<br />

#### Stochastic/RSI levels after the test differ from Signal levels in the EA settings. What’s wrong?

These are just indicator draw settings, EA can’t change them. But EA works correctly (with signal levels you’ve set), just check signals.

<br />

#### Should I drag all indicators to the chart while EA is working?

No, you shouldn’t.

<br />

#### EA doesn’t open any trades! I see only “Trade by experts is disabled!” and “ERROR #133 (trade is disabled)” messages in the expert log.

This is a restriction from your broker. Ask your broker to allow trading by EAs or [change your broker](/brokers/).

<br />

#### Can’t load EA (Error #4200)

![]({{site.baseurl}}/assets/img/faq/faq3.png)

To use templates with EA attached:
 * Launch and configure the ea
 * delete all objects from chart (including hidden objects)
 * save the template
 * Then you can load this template to any chart

<br />

#### Alert: GVManager: WARNING! Too long GV name ("20674884 CommunityPower MT5 3041  BE_Alerted_S")

Rename EA with a shorter name (for example, "CP MT5" instead of "CommunityPower MT5 3041"). 

To find the EA file, use the File -> Open Data Folder menu, then go to **MQL5\Experts\** folder.

<br />
