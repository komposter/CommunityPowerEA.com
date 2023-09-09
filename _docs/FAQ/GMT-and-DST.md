---
layout: page
title: GMT and DST
permalink: /docs/FAQ/gmt-and-dst
---

# How to set the correct GMT and DST for your broker

1. Enable the [News filter](/docs/news), set the "Non-Farm" key-word.

2. Run the back-test for 1-1.5 years on any symbol containing "USD", timeframe M5-M15.<br />
Modelling mode doesn't matter, you can use Control points for faster test.

3. Find the news lines on the chart (or trades arrows after MT5 test), they should fit the strongest price movement of the day.

4. If they are not, correct GMT (to move all lines left or right) or DST (to move only winter or summer lines).

5. Repeat until success ;)

<br />

Here I set GMT +4 and ran the first test:

![gmt_and_dst_1.png](..%2F..%2Fassets%2Fimg%2Fdocs%2Fgmt_and_dst_1.png)

<br />

Then I changed GMT to +2:

![gmt_and_dst_2.png](..%2F..%2Fassets%2Fimg%2Fdocs%2Fgmt_and_dst_2.png)

<br />

Always check both summer and winter periods, lines should fit the movements all the year!

You can use these sets to check GMT and DST:

* [Set for MT4 (CP v2.55)](/assets/sets/CP_MT4_USD_GMTandDST_check.set)
* [Set for MT5 (CP v2.55)](/assets/sets/CP_MT5_USD_GMTandDST_check.set)

If you experience problems with GMT and DST configuration, look for help on the [community forum](https://forum.communitypowerea.com/communities/7/topics/273-how-to-set-the-correct-gmt-and-dst-for-your-broker).
