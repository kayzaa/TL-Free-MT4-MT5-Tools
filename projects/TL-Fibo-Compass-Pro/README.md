<div align="center">

# ⚡ TL Fibo Compass Pro

**FiboCompassArrows rebuilt for MT4 and MT5 with the first animated canvas quant panel.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Indicator-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Fibo_Compass_Pro_fcp_6_H1.png" alt="TL Fibo Compass Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Fibo Compass Pro.ex4`](MT4/TL%20Fibo%20Compass%20Pro.ex4) |
| **MT5** | [`TL Fibo Compass Pro.ex5`](MT5/TL%20Fibo%20Compass%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- 🧭 **Daily Fibonacci compass** — built automatically from the high / low of the previous completed D1 candle.
- 🎯 **Every level has a job** — breakout entries, retrace zones, targets and "stop trading" extensions.
- 🏹 **Arrows that stay on the chart** — full history instead of the original's vanishing arrows.
- 🔕 **No arrow spam** — by default only the FIRST hit of each level per day fires.
- 🖥️ **Animated dashboard** — live zone, compass gauge, every level with price and distance in pips.
- 🔌 **EA-ready buffers** — buy, sell, TP / pivot and stop-trading signals.

## 🧠 How it works

The indicator takes the high / low of the previous completed D1 candle (any source timeframe can be chosen; the small Sunday candle is skipped) and builds the compass:

| Level | Name | Meaning |
|---|---|---|
| **200 %** | STOP TRADING | Full-range extension — stop opening trades |
| **138.2 %** | BUY TP | Target for breakout buys |
| **100 %** | BREAKOUT BUY | Previous high |
| **78.6 %** | RETRACE SELL | Top of the retrace sell zone (78.6 – 100 %) |
| **50 %** | PIVOT / TP | Middle — target for retrace trades |
| **23.6 %** | RETRACE BUY | Top of the retrace buy zone (0 – 23.6 %) |
| **0 %** | BREAKOUT SELL | Previous low |
| **-38.2 %** | SELL TP | Target for breakout sells |
| **-100 %** | STOP TRADING | Full-range extension — stop opening trades |

**Arrows when price hits a level:** up arrow = buy level, down arrow = sell level, diamond = TP / pivot, cross = stop-trading level. Hover any arrow for the details.

**Trigger mode:**
- **Touch** — live, the moment price touches the level (like the original).
- **Close cross** — confirmed when a candle closes through the level.

**Alerts:** popup / sound / push / e-mail, separately for entry, TP and stop levels.

**History:** arrows on all calculated bars plus the level sets of the last 5 days.

## 🖥️ Dashboard & chart

- Animated panel — hover any block for an explanation.
- Live zone (e.g. "RETRACE BUY ZONE", "BREAKOUT SELL - BELOW LOW"), compass gauge with the price marker, every level with price and distance in pips, D1 range and the last signal.
- Click **X** to close it — a small pill stays; click the pill to open it again.
- Drag the header (or the pill) to move it anywhere on the chart.
- Position and open / closed state survive timeframe and symbol changes.

## 🔌 Buffers for EAs

| Buffer | Signal |
|---|---|
| 0 | Buy |
| 1 | Sell |
| 2 | TP / pivot |
| 3 | Stop-trading |

`EMPTY_VALUE` = no signal.

## 🩹 Why the original did not work

- **"unsupported file extension"** — the code must be saved as `.mq4` (not `.txt`) inside `MQL4\Indicators`.
- The original only painted arrows on the current candle and erased them on every tick, so nothing stayed on the chart. This version keeps the full history.

## 🛠️ Installation

1. **MT5:** copy `MT5/TL Fibo Compass Pro.ex5` to `File → Open Data Folder → MQL5 → Indicators`.
   **MT4:** copy `MT4/TL Fibo Compass Pro.ex4` to `File → Open Data Folder → MQL4 → Indicators`.
2. Refresh the Navigator and drag the indicator onto a chart (any timeframe below D1).
3. Tick **Allow DLL imports** only if you want the YouTube / RoboForex / WhatsApp / Forex Factory buttons to work.

## ⚠️ Notes

- In **Touch** mode arrows fire live on the developing candle; use **Close cross** if you want confirmed signals only.
- The levels are a framework for decisions, not a guarantee. Test on a demo account first.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
