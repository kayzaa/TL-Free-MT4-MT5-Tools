<div align="center">

# ⚡ TL MTF Six MA Pro

**Six moving averages across multiple timeframes — trend alignment at a glance.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Indicator-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_MTFSixMAPro_FF.png" alt="TL MTF Six MA Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL MTF Six MA Pro.ex4`](MT4/TL%20MTF%20Six%20MA%20Pro.ex4) |
| **MT5** | [`TL MTF Six MA Pro.ex5`](MT5/TL%20MTF%20Six%20MA%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- 📏 **Up to 6 moving averages** — each with its own period, shift, method, applied price, colour and style.
- ⏱️ **Up to 9 timeframes on one chart** — every MA from M1 to MN1.
- 🧮 **Trend matrix** — green up / red down per timeframe and MA, plus a bias per timeframe and over all timeframes.
- 🏷️ **Clean price labels** — e.g. "H4 50 EMA" right of the last candle; overlapping labels are spread apart.
- 🧲 **A panel that never gets stuck** — closes, folds, moves, and removes everything it drew when you remove it.
- 🧹 **Cleans up the old one** — automatically removes stuck panels of the old FXTT_MTF_6MA.

## 🧠 How it works

A rebuild of **FXTT_MTF_6MA** with the same calculation as the original and a brand-new panel.

- **Moving averages** — up to 6 MAs (period `0` = MA off). Defaults match the original: **10 SMA, 20 SMA, 50 EMA, 31 EMA, MA5 off, 240 LWMA (open)**.
- **Timeframes** — each MA can be shown from up to 9 timeframes (M1 … MN1). Only timeframes equal to or higher than the chart timeframe can be shown (like the original).
- **Labels** — price labels right of the last candle, e.g. "H4 50 EMA". Labels that would overlap are spread apart.
- **Trend matrix** — for every timeframe: green up = price above that MA, red down = price below, plus a bias per timeframe and over all timeframes.

## 🖥️ Dashboard & chart

- **Timeframe buttons** M1 … MN1, plus **ALL / NONE / CHART** (only the chart timeframe) and **LABELS** on/off.
- **MA buttons** — show / hide each MA on every timeframe.
- **Matrix rows** — click a row to show / hide that timeframe.
- **X** folds the panel to a small pill (the lines stay); click the pill to open it again.
- Drag the header (or the pill) to move it. Position and buttons survive timeframe changes; the buttons are remembered per symbol.
- Removing the indicator removes everything it drew — nothing stays behind.

## ⚙️ Key inputs

| Input | What it does |
|---|---|
| Per MA: period / shift / method / applied price / colour / style | Defines each of the 6 MAs (period `0` = off) |
| Remove stuck panels of the old FXTT_MTF_6MA | Cleans up a stuck panel left by the old indicator |

## 🔌 EA buffers (iCustom)

`buffer = timeframe index × 6 + MA index` (both counted from 0)

| Timeframe index | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 |
|---|---|---|---|---|---|---|---|---|---|
| **Timeframe** | M1 | M5 | M15 | M30 | H1 | H4 | D1 | W1 | MN1 |

Example: H4 MA 3 = 5 × 6 + 2 = **buffer 32**. `EMPTY_VALUE` = not available.

## 🛠️ Installation

1. Remove the old FXTT_MTF_6MA from the chart first.
2. **MT4:** copy `MT4/TL MTF Six MA Pro.ex4` to `File → Open Data Folder → MQL4 → Indicators`.
   **MT5:** copy `MT5/TL MTF Six MA Pro.ex5` to `File → Open Data Folder → MQL5 → Indicators`.
3. In the Navigator: right-click → **Refresh**, then drag the indicator onto the chart.
4. **Allow DLL imports** is only needed for the link buttons (they open the browser).

## ⚠️ Notes

- Free — no lock, no expiry. Educational tool, no investment advice.

## 🙏 Credits

- Original indicator: **FXTT_MTF_6MA**. Rebuilt on a Forex Factory request by **Mahapathy** (post 15951546).

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
