<div align="center">

# ⚡ TL Color Flip Pro

**The GJ "Holygrail" colour-flip indicator turned into a one-file EA with an animated 3D coin dashboard.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/screenshot.png" alt="TL Color Flip Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT5** | [`TL Color Flip Pro.ex5`](MT5/TL%20Color%20Flip%20Pro.ex5) |

> Compiled build only — source code is not published.

## Overview

The GJ indicator ("MY HOLYGRAIL SYSTEM", GBPJPY M5) turned into an Expert Advisor, built exactly after the Forex Factory post by "richest" (13 May 2009): <https://www.forexfactory.com/thread/post/2731571#post2731571>

ONE FILE: "TL Color Flip Pro.ex5" - the GJ indicator window and the 3D logo are built in. You do NOT need GJ.mq4 or any other indicator.

## Install

- Copy "TL Color Flip Pro.ex5" to  MQL5\Experts\  (File -> Open Data Folder)
- Restart MT5 or right-click "Expert Advisors" in the Navigator -> Refresh
- Drag it onto a chart (original: GBPJPY M5), enable "Allow Algo Trading" and "Allow DLL imports" (only needed for the YouTube / RoboForex / WhatsApp buttons)
- A HEDGING account is required (buy and sell open at the same time).

## The Rules (as written in the post)

- **1** — The indicator has 2 colors: BLUE = long, RED = short. It repaints, so after a color change the EA waits until the candle closes. 2  On the next candle it places an order in the new color with the SAME lot size (buy, sell, buy, sell ...). 3  With 4 or more open positions, on the next color change the EA looks at the positions OPPOSITE to the new order and closes the one with the SMALLEST profit, then places the new order. 4  This repeats until the whole basket reaches +X % equity -> close all. 5  ... or until the trend ends (color change + candle close): if the basket is in profit at a color change, everything is closed (input "TREND END rule"). Interpretation note: rule 5 is ambiguous in the post. Closing ALL on every color change would make rule 3 impossible, so the default closes all only when the basket is in profit (matches the indicator's own notes: "close-all when the accumulated profit is positive"). Options: every color change / off.

## Indicator Math (1:1 from Gj.mq4)

MA = (LWMA 14 of typical price + LWMA 14 of open) / 2
- **color of bar i = BLUE if MA(i-1) >= MA(i), else RED** — (the -1 shift of the original) -> the last closed bar depends on the running candle = repaint. The EA only uses the final color at the candle close.

## Safety (not part of the original idea, can be switched off)

Emergency stop at -20 % of the cycle start balance, max lot, spread filter, optional Friday close.

## Panel

Animated 3D coin (turns blue / red on every confirmed color change), GJ color strip with the repainting bar, basket list in historical order (gold = the position that will be closed next), equity target, the 5 rules with live state. Hover over any box for an explanation. The panel always fits the chart (it splits into columns on small charts).

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
