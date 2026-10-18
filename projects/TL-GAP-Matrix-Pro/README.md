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

## ✨ Highlights

- **28 pairs × 5 timeframes on one chart** — M5, M15, H1, H4 and D1 trend conditions for every pair in a single matrix.
- **Three trend conditions per cell** — MA breakout, linear regression slope and Bollinger-Keltner squeeze; all three agree = the timeframe is in trend.
- **GAP strength engine** — bid ratio, currency strength, absolute strength (GAP), momentum, buyers % and sync.
- **Six signal modes** — S23, S33, S34, S35, W45 and W55, switchable from tabs in the header.
- **ATR-based targets** — TP / SL from the ATR of the next higher timeframe.
- **Trading OFF by default** — optional one-click BUY / SELL or auto trading on confirmed signals.

## 🧠 How it works

### The matrix

For every pair the matrix shows the **spread**, the **M15 ATR** and the **daily open side**. Then, for **M5 M15 H1 H4 D1**, it checks three conditions:

| Condition | Definition |
|---|---|
| **MA breakout** | Price vs. SMA 20 |
| **Linear regression slope** | Slope over 20 bars |
| **Bollinger-Keltner squeeze** | Yellow ring = squeeze |

When all three agree, the cell turns **green** or **red** — that timeframe is in trend. The matrix ends with the **ALIGN**, **GAP** and **SIGNAL** columns.

### Signals, filters and targets

- **Signal modes:** S23, S33, S34, S35, W45, W55 (tabs in the header).
- **Filters:** daily open, GAP direction (min 1.0), max spread. A signal must hold for **60 seconds** to be confirmed.
- **Targets:** the ATR of the next higher timeframe after the smallest timeframe in trend, scaled by TP / SL multipliers.

### GAP

Bid ratio, currency strength 0–9, absolute strength (GAP), momentum (30 min), buyers % and sync 0–7.

## 🖥️ Dashboard & chart

- **Best setup** card.
- **Pair inspector** — a "5 charts" button and one-click BUY / SELL.
- **Buyers vs sellers**, **GAP matrix** and **Signal tracker** (virtual pips, spread included).
- **Market pulse** — radar, stats and sessions.
- **X** folds the whole suite to a pill. Hover over anything for an explanation.

## ⚙️ Trading

| Input | What it does |
|---|---|
| Trading: enable the BUY / SELL buttons | One-click trading — a second click within 3 s confirms |
| Trading: open a trade on every confirmed signal | Auto trading — one trade per pair, with max trades, magic number and close on signal flip / end |

Both are **OFF by default**.

## 🛠️ Installation

1. In MetaTrader open **File → Open Data Folder**.
2. **MT4:** copy `TL GAP Matrix Pro.ex4` into `MQL4 → Experts`. **MT5:** copy `TL GAP Matrix Pro.ex5` into `MQL5 → Experts`.
3. Refresh the Navigator, drag the EA onto **one** chart (any symbol / timeframe) and maximise the chart.
4. Tick **"Allow DLL imports"** only if you want the link buttons to work.
5. The first start loads 28 pairs × 5 timeframes of history — this takes a few seconds (progress bar).

## ⚠️ Notes

- Trading is risky. Test on a demo account first.
- The signal tracker counts virtual pips on past signals — it describes the past, not the future.
- Free, no lock, no expiry.

## 🙏 Credits

Idea: **SwingMan**'s ["GAP without Excel" dashboard](https://www.forexfactory.com/thread/657370) and [the GAP method](https://www.forexfactory.com/thread/561309) on Forex Factory.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
