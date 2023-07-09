---
layout: page
title: Notifications
description: Notifications settings
permalink: /docs/notifications
---

# Notifications settings

[Starting from v2.26](/docs/versions-history#20210202-226), you can set any sound for any opening and closing signals, as well as send signal screenshots to the Telegram.

To connect your MetaTrader terminal to the Telegram, you need to rent and install Grammy:
 - Version for MT4 is [here](https://www.mql5.com/en/market/product/14774)
 - Version for MT5 is [here](https://www.mql5.com/en/market/product/14775)

You can look how it works in the [CommunityPowerEA Trades](https://t.me/CommunityPowerEA_Trades) channel.

Contact me to get your free demo-version of Grammy.

<br />

### Allow messages to Grammy

If **true**, EA sends additional messages and screenshots to the Telegram (Grammy should be launched on the same terminal and configured, of course).

<br />

### Enable alert on first signal

Show alert on every first signal (even if trading is disabled or **first** checkbox is unchecked)

<br />

### Enable sounds

Enable sounds

<br />

### First signal sound name

The name of the sound file that will be played when the first signal happens. Sound will be played even if trading is disabled or 'first' checkbox is unchecked.

The file must be located in terminal_directory\Sounds or its sub-directory. Only WAV files are played.

<br />

### Martin opening sound name

The name of the sound file that will be played when the martingale trade is opened

<br />

### Anti-martin opening sound name

The name of the sound file that will be played when the anti-martingale trade is opened

<br />

### Closing sound name

The name of the sound file that will be played when trade is closed

