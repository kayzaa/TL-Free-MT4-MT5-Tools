<!-- auto-generated: remove this line after hand-editing so publish keeps your text -->
<div align="center">

# ⚡ TL Glory SuperTrend Pro

**bush01's SuperTrend break EA — stop trails on the ATR line, optional MACD and RSI filters.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Glory_SuperTrend_Pro_panel.png" alt="TL Glory SuperTrend Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT5** | [`TL Glory SuperTrend Pro.ex5`](MT5/TL%20Glory%20SuperTrend%20Pro.ex5) |

> Compiled build only — source code is not published.

## Overview

bush01's SuperTrend (ATR line) + MACD + RSI idea from Forex Factory as ONE MT5 EA. Source: thread "I will code your EAs and Indicators for no charge", posts #81,062 and #81,074 (Feb 2026): <https://www.forexfactory.com/thread/post/15565728#post15565728> <https://www.forexfactory.com/thread/post/15567701#post15567701>

## What Was Asked

- Template: PZ_SuperTrend (ATR period 14, multiplier 3.0), MACD (12,26,9), RSI (14) with 70 / 30.
- "open trade order once the ATR is broken on either side"
- "TRAILING STOP should start following below the ATR line" (buy) / "above the ATR line" (sell)
- "an opportunity to input a target or TP"
- "Trade can also be close on opposite signal"
- "EA is not working on back testing, please fix this"

WHY EBAKEM_EA_GLORY.mq5 DID NOT TRADE
- It needed the ATR break AND a MACD divergence AND RSI below 30 (buy) / above 70 (sell) on the SAME candle. When the line breaks to the upside the RSI is almost never below 30, so there were practically no trades - live or in the tester.
- The SuperTrend was rebuilt from only 50 bars on every candle and mixed the upper and the lower band, so the line did not match the PZ_SuperTrend on the chart.
- The break was read from the unfinished candle (bar 0 at its first tick).
- PositionsTotal() counted the trades of all other EAs / symbols too.

## What This EA Does

- BUY when a candle closes above the red ATR line (the line turns blue), SELL when a candle closes below the blue ATR line (the line turns red).
- Stop loss on the ATR line at entry, then it TRAILS on the line every candle (only in the profit direction). Optional extra buffer in points.
- Take profit: none (default), points, X times the risk, or X times ATR.
- Close on the opposite signal (default on), optionally stop & reverse.
- Optional confirmations (default OFF, as requested in #81,074): MACD: above / below its signal line, above / below zero, or rising / falling RSI : above / below 50, not overbought / oversold, or SCALP mode (buy only after oversold, sell only after overbought within X bars) The filters may confirm up to X candles after the break ("confirm bars").
- Trading timeframe input (current chart by default), fixed lot or risk % (stop = ATR line).
- The template is built in: SuperTrend line (blue / red, gap at every break), MACD window, RSI window, arrows + dotted vertical lines at every signal.
- Panel: position, SuperTrend state + distance, candle timer, MACD / RSI gauges with 40-candle strips, filter status, results, chart history simulation, TRADING ON / PAUSE, CLOSE ALL, link buttons.
- Alerts: popup, sound, push, email.
- Works in the strategy tester (headless and visual).

## Installation

- Copy "TL Glory SuperTrend Pro.ex5" to  MQL5\Experts\  (File > Open Data Folder).
- Right-click "Expert Advisors" > Refresh in the Navigator.
- Drag the EA on a chart. Enable "Allow Algo Trading". Enable "Allow DLL imports" only if you want the link buttons (YouTube / RoboForex / WhatsApp / Myfxbook) to open your browser.
- One chart per pair. Use a different magic number if you run the same pair twice.

## Risk Warning

A SuperTrend break system wins big in trends and loses small, often, in ranges. Test on a demo account first. Past results do not guarantee future results. Trading involves high risk. No profit promise.

trader.lifestyle  ·  <https://www.youtube.com/@traderlifestyle>

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
