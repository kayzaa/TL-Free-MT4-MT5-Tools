<div align="center">

# ⚡ TL SuperSlope Confluence Pro

**Improved Baluda SuperSlope v2.2 — currency slope confluence across pairs and timeframes.**

![version](https://img.shields.io/badge/version-v3.0-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Indicator-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL%20SuperSlope%20Confluence%20Pro.png" alt="TL SuperSlope Confluence Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL SuperSlope Confluence Pro.ex4`](MT4/TL%20SuperSlope%20Confluence%20Pro.ex4) |

> Compiled build only — source code is not published.

## Overview

arrows/MTF table by gprince66, all-pairs fix by VirtualFM).

## Install

- MT4: File -> Open Data Folder -> MQL4 -> Indicators -> copy the .ex4 there.
- Restart MT4 or right-click "Indicators" in the Navigator -> Refresh.
- Drag it onto the chart. Tick "Allow DLL imports" (only needed for the panel link buttons).

## Why The Old Version Repainted

With timeFrame = D1 on an intraday chart, v2.2 used the FINAL D1 close for every intraday bar of that day. History therefore showed slope values and arrows that were never on the chart live - especially on the first bars of a new day.

## What Is New

- No repaint: every bar uses the price that was known when that bar closed ("point in time"). The live value is identical to v2.2. Mode "last CLOSED higher-TF bar" = 100% stable but one D1 bar slower. Mode "Original" = old behaviour, for comparison.
- Arrows only on CLOSED bars - an arrow never disappears or moves.
- Confluence score (each filter on/off in the inputs): F1 extra TF 1 (W1) slope agrees      F5 close above/below EMA 50 F2 extra TF 2 (MN) slope agrees      F6 ADX >= 20 and +DI/-DI agree F3 chart-TF slope agrees (timing)    F7 RSI above/below 50 F4 base slope gaining strength       F8 not overextended (inside +-level) The base D1 slope direction is always required. Arrow only when the score reaches MinConfluence (default 5 of 7 active filters).
- Grey dot = slope flipped but confluence too low (filtered signal).
- Live checklist panel (click the header to collapse).
- Alerts (popup / push / e-mail) only on closed bars.
- iCustom buffers for EAs: 0 slope, 1 mirror, 2 buy score, 3 sell score, 4 signal (+1 buy / -1 sell on the signal bar).

Indicators help with timing; they do not guarantee profits. Test on demo first.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
