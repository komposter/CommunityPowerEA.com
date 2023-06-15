---
layout: page
title: Time
description: Time parameters
permalink: /docs/time
---

# Time parameters

<sup>[*(starting from v2.04)*](/docs/versions-history#20200416-204)</sup>

All settings are in GMT time corrected with selected DST mode.

Please, set correct DST mode and GMT offset while testing ([How to?](https://communitypowerea.userecho.com/en/communities/7/topics/273-how-to-set-the-correct-gmt-and-dst-for-your-broker))


<br />

### Apply schedule to

<sup>[*(starting from v2.25)*](/docs/versions-history#20210115-225)</sup>

Mode of schedule:
* **Schedule disabled**: none of the time settings work
* **Apply to the first entry only**: the schedule applies to the first deal opening only
* **Apply to all new trades**: the schedule applies to all openings (including martin and anti-martin)
* **Apply to all trade operations**: the schedule applies to all trading operations (excluding closing time)

<br />

### DST mode

DST mode of your broker:
* **Disable DST**
* **DST Europe** (last Sunday of March / last Sunday of October)
* **DST USA** (2nd Sunday of March / 1st Sunday of November)
* **DST Australia** (1st Sunday of April / 1st Sunday of October)
* **DST New Zealand** (1st Sunday of April / last Sunday of September)

<br />

### GMT offset

GMT offset for StrategyTester.<br/>
Ask your broker what GMT offset and DST mode he uses.

[How to set the correct GMT and DST for your broker?](https://communitypowerea.userecho.com/en/communities/7/topics/273-how-to-set-the-correct-gmt-and-dst-for-your-broker)

<br />

### EveryDay start hour/minute

Start time for every day.<br/>
First trade opens only within the **start time  -  end time** interval.<br/>
If disabled, work time starts at 00:00

<br />

### EveryDay session duration (mins)

<sup>[*(starting from v2.49)*](/docs/versions-history#20221007-249)</sup>

Length (in minutes) of the EA trade session.<br/>
Set 0 to use EveryDay end hour/minute parameters.

<br />

### EveryDay end hour/minute

End time for every day.<br/>
First trade opens only within the **start time  -  end time** interval.<br/>
If disabled, work time ends at 23:59

<br />

### EveryDay close hour/minute

<sup>[*(starting from v2.25)*](/docs/versions-history#20210115-225)</sup>

Close time for every day.<br/>
EA will close all open deals at this time.

<br />

### Friday stop hour/minute

End time for Friday (can differs from EveryDay end time).<br/>
EA will not open new first trades after this time on Friday.

<br />

### Friday close hour/minute

Close time for Friday.<br/>
EA will close all opened deals at this time on Friday (if trading is still enabled).

<br />

### Custom Schedule for each day

<sup>[*(starting from v2.25)*](/docs/versions-history#20210115-225)</sup>

Individual schedule for each day.<br/>
Works if **Enable Custom Schedule** = true only.<br/>
Set equal start and end hour/minute to disable the whole day.

<br />

### Last December day to trade

Last day of December when trade is allowed.

Set 0 to disable this filter.

<br />

### First January day to trade

First day of January when trade is allowed.

Set 0 to disable this filter.





