<div align="center">

# ⚡ TL Adaptive Trend Sweep Pro

**Machine-learning adaptive SuperTrend + Nadaraya-Watson liquidity sweeps, automated as an EA with live signal dashboard.**

![version](https://img.shields.io/badge/version-v1.09-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Adaptive_Trend_Sweep_Pro_XAUUSD_M1_tlats_scale1.png" alt="TL Adaptive Trend Sweep Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Adaptive Trend Sweep Pro.ex4`](MT4/TL%20Adaptive%20Trend%20Sweep%20Pro.ex4) |
| **MT5** | [`TL Adaptive Trend Sweep Pro.ex5`](MT5/TL%20Adaptive%20Trend%20Sweep%20Pro.ex5) |

> Compiled build only — source code is not published.

## Overview

Thread: <https://www.myfxbook.com/community/programming/my-free-eas-indicators-/3376352,1>

What it trades The strategy from the YouTube video "j6ZKzAyACzM" (NDQ 1-minute chart), built from two open-source TradingView scripts by AlgoAlpha, ported line by line:
- Machine Learning Adaptive SuperTrend [AlgoAlpha]  - ATR length 11 (video), factor 3, k-means training 100 bars, initial guesses 0.75 / 0.50 / 0.25
- Nadaraya-Watson Regression Liquidity Sweeps [AlgoAlpha] - bandwidth 2 (video), lookback 140, normalization 100, smoothing 21, signal 14, swing points on

SELL  1. SuperTrend label DOWN (trend flips bearish)
- Nadaraya-Watson oscillator in the RED area (below 0)
  - a BEARISH candle closes (first one after the label candle) -> sell at market. Stop = the red line (previous high / upper liquidity level). Target = 1.5 x risk.
BUY   mirror image: label UP, GREEN area, BULLISH candle, stop = green line (previous low), target 1.5 x risk.

One trade per label. Closed-bar logic - nothing repaints. If the red / green line is not beyond the entry price, the stop falls back to the highest high / lowest low of the last 20 bars (input).

Installation MT5: copy MT5\TL Adaptive Trend Sweep Pro.ex5 to  File -> Open Data Folder -> MQL5\Experts MT4: copy MT4\TL Adaptive Trend Sweep Pro.ex4 to  File -> Open Data Folder -> MQL4\Experts Refresh the Navigator, drag the EA onto a chart (video: NASDAQ / NDQ, M1). Tick "Allow Algo Trading" and "Allow DLL imports" (DLL only opens the links of the buttons). Source files (.mq5 / .mq4) are included - one source file, compiles on both platforms.

Dashboard SuperTrend trend + volatility cluster (high / medium / low), Nadaraya-Watson oscillator with a mini chart of the last 70 bars (green / red area), current red / green line, setup state, open position, auto trading ON / OFF button and a backtest of the loaded chart bars. All elements have English tooltips (input "Show tooltips" switches them off).

Inverse mode (v1.01) Input "INVERSE mode" (default off): every signal of the video is traded in the opposite direction. The stop goes where the original target was and the target where the original stop was (the red / green line), so the trade is a true mirror (reward : risk = 1 : 1.5). The dashboard header shows "ATS INVERSE" while it is active.

Break-even and trailing stop (v1.02, both optional, default OFF) Break-even: when the trade is x R in profit (default 1.0 R), the stop moves to the entry price (+ optional extra points to lock in). Trailing stop: from x R profit (default 1.0 R) the stop follows the price at a distance of x R (default 1.0 R). R = the initial risk of the trade, so it scales with every trade automatically. Min. step in points avoids too many modifications. Both work in normal and INVERSE mode, on MT4 and MT5, and survive a restart (the initial risk is taken from the target, which the EA never moves). The chart backtest on the dashboard uses the same rules (new stop active from the next candle).

2 or 3 take profits (v1.03) - DEFAULT: 2 targets (50 % at TP1 + break-even, rest at TP2) (set it to 1 target for the exact video rule: 1 x target at 1.5 R) "Targets: number of take profits" = 1 / 2 / 3. TP1 / TP2 / TP3 in R (default 1.0 / 1.5 / 2.0). 2 targets: at TP1 half of the position is closed and the stop moves to break-even, the rest runs to TP2. 3 targets: at TP1 one third is closed and the stop moves to break-even, at TP2 another third, the last third runs to TP3. The broker target of the order is the last TP; the partial closes are done by the EA. The reached stage is stored per position (terminal global variable), so it survives a restart. Very small lots (e.g. 0.01) cannot be split - then only the break-even move is done. TP1 / TP2 / TP3 lines are drawn on the chart.

Max trades per day (v1.03) - DEFAULT: 5 "Trading: max trades per day" (0 = unlimited). Counts the trades opened today (server day) by this EA - partial closes are not counted twice.

Daily trading window (v1.04) - DEFAULT: ON, 10:00 - 18:00 server time "Trading window" on / off, "from" and "to" as HH:MM in server time (e.g. 08:30 and 17:45). New trades only inside the window - afterwards the EA waits for the next day. Windows over midnight work too (e.g. 22:00 - 02:00). Optional: close open positions at the end time. The dashboard shows the window and whether it is OPEN or CLOSED.

Virtual stop line (v1.09) "Display: virtual stop line" (default ON) draws an orange dashed step line for every trade of the chart model: initial stop -> break-even -> each trailing step -> exit. It works with AUTO TRADING OFF, so you can watch break-even / trailing behave without placing any order. Needs break-even, trailing stop or 2 / 3 targets switched on (otherwise the stop never moves).

Main inputs Risk per trade % (default 1 %) or fixed lots, RR (1.5), stop mode (liquidity line / swing), max bars to wait for the confirmation candle (0 = until the next label), direction filter, one position at a time, optional close on opposite label, trading window, max trades per day, max spread, magic.

Honest test results (MT5 strategy tester, RoboForex, 10,000 USD, 1 % risk) The indicator values were checked against an independent re-implementation of the Pine code: EURUSD 0.51, GBPJPY 0.71, BTCUSD 0.74 - spread / commission is paid in both directions. Break-even / trailing stop (defaults 1 R), XAUUSD M1: Multiple targets, XAUUSD M1 (defaults 1.0 / 1.5 / 2.0 R):

## Nasdaq (the market of the video) could not be tested - no data on the test account.

=> The rules do NOT show a stable edge in these tests. Use a demo account first.

Credits / licence Indicator logic (c) AlgoAlpha, Mozilla Public License 2.0: <https://www.tradingview.com/script/CLk71Qgy-Machine-Learning-Adaptive-SuperTrend-AlgoAlpha/> <https://www.tradingview.com/script/IdfeKkUv-Nadaraya-Watson-Regression-Liquidity-Sweeps-AlgoAlpha/> This port is distributed as source under the same MPL 2.0 terms. Trading involves risk. Past results do not guarantee future results. Not financial advice.

YouTube  <https://www.youtube.com/@traderlifestyle> WhatsApp <https://wa.me/18585003724>

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
