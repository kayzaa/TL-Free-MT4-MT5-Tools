<!-- auto-generated: remove this line after hand-editing so publish keeps your text -->
<div align="center">

# ⚡ TL GAP Matrix Pro

**28 pairs × 5 timeframes trend matrix plus GAP buyers / sellers strength on one full-chart dashboard.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL GAP Matrix Pro.ex4`](MT4/TL%20GAP%20Matrix%20Pro.ex4) |
| **MT5** | [`TL GAP Matrix Pro.ex5`](MT5/TL%20GAP%20Matrix%20Pro.ex5) |

> Compiled build only — source code is not published.

## Overview

Idea: SwingMan's "GAP without Excel" dashboard (FF thread 657370) and the GAP method (FF thread 561309).

## Install

- MT5: copy "TL GAP Matrix Pro.ex5" to MQL5\Experts
- MT4: copy "TL GAP Matrix Pro.ex4" to MQL4\Experts
- Refresh the navigator, drag the EA onto ONE chart (any symbol / timeframe), maximise the chart.
- Tick "Allow DLL imports" (only needed for the link buttons).
- The first start loads 28 pairs x 5 timeframes of history (a few seconds, progress bar).

## What You See

- Matrix: per pair spread, M15 ATR, daily open side, and for M5 M15 H1 H4 D1 three conditions MA breakout (SMA 20) / linear regression slope (20 bars) / Bollinger-Keltner squeeze (yellow ring = squeeze). All three agree = cell green or red = timeframe in trend. Then ALIGN, GAP and the SIGNAL column.
- Signal modes S23 S33 S34 S35 W45 W55 (tabs in the header).
- Filters: daily open, GAP direction (min 1.0), max spread. Confirmation: 60 seconds.
- Targets: ATR of the next higher timeframe after the smallest timeframe in trend (TP / SL multipliers).
- GAP: bid ratio, currency strength 0-9, absolute strength (GAP), momentum (30 min), buyers %, sync 0-7.
- Cards: Best setup, Pair inspector (5 charts button, one-click BUY / SELL), Buyers vs sellers, GAP matrix, Signal tracker (virtual pips, spread included), Market pulse (radar, stats, sessions).
- X folds the suite to a pill. Hover over anything for an explanation.

## Trading

- OFF by default. "Trading: enable the BUY / SELL buttons" = one-click trading (second click within 3 s confirms).
- "Trading: open a trade on every confirmed signal" = auto trading (one trade per pair, max trades, magic number, close on signal flip / end).
- Trading is risky. Test on a demo account first.

Free, no lock, no expiry.  trader.lifestyle More free tools: <https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4>

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
