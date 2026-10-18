<div align="center">

# ⚡ TL Gold Velocity Pro

**Catch fast gold bursts and ride the move — velocity detection with a live speed gauge.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Gold_Velocity_Pro_gvp_panel_compact_preview.png" alt="TL Gold Velocity Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT5** | [`TL Gold Velocity Pro.ex5`](MT5/TL%20Gold%20Velocity%20Pro.ex5) |

> Compiled build only — source code is not published.

## Overview

"Catch FAST movement and jump on the train while it lasts - a drop or rise of ~10 $ with an acceleration of 1 $ or more per second, TP 2-5 $, SL 2 $."

plus the rebound idea (catch the bounce after the hype), the "second tool" (news scoring, DXY, FED rate, MACD, BB, volume, RSI) and a greed shield ("without greed I would be around 2000 $ today").

## Install

- Copy "TL Gold Velocity Pro.ex5" into  File > Open Data Folder > MQL5 > Experts (optional: folder "src" = full source code, compiles in MetaEditor).
- Restart MT5 or right-click "Expert Advisors" > Refresh in the Navigator.
- Drag the EA onto an XAUUSD chart (any timeframe, M1 recommended).
- Enable "Algo Trading". For the panel buttons: allow DLL imports.
- Run it on a VPS close to your broker's server - see LATENCY below.

## How It Works (tick by tick)

MOVE   = net price move inside a window (e.g. 15 $ within 30 s) SPEED  = $ per second over the last second (e.g. >= 1 $/s) Both in the same direction = BURST.
- **RIDE mode:** — enter WITH the burst (market order). REBOUND mode: wait until the burst is exhausted (speed drops below X % of its peak AND price comes back X $ from the extreme), then trade the bounce AGAINST the burst.
Exit: hard SL at the broker + tick-precise trailing stop (+ optional TP, break-even, time exit). SL/TP are re-anchored to the real fill price (bursts slip!).

## Sniper (default)  15 $ in 30 s, 1 $/s, SL 10 $, trailing from +2 $ (distance 1 $),

- **no fixed TP, max spread 1.50 $.** — ~10 trades/month.
BALANCED          10 $ in 20 s, SL 5 $, trailing 0.5/0.5, 07-23 server time. SCALPER           8 $ in 30 s, 0.5 $/s, SL 5 $, trailing 1/0.5, 07-23. FF-ORIGINAL       your idea 1:1: 10 $ / 60 s / 1 $/s, TP 3 $, SL 2 $. REBOUND           10 $ in 30 s burst, bounce after exhaustion, TP 8 / SL 4. MANUAL            every value from groups 1-4 yourself.

## Greed Shield (group 5)

Daily target (default 5 %) -> close everything, done for the day. Daily loss stop (5 %), max trades per day, pause after N losses in a row. Goal tracker in the panel: 100 $ -> 100,000 $ at X % per day.

## Intel (group 6b) - "the second tool"

- Liquidation sweep: burst must take out the high/low of the last X minutes.
- News score (LIVE only, MQL5 calendar): for every USD high/medium event the EA learns from 1 year of calendar history how many $ gold moved per sigma of surprise (actual vs. forecast). After a release it shows the expected gold reaction; optional filter "trade only in news-score direction". Report: MQL5\Files\gvp_newsscore.csv
- DXY (real symbol or synthetic from EURUSD/USDJPY/GBPUSD/USDCAD/USDSEK/USDCHF), FED rate decision from the calendar, MACD, Bollinger, volume, RSI.
- All combined in a BIAS SCORE -100..+100 (+ = gold up), optional filter.
News mode: OFF / ONLY inside news window / AVOID news.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
