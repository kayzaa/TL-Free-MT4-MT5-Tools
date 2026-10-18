<!-- auto-generated: remove this line after hand-editing so publish keeps your text -->
<div align="center">

# ⚡ TL Curve Profile Pro

**MetaTrader adaptation of Zeiierman's Curved Trendlines — smooth curved support and resistance.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Indicator-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Curve_Profile_Pro_MT5.png" alt="TL Curve Profile Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Curve Profile Pro.ex4`](MT4/TL%20Curve%20Profile%20Pro.ex4) |
| **MT5** | [`TL Curve Profile Pro.ex5`](MT5/TL%20Curve%20Profile%20Pro.ex5) |

> Compiled build only — source code is not published.

## Overview

An independent MetaTrader adaptation of Curved Trendlines (Zeiierman). Original author: Zeiierman. MT adaptation and interface: trader.lifestyle. Source: <https://www.tradingview.com/script/d1yc5hBu-Curved-Trendlines-Zeiierman/> Video: <https://www.youtube.com/watch?v=G0tvIPw3eHs> (Soheil PKO, 5:43). License: Creative Commons Attribution-NonCommercial-ShareAlike 4.0. Free, no account lock, no expiry. Noncommercial use; retain attribution and the same license when sharing adaptations. This is not an official Zeiierman release.

## Installation

- MT5: File > Open Data Folder > MQL5 > Indicators. Copy the EX5 from MT5.
- MT4: File > Open Data Folder > MQL4 > Indicators. Copy the EX4 from MT4_COMPILE_ONLY. Its runtime remains unverified in this environment.
- Refresh Navigator, then attach TL Curve Profile Pro to a chart.
- AutoTrading and DLL imports are not required. No orders are sent.
- Load enough broker history; at least three confirmed pivots per side are needed.
- Do not restart a running terminal just to install. Refresh Navigator instead.

## How It Works

Each side independently fits a quadratic to recent confirmed swing points. The upper fit is shifted by the maximum residual; the lower by the minimum. Projection stops before the upper curve crosses the lower. Midline is their average. R-squared describes fit to the selected pivots, not prediction accuracy. The live profile spans the current pivot structure. Older candles contribute to separate upper/lower memory profiles only outside that live price range and inside the projected envelope. Each nonempty profile has its own POC. Volume is distributed across rows by candle-range overlap. Buy/sell shares are estimated from close position inside each candle. This is not measured bid/ask delta, exchange order flow, or actual buyer/seller identification.

## Features And Inputs

Structure: InpPivotLength=10 (left AND right confirmation), InpStructurePoints=6 (3..15), InpExtend=20 (0..300). Upper/lower curves: independent visibility and colors; InpCurveWidth=2. Midline: InpMid=true, separate color and width. Fill: InpFill=true, InpLayers=20, outer transparency65, center97; upper/lower colors also set their halves of the gradient. History: InpHistory=false; enable to retain the strongest qualifying pair per completed window. InpHistKeep=10, InpHistWindow=80, InpHistMinFit=50 percent. History color and width are adjustable. This is a bounded reconstruction, not an immutable record of every previously displayed channel. Live profile: InpProfile=true, InpRows=48, InpProfileWidth=60 bars, InpProfileGap=5 bars, configurable buy/sell colors. Live POC: InpPOC=true, configurable gold color. Profile range boundaries: InpBounds=false; optional dotted lines. Memory: InpMemory=true, InpMemoryWidth=50 bars, separate buy/sell colors, InpMemoryPOC=true, configurable blue POC color. Empty regions have no POC. Shared row size can increase to stay within the drawing/bin budget. InpScanBars=5000 (100..20000) bounds pivot/history processing; profile data is limited to 5000 bars. Excessively old structures disable their profiles. InpVolume=V_TICK by default. V_REAL uses broker real_volume only, with no silent fallback. Forex feeds often supply no real volume; profiles then empty.

## Our Additions

Dark/Cyan/Gold Canvas interface, animated logo, responsive panel columns, drag header, X-to-pill, click pill to reopen, contextual hover information. Live boundary/POC values, fit score, pivot delay, volume mode and model status. CHART LAYER ON/OFF toggles drawings; REFRESH forces recalculation. InpShowPanel and InpShowTooltips control panel/hover visibility. InpPanelX/Y set its initial location. A saved chart position can take priority. InpInstance must differ for additional copies on the same chart. Shared chart theme/scale settings can conflict between copies; one themed copy is preferred. InpTheme=true styles the chart and heals changes; original settings are restored on removal. Disable it to keep your own colors. InpAutoScale=true includes visible projected curves in the price scale. InpFitProfileOnScreen=true compresses profile width/gap to available space. Disable those options for native scaling and literal bar widths. Link buttons display URLs in a dialog and Experts log. Open them in your browser manually; the indicator does not need ShellExecute or DLL access.

## Timing, Refitting And Alerts

InpClosedBars=true is the default addition: calculations use completed candles. False includes the developing candle, closer to the original live behavior, with an update throttle. Confirmed pivots still arrive after the right-hand confirmation delay. Curves are REFITTED when new pivots arrive; old chart segments can move. Closed-bar mode does NOT make this a non-repainting system. InpPopupAlerts/InpPushAlerts default false. In closed-bar mode they notify on an upward upper-curve cross, downward lower-curve cross, or either live-POC cross, using the prior model projected into the just-closed bar. At most one message per bar; boundary events take priority. They are optional additions, not entry signals from the video. Push needs terminal Notifications configured; external push delivery has not been verified. Initial attachment is silent.

## Trading Interpretation

Rising/falling curvature describes structure. POCs highlight high estimated volume concentrations. These are contextual levels, not trade instructions. The video/source supplies no complete mechanical BUY/SELL, stop-loss, take-profit, position-size or exit rules. This indicator deliberately does not invent them or place trades. Future curves are mathematical extrapolation.

## Integration Buffers (0-based)

0 upper, 1 lower, 2 midpoint, 3 live POC, 4 upper memory POC, 5 lower memory POC. Index0 holds the most recent calculated snapshot. In closed-bar mode it refers to the last completed candle. Previously observed snapshots shift as new bars arrive; historical data is NOT backfilled at attachment. EMPTY_VALUE means unavailable. These are not a complete historical signal/backtest buffer.

## Validation Status

Both platform builds compile with 0 errors / 0 warnings. MT5: native core/tester run, independent numeric comparison, real-chart UI checks and actual release EX5 loading/buffers tested. See separate verification. MT4: compiled successfully, but isolated terminal stalled after loading the test harness. Runtime, appearance and interactions are NOT verified on MT4. Broker history, tick volume, sessions and missing bars differ from TradingView; identical settings do not guarantee identical curves or POCs between feeds. No trading-performance or profitability claim is made.

## Links

YouTube: <https://www.youtube.com/@traderlifestyle> WhatsApp: <https://wa.me/18585003724> Forex Factory: <https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4> RoboForex: <https://my.roboforex.com/en/?a=jjlu> (referral link) CREATED WITH INDICATORGENIUS.COM — <https://indicatorgenius.com/> Trading involves risk. Test behavior on a demo chart before relying on it.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
