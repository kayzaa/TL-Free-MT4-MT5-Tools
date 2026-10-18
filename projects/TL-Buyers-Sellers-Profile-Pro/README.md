<!-- auto-generated: remove this line after hand-editing so publish keeps your text -->
<div align="center">

# ⚡ TL Buyers Sellers Profile Pro

**Buyers / sellers volume profile, dynamic support & resistance and volume delta — all-in-one, 1:1 look of the original.**

![version](https://img.shields.io/badge/version-v1.01-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Indicator-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_BuyersSellersProfilePro_v1.01.png" alt="TL Buyers Sellers Profile Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Buyers Sellers Profile Pro.ex4`](MT4/TL%20Buyers%20Sellers%20Profile%20Pro.ex4) |
| **MT5** | [`TL Buyers Sellers Profile Pro.ex5`](MT5/TL%20Buyers%20Sellers%20Profile%20Pro.ex5) |

> Compiled build only — source code is not published.

## Overview

What it shows
- Large rolling volume profile (default 600 bars, 72 rows) on the right side of the chart. Every row is split into estimated BUYING volume (green, left) and SELLING volume (blue, right). Low-volume rows fade into the background, the POC (highest volume row) is framed orange.
- Dynamic support / resistance: swing pivots are only accepted when the volume profile backs them (node strength, local peak, buyer / seller bias, distance, absorption around the pivot). Red = resistance, green = support. Higher score = thicker line, bigger circle, glow from 80. Profile rows that hold an active level are framed in the level colour.
- POC confluence zones: an active level close to the POC is shaded - a key turning / target zone.
- Volume delta columns at the bottom of the chart: grey = total, cyan = buying, red = selling (dominant side behind, smaller in front), diamond = dominant side.
- Optional (inputs): candles coloured by dominant volume, EMA 12/26 band (volume-weighted), crossover arrows confirmed by the buy / sell volume of the last 6 bars.
- Dashboard: POC, buyers vs sellers, nearest levels, confluence, current candle buy / sell / net.

Install MT5: copy the .ex5 to  MQL5\Indicators   |   MT4: copy the .ex4 to  MQL4\Indicators Refresh the Navigator, drag the indicator onto a chart. Enable "Allow DLL imports" only if you want the link buttons to open in the browser (the indicator works without it).

Notes
- Buy / sell volume is ESTIMATED from candle data: buy = volume x (close - low) / (high - low). It is not real bid / ask order flow. Tick volume is used (MT5: real volume optional).
- Levels are calculated on closed bars only.
- The dark chart theme and chart shift are restored when you remove the indicator.
- EA buffers: 16 = bullish cross, 17 = bearish cross, 19 = nearest resistance, 20 = nearest support, 21 = strongest level score.

Educational tool - no investment advice.

v1.01 (08.10.2026): MT4 fix - the indicator stopped right after switching the chart to the dark theme (MT4 passes an empty real-volume array -> "array out of range"). Profile, levels, volume panel and dashboard work on MT4 again.

## 🖼️ More screenshots

<img src="screenshots/TL_BuyersSellersProfilePro_screenshot.png" width="49%">

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
