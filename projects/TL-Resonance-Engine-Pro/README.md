<div align="center">

# ⚡ TL Resonance Engine Pro

**One engine, one 0–100 resonance score: SuperTrend trend, smoothed RSI momentum, estimated buy/sell volume and more — momentum-coloured candles.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

## 📥 Download

| Platform | File |
|---|---|
| **MT5** | [`TL Resonance Engine Pro.ex5`](MT5/TL%20Resonance%20Engine%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **One score to rule the chart** — trend, momentum, volume, multi-timeframe agreement and ADX fused into a single 0–100 resonance score.
- **Momentum-coloured candles** — cyan (bull) / magenta (bear), brighter = stronger momentum.
- **Complete trade plan on every signal** — Entry, Stop and TP1 / TP2 / TP3 at 1R / 2R / 3R, with break-even and SuperTrend trailing.
- **Smart-money overlay** — BOS / CHoCH, order blocks, premium / equilibrium / discount zones and trendlines.
- **Built-in volume profile** and a resonance oscillator strip with live value tags.
- **Closed bars only** — signals do not repaint.

## 🧠 How it works

### The resonance score

**Trend** comes from SuperTrend (ATR 10 × 3). Four independent readings then add up to the score:

| Reading | What it measures | Points |
|---|---|---|
| **Momentum** | Smoothed RSI on a −100..+100 scale with a slow signal line | 25 |
| **Volume** | Estimated buy vs. sell volume of the last 20 bars | 25 |
| **MTF matrix** | Trend + momentum on 5m / 15m / 1H / 4H / 1D — share agreeing | 25 |
| **ADX** | Trending vs. ranging market | 25 |

### Strategy rules

> **BUY / SELL:** the first bar of a new trend leg with a score ≥ the minimum score (default 60). After a closed position the EA can re-enter in the same leg when the score qualifies again.

| Item | Rule |
|---|---|
| **Stop** | SuperTrend line + ATR buffer |
| **Targets** | TP1 / TP2 / TP3 = 1R / 2R / 3R |
| **After TP1** | Stop moves to break-even and trails the SuperTrend line |
| **After TP2** | Stop moves to TP1 |
| **Exit** | An opposite trend flip closes the position |
| **Risk** | Default 1 % of the balance per trade |

## 🖥️ Dashboard & chart

- **Resonance oscillator strip** on top — momentum, slow line, resonance cloud, volume pressure, ADX — with live value tags.
- **Smart-money structure** — BOS / CHoCH lines, Bullish / Bearish labels, Resistance / Support pivots.
- **Order blocks** — Internal OB and Intraday OB (bullish blue / bearish red), with their volume share.
- **Premium / Equilibrium / Discount zones** and trendlines.
- **Volume profile** on the right — selling volume magenta, buying volume blue.
- **Trade pills** — Entry / SL / Trailing / TP1–TP3 pills and price tags, plus a resonance timeline at the bottom.
- **Dashboard** — Resonance Engine, MTF Matrix Monitor, Core Data & Risk, Signal Engine, Position Tracking, AUTO TRADING ON/OFF, CLOSE ALL. Close with **X**, reopen with the pill, drag the header to move it.

## 🛠️ Installation

1. Copy the `.ex5` to `File → Open Data Folder → MQL5 → Experts`.
2. Refresh the Navigator and drag the EA onto a chart (e.g. XAUUSD M15).
3. Enable **"Allow Algo Trading"** for auto trading.
4. Enable **"Allow DLL imports"** only if you want the link buttons to open in the browser — the EA works without it.

## ⚠️ Notes

- **Auto trading is ON by default** — switch it off in the inputs or with the dashboard button if you only want the signals.
- Buy / sell volume is **estimated** from candle data (close position in the bar range), not real order flow.
- The black chart theme, engine candles and price scale are restored when you remove the EA.
- Educational tool, no investment advice. Trading involves high risk — test on a demo account first.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
