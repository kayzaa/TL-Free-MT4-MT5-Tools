<div align="center">

# ⚡ TL Volume Pulse Pro

**Own volume-pulse oscillator EA: SMA 200 bias, entry on the second closed pulse bar after a zero cross.**

![version](https://img.shields.io/badge/version-v1.10-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/Volume%20Pulse%20Pro%20-%20XAUUSD%20H1.png" alt="TL Volume Pulse Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Volume Pulse Pro.ex4`](MT4/TL%20Volume%20Pulse%20Pro.ex4) |
| **MT5** | [`TL Volume Pulse Pro.ex5`](MT5/TL%20Volume%20Pulse%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- 💓 **Own Volume Pulse engine** — tick volume signed by where each candle closes, smoothed into an oscillator from -100 to +100.
- 🧭 **SMA 200 bias** — price above = buys only, below = sells only.
- ⏳ **Patient entries** — only after the SECOND closed pulse bar of a zero cross, with the pulse beyond its signal line.
- 🛡️ **Swing + ATR stops** — a stop that would be too wide means no trade.
- 🚦 **Traffic-light signal engine** — every condition visible live in the panel, plus a quality score.
- ✍️ **Written from scratch** — own code, own formulas, no third-party code.

## 🧠 Strategy rules

### 1. Volume Pulse (own engine)

Every candle's tick volume is signed by WHERE the candle closes inside its range (close at the high = full buying, close at the low = full selling). Signed volume and volume are smoothed, and **pulse = 100 × signed / total**, so it always runs from -100 to +100. The gold line is its signal line (EMA 9).

### 2. Entry (defaults)

> 1. The pulse crosses the zero line.
> 2. After the **2nd closed pulse bar**: pulse direction = SMA 200 bias.
> 3. The pulse is beyond its signal line.
> 4. *(Optional)* the higher timeframe agrees.
>
> Entry at the close of that bar, one entry per pulse leg.

- **Signal line condition** (input): pulse beyond its signal line, or additionally the signal line pointing the same way / the signal line beyond zero.
- **Higher-timeframe filter** (ON / OFF): HTF pulse beyond its signal line, HTF signal line beyond zero, or HTF pulse beyond zero.
- **Optional extras** (all OFF by default): score, volume, anti-chop and EMA stack filters.
- The v1.00 **EMA-slope bias** is still available as an alternative to SMA 200.

### 3. Stop / target / management

- **Stop** behind the swing of the last N bars + ATR buffer (min / max in ATR — a stop that would be too wide = no trade).
- **Target** 1:2 (input).
- **Optional:** break-even, partial close, ATR or EMA trailing, exit on the opposite signal.

### 4. Risk

Risk % per trade (or fixed lots), max lots, max spread, max trades per day, daily loss limit (optionally closes the EA trades), session hours, Friday stop, long / short only. No order traffic during the broker's daily break (gold 00:00–01:05).

## 🖥️ Dashboard & chart

- **Volume Pulse histogram** (64 bars) + signal line, SMA 200 bias as background, signal markers.
- **Signal engine** — every condition as a traffic light (bias, signal line, higher TF, optional extras) + quality score.
- **Signal track record** — all signals of the rules on your chart history, replayed bar by bar (stop or target, stop first if one bar hits both, NO costs). A quick honest check of the rules, not a full simulation.
- **Trade control** — auto trading ON / signals only, close EA trades (2 clicks), open trade with progress in R, daily guard, live statistics of the EA (magic number).
- **X** folds the panel to a pill, drag the header to move it; it avoids other trader.lifestyle panels on the same chart.
- **Chart** — SMA 200, signal arrows, R result tags, live SL / TP lines.

## 🆕 What's new in v1.10

Rules updated after user feedback:
- Trend bias / histogram background = **SMA 200** (the v1.00 EMA-slope bias is still available).
- Entry only after the **second closed pulse bar** of a zero cross, and only when the pulse direction matches the SMA 200 bias.
- The pulse **signal line (EMA 9)** is part of the entry.
- Optional **higher-timeframe filter**.
- Score / volume / anti-chop / EMA stack filters are now optional extras (all OFF by default).
- No order traffic during the broker's daily break.

## 🛠️ Installation

1. **MT5:** copy `TL Volume Pulse Pro.ex5` to `File → Open Data Folder → MQL5 → Experts`.
   **MT4:** copy `TL Volume Pulse Pro.ex4` to `File → Open Data Folder → MQL4 → Experts`.
2. Refresh the Navigator and drag the EA onto a chart.
3. Allow **Algo Trading**.
4. **Allow DLL imports** is only needed for the link buttons in the panel.

## ⚠️ Notes

- Independently written by trader.lifestyle — not a copy, port or decompile of anybody's indicator or product.
- No performance promises. The track record in the panel shows how the rules behaved on YOUR chart, without trading costs.
- Trading is risky — test on a demo account first.

## 🖼️ More screenshots

<img src="screenshots/TL_VolumePulsePro_FF.png" width="49%">
<img src="screenshots/TL_VolumePulsePro_v110_FF.png" width="49%">

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
