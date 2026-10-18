<!-- auto-generated: remove this line after hand-editing so publish keeps your text -->
<div align="center">

# ⚡ TL HTF Candle Trader Pro

**Trades the lower timeframe inside the structure of the higher-timeframe candle.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_HTFCandleTraderPro_screenshot.png" alt="TL HTF Candle Trader Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT5** | [`TL HTF Candle Trader Pro.ex5`](MT5/TL%20HTF%20Candle%20Trader%20Pro.ex5) |

> Compiled build only — source code is not published.

## Overview

What it does One EA that trades the LOWER timeframe candle (default M2) in the direction of the running BIGGER timeframe candle (default M10) - with the bigger / lower candles drawn on the chart (TL Bigger TF Candles Pro built in), a tiny CLOSE ALL button and a tiny candle countdown.

The rules (BUY - SELL is the exact mirror)
- Direction   price is ABOVE the open of the running bigger candle -> only BUY trades (below the open -> only SELL trades). Never against the bigger candle.
- First part  optional: wait X minutes after the bigger candle opened ("First part", 0 = off)
- Big move    optional: the bigger candle must already be X points above its open (0 = any)
- Lower wait  optional: wait X seconds after the lower candle opened (0 = off)
- Trigger     the lower candle must move PAST ITS OWN OPEN in the same direction by at least "min. move" points (default 20 points = 2 pips on a 5-digit pair, 0.20 on gold)
- Entry       Market            : buy at market as soon as 1-5 are true Stop current high : buy stop at the HIGH of the current lower candle + extra distance Stop previous high: buy stop at the HIGH of the previous lower candle + extra distance (price already above it -> skip, or market order - input) Unfilled stop orders are deleted at the end of the lower candle (or the bigger candle - input) and when the bigger candle flips to the other side of its open.
- Limits      one trade per lower candle, max. trades per bigger candle (default 1), max. open trades, no new trades in the last X minutes of the bigger candle, trading hours, max. spread. The EA respects the broker trading sessions.

Exits
- **Stop loss** — beyond the bigger candle open / lower candle open / lower candle low (+ buffer), a fixed distance or none Take profit  R multiple of the stop (default 1.5R), fixed points or none Candle end   close the trade when the bigger candle ends (default on) Flip         optional: close when the bigger candle flips against the trade Break even   optional: stop to entry + X points after +Y points profit

Tiny buttons (top right, drag them anywhere by the grip - the position is saved per chart)
- **CLOSE ALL** — closes ALL trades of the chart symbol (like TL Close All Pro): magic filter (-1 = all, 0 = manual only, or one magic), optional pending orders, optional 2-click confirmation, shows the number of open trades Countdown    time left of the current candle - chart timeframe or any timeframe you choose, turns orange in the last 10 seconds Width / height of both buttons in pixels are inputs.

On the chart Bigger candles as filled boxes with wicks, lower candles as outlines inside them, labels with open time + range in points + countdown, dotted lines at the bigger / lower candle open. The candles are only drawn when the chart timeframe is LOWER than their timeframe (e.g. M1 chart).

Dashboard bigger candle direction, move, time in / left (gold mark = end of the first part), lower candle move / high / low, a live BUY | SELL checklist of every rule, entry mode, status (why it waits), last setup, position, stops, results, auto trading on / off, close all EA trades. X closes it to a small pill, drag the header to move it, hover any line for an explanation.

Installation MT5\Experts\TL HTF Candle Trader Pro.ex5 -> File > Open Data Folder > MQL5\Experts Refresh the Navigator, drag the EA onto a chart (M1 chart recommended to see the candles). Enable Algo Trading. "Allow DLL imports" is only needed for the link buttons.

Main inputs Bigger / lower timeframe, direction, first part (min), bigger candle min. move, lower candle wait (s), lower candle min. move, entry mode, extra distance, pending expiry, delete on flip, max. trades per bigger candle, no trades in the last X min, trading hours, stop mode + buffer, target mode, close at candle end, close on flip, break even, fixed lots or risk %, max. open trades, max. spread, candle colours, tiny button sizes, countdown timeframe, close-all filter.

Risk warning: no profit promise - trading involves high risk. Test on a demo account first.

trader.lifestyle - free tools thread on Forex Factory: <https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4>

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
