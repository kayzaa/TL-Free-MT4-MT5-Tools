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

## ✨ Highlights

- **Two AlgoAlpha TradingView scripts, ported line by line** — Machine Learning Adaptive SuperTrend + Nadaraya-Watson Regression Liquidity Sweeps, combined into one EA.
- **Closed-bar logic** — nothing repaints, one trade per SuperTrend label.
- **Structure-based stops** — the stop sits on the red / green liquidity line, the target is a multiple of the risk.
- **Full trade management** — optional break-even, trailing stop and 2 or 3 take profits with partial closes, all measured in R.
- **Daily trading window and trade cap** — trade only during your hours, with a maximum number of trades per day.
- **INVERSE mode** — trade every signal in the opposite direction as a true mirror.

## 🧠 Strategy rules

The strategy comes from a YouTube video (NASDAQ / NDQ, 1-minute chart) and is built from two indicators:

- **Machine Learning Adaptive SuperTrend [AlgoAlpha]** — ATR length 11 (as in the video), factor 3, k-means training over 100 bars, initial guesses 0.75 / 0.50 / 0.25.
- **Nadaraya-Watson Regression Liquidity Sweeps [AlgoAlpha]** — bandwidth 2 (as in the video), lookback 140, normalization 100, smoothing 21, signal 14, swing points on.

| | SELL | BUY |
|---|---|---|
| **1. Trend** | SuperTrend label **DOWN** (trend flips bearish) | SuperTrend label **UP** (trend flips bullish) |
| **2. Oscillator** | Nadaraya-Watson oscillator in the **red** area (below 0) | Oscillator in the **green** area (above 0) |
| **3. Trigger** | The first **bearish** candle that closes after the label candle → sell at market | The first **bullish** candle that closes after the label candle → buy at market |
| **Stop** | The red line (previous high / upper liquidity level) | The green line (previous low) |
| **Target** | 1.5 × risk | 1.5 × risk |

- One trade per label, closed-bar logic — nothing repaints.
- If the red / green line is not beyond the entry price, the stop falls back to the highest high / lowest low of the last 20 bars (input).
- Optional: max bars to wait for the confirmation candle (0 = until the next label), close on the opposite label.

## 🎯 Trade management

- **INVERSE mode** (default off) — every signal is traded in the opposite direction. The stop goes where the original target was and the target where the original stop was (the red / green line), so the trade is a true mirror (reward : risk = 1 : 1.5). The dashboard header shows **ATS INVERSE** while it is active.
- **Break-even** (optional, default off) — once the trade is x R in profit (default 1.0 R), the stop moves to the entry price, plus optional extra points to lock in.
- **Trailing stop** (optional, default off) — from x R profit (default 1.0 R) the stop follows price at a distance of x R (default 1.0 R). A minimum step in points avoids too many modifications.
- **R** is the initial risk of each trade, so everything scales automatically. Break-even and trailing work in normal and INVERSE mode on MT4 and MT5, and survive a restart (the initial risk is derived from the target, which the EA never moves).
- **2 or 3 take profits** — default is **2 targets**: 50 % closes at TP1 and the stop moves to break-even, the rest runs to TP2. With 3 targets, one third closes at TP1 (stop to break-even), another third at TP2, and the last third runs to TP3. TP1 / TP2 / TP3 in R default to 1.0 / 1.5 / 2.0. Set targets to **1** for the exact video rule (one target at 1.5 R).
  - The broker target of the order is the last TP; the partial closes are done by the EA.
  - The reached stage is stored per position (terminal global variable), so it survives a restart.
  - Very small lots (e.g. 0.01) cannot be split — then only the break-even move is done.
- **Max trades per day** — default 5 (0 = unlimited). Counts the trades this EA opened today (server day); partial closes are not counted twice.
- **Daily trading window** — default ON, 10:00 – 18:00 server time. Set "from" and "to" as HH:MM (e.g. 08:30 and 17:45). New trades only open inside the window; windows over midnight work too (e.g. 22:00 – 02:00). Optionally close open positions at the end time.

## 🖥️ Dashboard & chart

- SuperTrend trend and volatility cluster (high / medium / low).
- Nadaraya-Watson oscillator with a mini chart of the last 70 bars (green / red area).
- Current red / green line, setup state, open position and an **AUTO TRADING ON / OFF** button.
- A simulation of the rules on the loaded chart bars, using the same break-even / trailing rules as live trading (a new stop becomes active from the next candle).
- Trading window status (OPEN / CLOSED).
- **Virtual stop line** (default ON) — an orange dashed step line for every trade of the chart model: initial stop → break-even → each trailing step → exit. It works with AUTO TRADING OFF, so you can watch break-even and trailing behave without placing a single order. It needs break-even, trailing stop or 2 / 3 targets switched on (otherwise the stop never moves).
- TP1 / TP2 / TP3 lines on the chart.
- English tooltips everywhere (input "Show tooltips" switches them off).

## ⚙️ Key inputs

| Input | What it does |
|---|---|
| Risk per trade % / fixed lots | Position size — default 1 % risk, or a fixed lot size |
| RR | Reward : risk of the target (default 1.5) |
| Stop mode | Liquidity line or swing high / low |
| Max bars to wait | Bars to wait for the confirmation candle (0 = until the next label) |
| Direction filter | Limit which trade direction is allowed |
| One position at a time | Only one open position |
| Close on opposite label | Optional exit on the next SuperTrend label |
| INVERSE mode | Trade every signal in the opposite direction |
| Break-even / trailing stop | Optional R-based stop management |
| Targets: number of take profits | 1 / 2 / 3, with TP1 / TP2 / TP3 in R |
| Trading window | On / off, from / to (HH:MM server time), optional close at end |
| Max trades per day | Daily cap (0 = unlimited) |
| Max spread | No entry above this spread |
| Display: virtual stop line | Draws the stop path of every chart-model trade |
| Magic | Magic number of the EA |

## 🛠️ Installation

1. In MetaTrader open **File → Open Data Folder**.
2. **MT4:** copy `TL Adaptive Trend Sweep Pro.ex4` into `MQL4 → Experts`. **MT5:** copy `TL Adaptive Trend Sweep Pro.ex5` into `MQL5 → Experts`.
3. Refresh the Navigator and drag the EA onto a chart (the video uses NASDAQ / NDQ on M1).
4. Tick **"Allow Algo Trading"**. Tick **"Allow DLL imports"** only if you want the dashboard link buttons to work.

## ⚠️ Notes

- The market of the video (NASDAQ) is the reference; other symbols and timeframes may behave very differently.
- Results vary by symbol, broker and costs — spread and commission matter on M1. Test on a demo account first.
- Trading involves risk. Not financial advice.

## 🙏 Credits

- Indicator logic © **AlgoAlpha**, Mozilla Public License 2.0:
  - [Machine Learning Adaptive SuperTrend [AlgoAlpha]](https://www.tradingview.com/script/CLk71Qgy-Machine-Learning-Adaptive-SuperTrend-AlgoAlpha/)
  - [Nadaraya-Watson Regression Liquidity Sweeps [AlgoAlpha]](https://www.tradingview.com/script/IdfeKkUv-Nadaraya-Watson-Regression-Liquidity-Sweeps-AlgoAlpha/)
- Strategy video: [YouTube j6ZKzAyACzM](https://www.youtube.com/watch?v=j6ZKzAyACzM)
- Discussion thread: [Myfxbook — My free EAs & indicators](https://www.myfxbook.com/community/programming/my-free-eas-indicators-/3376352,1)

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
