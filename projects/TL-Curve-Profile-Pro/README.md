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

## ✨ Highlights

- 📈 **Curved support & resistance** — each side fits a quadratic curve to recent confirmed swing points, with a midline in between.
- 📊 **Built-in volume profiles** — a live profile across the current structure plus separate upper/lower memory profiles, each with its own POC.
- 🌈 **Gradient channel fill** — layered fill between the curves, with optional history of the strongest past channels.
- 🖥️ **Dark/Cyan/Gold canvas panel** — live boundary/POC values, fit score, pivot delay, volume mode and model status.
- 🔔 **Optional alerts** — curve breaks and live-POC crosses, at most one message per bar.
- 🔌 **EA-ready buffers** — upper, lower, midpoint and three POC values.

## 🧠 How it works

- **Curves** — each side independently fits a quadratic to recent confirmed swing points. The upper fit is shifted by the maximum residual, the lower by the minimum. Projection stops before the upper curve crosses the lower. The midline is their average.
- **Fit score** — R-squared describes the fit to the selected pivots, not prediction accuracy.
- **Live profile** — spans the current pivot structure. Volume is distributed across rows by candle-range overlap.
- **Memory profiles** — older candles contribute to separate upper/lower memory profiles, only outside the live price range and inside the projected envelope. Each non-empty profile has its own POC; empty regions have no POC.
- **Buy/sell shares** — estimated from the close position inside each candle. This is *not* measured bid/ask delta, exchange order flow or actual buyer/seller identification.
- **Timing** — `InpClosedBars=true` (default) calculates on completed candles. `false` includes the developing candle, closer to the original live behaviour, with an update throttle.

> **Trading interpretation:** rising/falling curvature describes structure, and POCs highlight high estimated volume concentrations. These are contextual levels, not trade instructions. The source/video supplies no complete mechanical BUY/SELL, stop-loss, take-profit, position-size or exit rules — this indicator deliberately does not invent them and places no trades. Future curves are mathematical extrapolation.

## 🖥️ Dashboard & chart

- Dark/Cyan/Gold canvas interface with animated logo and responsive panel columns.
- Drag the header, **X** shrinks it to a pill, click the pill to reopen. Contextual hover information everywhere.
- **CHART LAYER ON/OFF** toggles the drawings; **REFRESH** forces recalculation.
- `InpTheme=true` styles the chart and heals changes; your original settings are restored on removal. Disable it to keep your own colours.
- `InpAutoScale=true` includes visible projected curves in the price scale; `InpFitProfileOnScreen=true` compresses profile width/gap to the available space. Disable them for native scaling and literal bar widths.
- Link buttons display the URL in a dialog and the Experts log — open them in your browser manually. No ShellExecute or DLL access needed.

## ⚙️ Key inputs

| Input | What it does |
|---|---|
| `InpPivotLength=10` | Left AND right confirmation bars for pivots |
| `InpStructurePoints=6` (3..15) | Pivots used per fit |
| `InpExtend=20` (0..300) | Projection length |
| `InpCurveWidth=2`, colours, visibility | Upper/lower curve style (independent per side) |
| `InpMid=true` | Midline, with its own colour and width |
| `InpFill=true`, `InpLayers=20` | Gradient fill (outer transparency 65, centre 97) |
| `InpHistory=false` | Keeps the strongest qualifying pair per completed window (`InpHistKeep=10`, `InpHistWindow=80`, `InpHistMinFit=50` percent) |
| `InpProfile=true`, `InpRows=48` | Live profile; `InpProfileWidth=60` bars, `InpProfileGap=5` bars, buy/sell colours |
| `InpPOC=true` | Live POC (gold) |
| `InpBounds=false` | Optional dotted profile range boundaries |
| `InpMemory=true`, `InpMemoryWidth=50` | Memory profiles with buy/sell colours; `InpMemoryPOC=true` (blue) |
| `InpScanBars=5000` (100..20000) | Bounds pivot/history processing; profile data is limited to 5000 bars |
| `InpVolume=V_TICK` | `V_REAL` uses broker real volume only, with no silent fallback |
| `InpClosedBars=true` | Completed candles only (see Notes) |
| `InpPopupAlerts` / `InpPushAlerts` | Both `false` by default |
| `InpShowPanel`, `InpShowTooltips`, `InpPanelX/Y` | Panel and hover visibility, initial position (a saved chart position can take priority) |
| `InpInstance` | Must differ for additional copies on the same chart |
| `InpTheme`, `InpAutoScale`, `InpFitProfileOnScreen` | Chart styling and scaling helpers |

## 🔔 Alerts

In closed-bar mode the optional popup/push alerts fire on an upward upper-curve cross, a downward lower-curve cross, or either live-POC cross, using the prior model projected into the just-closed bar. At most one message per bar; boundary events take priority. Initial attachment is silent. These are optional additions, not entry signals from the video. Push needs terminal Notifications configured.

## 🔌 Integration buffers (0-based)

| Buffer | Value |
|---|---|
| 0 | Upper curve |
| 1 | Lower curve |
| 2 | Midpoint |
| 3 | Live POC |
| 4 | Upper memory POC |
| 5 | Lower memory POC |

Index 0 holds the most recent calculated snapshot (in closed-bar mode: the last completed candle). Previously observed snapshots shift as new bars arrive; history is **not** backfilled at attachment. `EMPTY_VALUE` = unavailable. These buffers are not a complete historical signal record.

## 🛠️ Installation

1. **MT5:** copy the `.ex5` from the `MT5` folder to `File → Open Data Folder → MQL5 → Indicators`.
   **MT4:** copy the `.ex4` from the `MT4` folder to `File → Open Data Folder → MQL4 → Indicators`.
2. Refresh the Navigator (no need to restart a running terminal), then attach **TL Curve Profile Pro** to a chart.
3. AutoTrading and DLL imports are **not** required — no orders are sent.
4. Load enough broker history: at least three confirmed pivots per side are needed.

## ⚠️ Notes

- **MT4 build is compile-only** — its runtime, appearance and interactions are not verified. The MT5 build is the verified one.
- **Curves refit.** When new pivots arrive the curves are refitted and old chart segments can move. Closed-bar mode does NOT make this a non-repainting system; confirmed pivots also arrive only after the right-hand confirmation delay.
- **Volume data:** forex feeds often supply no real volume — with `V_REAL` the profiles are then empty. Shared row size can grow to stay within the drawing budget, and very old structures disable their profiles.
- **Multiple copies:** shared chart theme/scale settings can conflict; one themed copy is preferred.
- Broker history, tick volume, sessions and missing bars differ from TradingView — identical settings do not guarantee identical curves or POCs between feeds.
- No trading-performance or profitability claim is made. Test behaviour on a demo chart before relying on it.

## 🙏 Credits

- Original indicator: [Curved Trendlines by Zeiierman](https://www.tradingview.com/script/d1yc5hBu-Curved-Trendlines-Zeiierman/) (TradingView).
- Video: [Curved Trendlines walkthrough by Soheil PKO](https://www.youtube.com/watch?v=G0tvIPw3eHs) (5:43).
- MetaTrader adaptation and interface: trader.lifestyle. This is an independent adaptation, not an official Zeiierman release.
- License: **Creative Commons Attribution-NonCommercial-ShareAlike 4.0** — noncommercial use; retain attribution and the same license when sharing adaptations. Free, no account lock, no expiry.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
