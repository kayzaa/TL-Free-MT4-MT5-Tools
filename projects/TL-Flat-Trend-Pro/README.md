<!-- auto-generated: remove this line after hand-editing so publish keeps your text -->
<div align="center">

# ⚡ TL Flat Trend Pro

**FlatTrend Defolt rebuilt 1:1 for MT4/MT5 — the four-colour ADX + Parabolic SAR histogram — as an EA with BUY/SELL pills, SAR-flip exit and an optional Autotrade mode.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Flat_Trend_Pro_screenshot.png" alt="TL Flat Trend Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Flat Trend Pro Indicator.ex4`](MT4/TL%20Flat%20Trend%20Pro%20Indicator.ex4) |
| **MT4** | [`TL Flat Trend Pro.ex4`](MT4/TL%20Flat%20Trend%20Pro.ex4) |
| **MT5** | [`TL Flat Trend Pro Indicator.ex5`](MT5/TL%20Flat%20Trend%20Pro%20Indicator.ex5) |
| **MT5** | [`TL Flat Trend Pro.ex5`](MT5/TL%20Flat%20Trend%20Pro.ex5) |

> Compiled build only — source code is not published.

## Overview

What it is A 1:1 rebuild of the "FlatTrend Defolt" indicator, turned into an Expert Advisor for MT4 and MT5 with our Canvas dashboard, BUY / SELL pills on the chart, alerts and two modes:
- **INDICATOR ONLY** — signals, pills, alerts and dashboard - no orders (default) AUTOTRADE        opens on BUY / SELL and closes by the exit rule The package also contains the stand-alone indicator "TL Flat Trend Pro Indicator", which draws the original histogram window with the same four colours and values. This is an independent rebuild of FlatTrend Defolt.

The original rules (unchanged) Every bar is coloured from two standard indicators:
- **+DI / -DI** — ADX(2) on the close SAR         Parabolic SAR (step 0.2, maximum 0.2) Buffer 1  RED          SAR above the close  and  -DI above +DI   (DMI down, SAR down) Buffer 2  GREEN        SAR below the close  and  +DI above -DI   (DMI up,   SAR up) Buffer 3  SALMON       SAR above the close  but  +DI above -DI   (SAR and DMI disagree) Buffer 4  LIGHT GREEN  SAR below the close  but  -DI above +DI   (SAR and DMI disagree) Equal values (SAR = close or +DI = -DI): no bar. Values are 0 / 1, the window is 0 - 1. Like the original, the indicator calculates the newest 400 bars and updates the running bar on every tick (input "Bars to calculate", 0 = all bars). Timeframe input: current timeframe by default, like the original. Green / red = SAR and DMI agree (trend), light green / salmon = they disagree (flat or a trend that is fading).

What I added (TL additions, not part of the original)
- **Signals** — BUY  = the first CLOSED bar that turns green SELL = the first CLOSED bar that turns red Optional: wait for 2, 3 ... bars in the new colour (input "Closed bars in the new colour"). Closed bars only - a signal never disappears afterwards. Exit rule   SAR flip (default): a long is closed when the SAR moves above the close, a short when it moves below it. Alternatives: opposite signal (stop and reverse) or "bar leaves green / red". Pills       glowing BUY / SELL pills below / above the signal bar, gold EXIT pills, for the whole loaded history - anchored to time and price, they follow scrolling and zooming. On chart    Parabolic SAR dots (green below / red above the price) and a Flat Trend colour ribbon at the bottom of the chart (works in MT4 and MT5, also on a higher signal timeframe). MT5: the original histogram window is added automatically. Trading     stop at the SAR of the signal bar (+ buffer), ATR, fixed pips or none; optional take profit in R; optional SAR trailing stop; fixed lots or % risk; spread filter; one trade at a time; CLOSE ALL closes only this EA's trades. Alerts      popup, sound, push (off by default). Dashboard   see below. The signal rules are a practical way to trade the colours; they are not a promise of better results than reading the indicator by hand.

Dashboard
- **Header** — animated logo, RoboForex / WhatsApp / YouTube, Forex Factory thread FLAT TREND       live state of the running bar (like the original window), a mini histogram of the last 64 bars with signal ticks, last closed bar and how long it has the colour, +DI / -DI, SAR and its side, colour legend SIGNALS          last signal, the signal model position (long / short / waiting) with its pips, entry and exit rule, number of signals in the history MODE · STOP      INDICATOR ONLY / AUTOTRADE, stop, target, lots POSITION         real positions of this EA, stops, results, MODE switch, CLOSE ALL Drag the header to move it, X folds it to a small pill (click to reopen). Hover any block for an explanation (tooltips can be switched off). The dashboard moves away from other trader.lifestyle panels on the same chart. Dark chart theme, restored on removal.

Differences to the original
- The original only colours bars. Signals, exits, pills, alerts and trading are additions.
- Signals use closed bars. The running bar of the histogram still changes during the bar, exactly like in the original.
- Optional higher timeframe: the rebuild reads the higher-timeframe bar that covers the same TIME. The default is the current timeframe, like the original.
- MT4 and MT5 calculate ADX slightly differently (each platform's own ADX), so the colours of the MT4 and MT5 versions can differ on a few bars - each version follows the original rules with its own platform's ADX.

Installation
- **MT5: MT5\Experts\TL Flat Trend Pro.ex5** — -> File > Open Data Folder > MQL5\Experts MT5\Indicators\TL Flat Trend Pro Indicator.ex5 -> MQL5\Indicators MT4: MT4\Experts\TL Flat Trend Pro.ex4            -> File > Open Data Folder > MQL4\Experts MT4\Indicators\TL Flat Trend Pro Indicator.ex4 -> MQL4\Indicators Refresh the Navigator (right-click > Refresh) and attach the EA to a chart. It uses the chart's symbol and timeframe. For AUTOTRADE enable Algo Trading / AutoTrading in the terminal. MT5 adds the histogram window by itself (the indicator file must be in MQL5\Indicators). In MT4 drag the indicator onto the chart if you want the window too. "Allow DLL imports" is only needed for the website buttons (they open your browser via the Windows shell32.dll). The EA trades without it.

Main inputs (EA) Mode: INDICATOR ONLY / AUTOTRADE (also a dashboard button). Flat Trend: timeframe, ADX period, SAR step, SAR maximum (FlatTrend Defolt: current, 2, 0.2, 0.2). Signals: closed bars in the new colour, exit rule, direction. Stop & target: stop mode, SAR buffer, ATR multiple, fixed pips, take profit in R, SAR trailing. Money: fixed lots (default 0.01) or risk %, max. lots, max. spread. Display: dashboard, position, auto-avoid, tooltips, BUY / SELL pills, EXIT pills, SAR dots, ribbon, MT5 histogram window, history bars, dark theme, alerts (popup / sound / push). Other: magic number, order comment, slippage.

Main inputs (indicator) Timeframe, ADX period, SAR step, SAR maximum, bars to calculate (400 like the original, 0 = all), link buttons, tooltips. Colours and widths in the "Colours" tab.

Risk warning: no profit promise - trading involves high risk. Test on a demo account first.

trader.lifestyle - free tools thread on Forex Factory: <https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4>

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
