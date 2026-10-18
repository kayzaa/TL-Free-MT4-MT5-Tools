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

## Overview

MT5 port of "Precision Market Entropy Heatmap" (c) LuxAlgo, including the tweak shown in the LuxAlgo short "This NEW Volume Profile Indicator Is Actually Accurate": previous-day POCs are drawn as ZONES with a day counter, the POC-row volume and the buy/sell dominance.

License: the original script is CC BY-NC-SA 4.0 (<https://creativecommons.org/licenses/by-nc-sa/4.0/).> This port is free, non-commercial and shared with source code under the same license. No lock, no expiry.

## What You See

- Heatmap: one block per session (Anchor Interval, default D1). The session range is split into 50 rows; every intrabar (default M1) spreads its volume evenly over the rows it touched. Colour = row volume / peak row volume: dark navy (low) -> green (mid) -> yellow (high).
- POC zone: the row with the most volume of each session, extended to the current bar, with a dotted centre line. Green = POC below price (support), red = POC above price (resistance). The colour flips live when price crosses the zone middle.
- Labels: "N Days | Vol: 36.26K (52% B)" N Days   = calendar days since that session started Vol      = volume inside that session's POC row (not accumulated over days) 52% B/S  = share of that volume from bullish (B) or bearish (S) intrabars, dominant side "Current Profile | ..." is the running session.
- White line: developing POC of every session.

## How To Trade It (as in the video)

- Wait for price to reach a previous POC zone; several POCs lining up = stronger level.
- Enter only on a clear reaction: rejection candle or 3-bar reversal. Do not buy/sell blindly.
- Typical target: the current profile's POC.

## Inputs (all in English, tooltips can be switched off)

Heatmap Settings : Anchor Interval, Intrabar Precision, Number of Rows (10-100), Volume Source Style Settings   : 3 heatmap colours, Heatmap Transparency (80 = gold scenes of the video, 70 = original default), POC bull/bear colours, zone fill/border transparency (80/30 as in the tweaked script), Developing POC (+Auto colour) Display Settings : Max Sessions (the original caps sessions x rows at 500 boxes), Extend POCs to Current Bar, show zones / labels, label font/size/offset Chart & Extras   : Apply video chart theme (dark #0A0A0A, no grid, white/grey candles, restored when the indicator is removed), Tooltips on/off, link buttons, Forex Factory thread link

## Notes

- MT5 uses tick volume by default (spot FX/gold has no central volume), so the numbers differ from TradingView/OANDA; the distribution and the POCs are what matters.
- Chart timeframe must be lower than the Anchor Interval (e.g. M1-H1 for D1).
- Hover over a zone or a heatmap row to get a detailed tooltip.
- The buttons (YouTube / RoboForex / WhatsApp / Myfxbook) open links via shell32.dll, so "Allow DLL imports" must be enabled. Everything else works without it.

## Install

- Copy "TL Entropy Heatmap Pro.ex5" to  File > Open Data Folder > MQL5 > Indicators, refresh the Navigator and drag it onto a chart.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
