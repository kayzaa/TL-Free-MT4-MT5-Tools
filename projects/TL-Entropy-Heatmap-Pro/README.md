<div align="center">

# ⚡ TL Entropy Heatmap Pro

**Entropy heatmap with POC zones and labels — a faithful port of the LuxAlgo-style heatmap.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Indicator-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Entropy_Heatmap_Pro_v_M5_s1.png" alt="TL Entropy Heatmap Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT5** | [`TL Entropy Heatmap Pro.ex5`](MT5/TL%20Entropy%20Heatmap%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **MT5 port of LuxAlgo's "Precision Market Entropy Heatmap"** — session-by-session volume heatmap from intrabar data.
- **Includes the tweak from LuxAlgo's short** *"This NEW Volume Profile Indicator Is Actually Accurate"*: previous-day POCs drawn as **zones**.
- **Live support / resistance colouring** — POC zones turn green below price and red above, flipping as price crosses.
- **Information-rich labels** — day counter, POC-row volume and buy / sell dominance.
- **Developing POC line** for every session, plus detailed hover tooltips.
- **Optional video chart theme** — dark background, no grid, restored when you remove the indicator.

## 🧠 How it works

| Element | What it shows |
|---|---|
| **Heatmap** | One block per session (Anchor Interval, default D1). The session range is split into 50 rows; every intrabar (default M1) spreads its volume evenly over the rows it touched. Colour = row volume / peak row volume: dark navy (low) → green (mid) → yellow (high). |
| **POC zone** | The row with the most volume in each session, extended to the current bar, with a dotted centre line. Green = POC below price (support), red = POC above price (resistance). The colour flips live when price crosses the zone middle. |
| **Labels** | `N Days \| Vol: 36.26K (52% B)` — see below. The running session is labelled `Current Profile \| ...`. |
| **White line** | Developing POC of every session. |

**Label anatomy:**

- **N Days** — calendar days since that session started.
- **Vol** — volume inside that session's POC row (not accumulated over days).
- **52% B / S** — share of that volume from bullish (B) or bearish (S) intrabars, showing the dominant side.

## 🎯 How to trade it (as in the video)

> 1. Wait for price to reach a previous POC zone — several POCs lining up = a stronger level.
> 2. Enter only on a clear reaction: a rejection candle or a 3-bar reversal. Do not buy / sell blindly.
> 3. Typical target: the current profile's POC.

The indicator draws the levels; it does not place trades.

## ⚙️ Key inputs

All inputs are in English, with tooltips that can be switched off.

| Group | Inputs |
|---|---|
| **Heatmap Settings** | Anchor Interval, Intrabar Precision, Number of Rows (10–100), Volume Source |
| **Style Settings** | 3 heatmap colours; Heatmap Transparency (80 = gold scenes of the video, 70 = original default); POC bull / bear colours; zone fill / border transparency (80 / 30 as in the tweaked script); Developing POC (+ auto colour) |
| **Display Settings** | Max Sessions (the original caps sessions × rows at 500 boxes), Extend POCs to Current Bar, show zones / labels, label font / size / offset |
| **Chart & Extras** | Apply video chart theme (dark #0A0A0A, no grid, white / grey candles, restored on removal), tooltips on / off, link buttons, Forex Factory thread link |

## 📋 Requirements

- The chart timeframe must be **lower** than the Anchor Interval (e.g. M1–H1 for D1).
- The link buttons (YouTube / RoboForex / WhatsApp / Myfxbook) open links via shell32.dll, so they need **"Allow DLL imports"**. Everything else works without it.

## 🛠️ Installation

1. Copy `TL Entropy Heatmap Pro.ex5` to `File → Open Data Folder → MQL5 → Indicators`.
2. Refresh the Navigator.
3. Drag the indicator onto a chart with a timeframe below the Anchor Interval.

## ⚠️ Notes

- MT5 uses tick volume by default (spot FX / gold has no central volume), so the numbers differ from TradingView / OANDA — the distribution and the POCs are what matters.
- Hover over a zone or a heatmap row for a detailed tooltip.

## 🙏 Credits

- Original script: **"Precision Market Entropy Heatmap"** © LuxAlgo, plus the POC-zone tweak shown in LuxAlgo's short *"This NEW Volume Profile Indicator Is Actually Accurate"*.
- License: the original is [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/). This port is free and non-commercial under the same license. No lock, no expiry.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
