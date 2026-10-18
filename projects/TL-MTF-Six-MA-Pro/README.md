<!-- auto-generated: remove this line after hand-editing so publish keeps your text -->
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

## Overview

Rebuild of FXTT_MTF_6MA (Forex Factory request by Mahapathy, post 15951546). Same calculation as the original - checked value by value against it - but a new panel that closes, folds, moves and never gets stuck on the chart.

What it does
- Up to 6 moving averages (period / shift / method / applied price / colour / style per MA, period 0 = MA off). Defaults = the original: 10 SMA, 20 SMA, 50 EMA, 31 EMA, MA5 off, 240 LWMA (open).
- Each MA from up to 9 timeframes (M1 ... MN1) on one chart. Only timeframes equal to or higher than the chart timeframe can be shown (like the original).
- Price labels right of the last candle, e.g. "H4 50 EMA". Labels that would overlap are spread apart.
- Trend matrix: for every timeframe, green up = price above that MA, red down = price below, plus a bias per timeframe and over all timeframes.

Panel
- Timeframe buttons M1 ... MN1, ALL / NONE / CHART (only the chart timeframe) / LABELS on-off
- MA buttons: show / hide each MA on every timeframe
- Click a row of the matrix to show / hide that timeframe
- X folds the panel to a small pill (the lines stay), click the pill to open it again
- Drag the header (or the pill) to move it. Position and buttons survive timeframe changes, the buttons are remembered per symbol.
- Removing the indicator removes everything it drew - nothing stays behind.
- Old FXTT_MTF_6MA panel stuck on your chart? Attach this indicator once: it removes the stuck panel of the old one automatically (input "Remove stuck panels of the old FXTT_MTF_6MA").

Install MT4: copy MT4/TL MTF Six MA Pro.ex4 into MQL4\Indicators MT5: copy MT5/TL MTF Six MA Pro.ex5 into MQL5\Indicators Navigator -> right-click -> Refresh, drag the indicator onto the chart. Remove the old FXTT_MTF_6MA from the chart first. "Allow DLL imports" is only needed for the link buttons (they open the browser).

EA buffers (iCustom) buffer = timeframe index x 6 + MA index (both from 0) timeframe index: 0 M1, 1 M5, 2 M15, 3 M30, 4 H1, 5 H4, 6 D1, 7 W1, 8 MN1 example: H4 MA 3 = 5 x 6 + 2 = buffer 32. EMPTY_VALUE = not available.

Free - no lock, no expiry. Educational tool, no investment advice.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
