<!-- auto-generated: remove this line after hand-editing so publish keeps your text -->
<div align="center">

# ⚡ TL Freebie System Pro

**Dredding82's Freebie system: Semafor + pivot fail + Stochastic + Heikin Ashi in one EA.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Freebie_System_Pro_fbs_shot_M15.png" alt="TL Freebie System Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT5** | [`TL Freebie System Pro.ex5`](MT5/TL%20Freebie%20System%20Pro.ex5) |

> Compiled build only — source code is not published.

## Overview

Built after the Forex Factory thread "Price Action Trading with Indicators! The Freebie System" by Dredding82 (2011) <https://www.forexfactory.com/thread/276813-price-action-trading-with-indicators-the-freebie-system>

ONE file (.ex5). All indicators of the original template are calculated and drawn by the EA itself - nothing else to install:
- Heiken Ashi candles (the normal candles are hidden behind them)
- Stochastic 10,3,3 (simple, close/close) in its own window
- ZZ Semafor dots, 3 levels (5 / 13 / 34)
- ZigZag line (12 / 5 / 3)
- Fib pivots + mid pivots (daily on M1-H1, weekly on H4, monthly on D1 = "Myperiod")
- Daily Range Calculator (ADR, range used today, expected high / low) in the panel

## BUY - trade with the trend of a higher timeframe

- ZZ Semafor dot on the BOTTOM (within 1-3 candles)
- Failed at a pivot: the candle touches / pierces a Fib pivot (1-5 pips are ok) and closes back ABOVE it
- Stoch crossed UP
- Heiken Ashi candle closed GREEN SL = last low (the semafor dot) + buffer TP = 1:1 - 1:4 risk:reward or the other pivots ("the Daily Range indicator will tell you what pivot to max profits")
SELL = the mirror image. Everything is checked at CANDLE CLOSE.

Money management (post #1041): risk 2% of the account, close 1/2 of the lots at 1:1, move the SL to break even -> "a free trade". Post #234: a trailing stop is safer when you leave the trade alone. Friday: no new trades after London close.

## How The EA Trades

- Signal = all enabled rules are true on the candle that just closed (and were not on the candle before). The trade opens at the start of the next candle.
- Trend (default): colour of the last CLOSED Heiken Ashi candle of the higher TF (M1-M5 -> H1, M15-H1 -> H4, H4 -> D1, D1 -> W1). Other modes: higher highs / lower lows of the higher TF, EMA, or off.
- SL: below / above the semafor dot (+2 pips buffer, min. 5 pips).
- TP (default "pivot inside the daily range"): the farthest pivot that today's average daily range still allows, at least 1:1, at most 1:4. Other modes: next pivot, fixed R:R, none.
- At 1R: 50% closed, SL to break even + 1 pip.
- One trade at a time per chart (magic number).

## Installation

- Copy "TL Freebie System Pro.ex5" into  File > Open Data Folder > MQL5 > Experts
- Restart MT5 or right-click "Expert Advisors" in the Navigator > Refresh
- Drag the EA onto a chart (e.g. EURUSD M15 or H1)
- Tick "Allow Algo Trading" and "Allow DLL imports" (DLL only for the 3 link buttons)
- Click "Algo Trading" in the toolbar

- Set "Trading ON" = false to use it as a pure signal / alert tool.

## Panel

- Status: position, higher-TF trend, trading state, last signal
- THE RULES: YES / no for BUY and SELL, rule by rule, for the last closed candle
- Fib pivots + Daily Range: all levels, nearest level, ADR bar, expected high / low
- Position (R multiple, SL, TP, partial done), results, chart history of the signals
- Buttons: TRADING ON/PAUSED, CLOSE ALL, YOUTUBE, ROBOFOREX, WHATSAPP
- Click "MYFXBOOK" to open the original thread. "–" minimises the panel.

## Risk Warning

Trading involves high risk. Past results are no guarantee. No profit promise. Test it on a demo account first - as Dredding82 said himself. See BACKTEST.txt for the backtest results.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
