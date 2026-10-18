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

## ✨ Highlights

- 🕯️ **Trade with the bigger candle** — trades the LOWER timeframe candle (default M2) only in the direction of the running BIGGER timeframe candle (default M10).
- 🎯 **Three entry modes** — market, buy/sell stop at the current lower candle's extreme, or at the previous lower candle's extreme.
- 🛡️ **Structured exits** — candle-based stops, R-multiple targets, close at candle end, close on flip, break-even.
- 📦 **Bigger TF candles drawn on your chart** — TL Bigger TF Candles Pro is built in.
- 🔘 **Tiny CLOSE ALL button + candle countdown** — draggable, position saved per chart.
- ✅ **Live BUY | SELL checklist** — the dashboard shows every rule and why the EA is waiting.

## 🧠 Strategy rules

BUY rules are listed below — SELL is the exact mirror.

| # | Rule | Detail |
|---|---|---|
| 1 | **Direction** | Price is ABOVE the open of the running bigger candle → only BUY trades (below → only SELL). Never against the bigger candle. |
| 2 | **First part** *(optional)* | Wait X minutes after the bigger candle opened (`0` = off) |
| 3 | **Big move** *(optional)* | The bigger candle must already be X points above its open (`0` = any) |
| 4 | **Lower wait** *(optional)* | Wait X seconds after the lower candle opened (`0` = off) |
| 5 | **Trigger** | The lower candle must move PAST ITS OWN OPEN in the same direction by at least "min. move" points (default 20 points = 2 pips on a 5-digit pair, 0.20 on gold) |

**Entry modes**
- **Market** — buy at market as soon as rules 1–5 are true.
- **Stop current high** — buy stop at the HIGH of the current lower candle + extra distance.
- **Stop previous high** — buy stop at the HIGH of the previous lower candle + extra distance. If price is already above it: skip, or send a market order (input).

Unfilled stop orders are deleted at the end of the lower candle (or the bigger candle — input) and when the bigger candle flips to the other side of its open.

**Limits** — one trade per lower candle, max. trades per bigger candle (default 1), max. open trades, no new trades in the last X minutes of the bigger candle, trading hours and max. spread. The EA respects the broker trading sessions.

**Exits**

| Exit | Options |
|---|---|
| **Stop loss** | Beyond the bigger candle open / lower candle open / lower candle low (+ buffer), a fixed distance, or none |
| **Take profit** | R multiple of the stop (default 1.5R), fixed points, or none |
| **Candle end** | Close the trade when the bigger candle ends (default on) |
| **Flip** *(optional)* | Close when the bigger candle flips against the trade |
| **Break even** *(optional)* | Stop to entry + X points after +Y points profit |

## 🖥️ Dashboard & chart

**On the chart** — bigger candles as filled boxes with wicks, lower candles as outlines inside them, labels with open time + range in points + countdown, and dotted lines at the bigger / lower candle open. The candles are only drawn when the chart timeframe is LOWER than their timeframe (e.g. an M1 chart).

**Tiny buttons** (top right — drag them anywhere by the grip, the position is saved per chart; width / height are inputs):
- **CLOSE ALL** — closes ALL trades of the chart symbol (like TL Close All Pro): magic filter (`-1` = all, `0` = manual only, or one magic), optional pending orders, optional 2-click confirmation, shows the number of open trades.
- **Countdown** — time left of the current candle, for the chart timeframe or any timeframe you choose; turns orange in the last 10 seconds.

**Dashboard** — bigger candle direction, move, time in / left (gold mark = end of the first part), lower candle move / high / low, a live BUY | SELL checklist of every rule, entry mode, status (why it waits), last setup, position, stops, results, auto trading on / off and close all EA trades. **X** closes it to a small pill, drag the header to move it, hover any line for an explanation.

## ⚙️ Key inputs

| Group | Inputs |
|---|---|
| **Timeframes & direction** | Bigger / lower timeframe, direction |
| **Rules** | First part (min), bigger candle min. move, lower candle wait (s), lower candle min. move |
| **Entry** | Entry mode, extra distance, pending expiry, delete on flip |
| **Limits** | Max. trades per bigger candle, no trades in the last X min, trading hours, max. open trades, max. spread |
| **Exits** | Stop mode + buffer, target mode, close at candle end, close on flip, break even |
| **Money management** | Fixed lots or risk % |
| **Visuals & tools** | Candle colours, tiny button sizes, countdown timeframe, close-all filter |

## 🛠️ Installation

1. Copy `MT5/TL HTF Candle Trader Pro.ex5` to `File → Open Data Folder → MQL5 → Experts`.
2. Refresh the Navigator and drag the EA onto a chart (an **M1 chart** is recommended to see the candles).
3. Enable **Algo Trading**.
4. **Allow DLL imports** is only needed for the link buttons.

## ⚠️ Notes

- MT5 only.
- The CLOSE ALL button acts on all trades of the chart symbol that match its magic filter — including manual trades when the filter allows it.
- No profit promise — trading involves high risk. Test on a demo account first.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
