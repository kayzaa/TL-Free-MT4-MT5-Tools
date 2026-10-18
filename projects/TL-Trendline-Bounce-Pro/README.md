<!-- auto-generated: remove this line after hand-editing so publish keeps your text -->
<div align="center">

# ⚡ TL Trendline Bounce Pro

**Automatic trendlines and bounce entries, built after the popular YouTube trendline strategy.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Indicator-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL%20Trendline%20Bounce%20Pro%20-%20XAUUSD%20M15.png" alt="TL Trendline Bounce Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Trendline Bounce Pro.ex4`](MT4/TL%20Trendline%20Bounce%20Pro.ex4) |
| **MT5** | [`TL Trendline Bounce Pro.ex5`](MT5/TL%20Trendline%20Bounce%20Pro.ex5) |

> Compiled build only — source code is not published.

## Overview

by Tori Trades (trend line bounce setup).

## Install

- MT5: copy MT5/Experts/TL Trendline Bounce Pro.ex5 to  <Data folder>/MQL5/Experts/
- MT4: copy MT4/Experts/TL Trendline Bounce Pro.ex4 to  <Data folder>/MQL4/Experts/ Restart or refresh the Navigator, drag it onto a chart (video: 15 min).
- Enable "Allow DLL imports" for the panel buttons (links only).

## Mode (first input)

EA mode        - trades automatically Indicator mode - lines, signals, alerts and virtual trades only. Never sends orders.

## Rules (from the video)

- Top-down: monthly -> weekly -> daily -> 4h -> 1h -> your timeframe.
- First down line from the highest point, first up line from the lowest point.
- Price may never intersect a line; capture as many touch points as possible.
- The last touch (point B) of a line is point A of the next, steeper line.
- New lines down to the 4h structure (point B = 4h swing), lower timeframes only refine.
- Entry: price comes back "at or near" the line and the candle closes on the right side. Only with the trend (BUY after a higher low, SELL after a lower high). Max. 2 entries per line (entry + the bonus re-entry of the video).
- Stop just beyond the line - the line must be violated for a loss.
- Trailing: after every new swing the stop moves - but never inside the line. Sideways phase (extra rule, can be switched off): when price moves sideways in profit and then breaks out in the trade direction, the stop jumps below the phase (SELL: above it).
- Exit: a candle closes on the other side of the line. No target (ride the trend).

All decisions on closed bars - no repaint. Strategy tester note: MT5 only provides about one year of history before the test start, so the monthly / weekly lines in the tester are shorter than on a live chart.

Trading involves high risk. Test on a demo account first.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
