<div align="center">

# ⚡ TL Delta Profile 3D Pro

**3D delta volume profile with buy / sell pressure per price level and a modern depth effect.**

![version](https://img.shields.io/badge/version-v1.12-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Indicator-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Delta_Profile_3D_Pro_MT5.png" alt="TL Delta Profile 3D Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Delta Profile 3D Pro.ex4`](MT4/TL%20Delta%20Profile%203D%20Pro.ex4) |
| **MT5** | [`TL Delta Profile 3D Pro.ex5`](MT5/TL%20Delta%20Profile%203D%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **LuxAlgo's Order Flow 3D Delta Profile, native on MT4 / MT5** — with a trader.lifestyle dark / cyan / gold canvas dashboard and a 3D chart layer.
- **POC, value area and delta colouring** — profile width = total volume, colour and alignment = delta direction.
- **High-volume glow and first-retest beams** — anomaly candles light up, and a ribbon runs until price first touches that level again.
- **POC break & retest signals** — BUY / SELL pills from explicit closed-candle rules, with an optional RSI-divergence filter. No orders are placed.
- **Polished visuals** — downward-projecting 3D depth face, adjustable glow, purple POC zone, collision-aware labels.
- **Optional alerts and a data interface** — popup / push context alerts (off by default) and six buffers for other tools.

## 🧠 How it works

### The profile

- **Up candles** add their entire selected volume to bullish volume, **down candles** to bearish volume; **dojis** are excluded from the profile.
- Each candle is assigned to **one price bin at HL2** — not distributed over its range.
- **Delta** = bullish minus bearish candle volume. This is a proxy, not measured bid/ask aggressor flow or a footprint.
- Profile **width** is total volume (as in the original). Colour and centre-alignment direction reflect delta. An optional **ABSOLUTE_DELTA** width is an extra mode; POC and value area always use total volume.
- **POC** is the largest-volume bin (equal maxima choose the lowest price bin); it is drawn at the bin midpoint.
- **Value area** expands contiguously from the POC toward the larger neighbouring volume, with upper-bin priority on ties. Whole-bin coverage may exceed the requested percentage. VA boundaries use the outer bin edges.

### High-volume anomalies

A candle is an anomaly when its volume is strictly greater than the window average × the threshold (the average includes dojis). The glow spans the candle's high to low. The beam starts at HL2 and ends at the first later candle touching that price; without a touch, it reaches the profile start. Bands are conditional — a quick next-bar retest creates only a short band, so long horizontal bands will not appear on every market.

### Rolling window

The default developing window includes the current candle; `ClosedBars=true` excludes it. Both are rolling profiles: bins, POC, value area and older anomaly classifications can change as the window moves. This is not a fixed historical signal indicator.

## 🎯 Strategy signals (v1.12)

The [video](https://www.youtube.com/watch?v=5ZKai50qErM) explains discretionary POC role reversal, RSI divergence and a short stop above the zone (04:05–06:56). This version turns those examples into explicit, adjustable closed-candle rules. The confirmation details are our own implementation — the video does not specify a complete automated strategy. **No orders are placed.**

| Rule | Condition |
|---|---|
| **BUY break** | The POC bucket is calculated from the Length candles *before* the tested candle. Previous close at/below the bucket high, tested closed candle closes above it. No current/future candle is used in that reference profile. |
| **SELL break** | Mirror image at the bucket low. |
| **Retest** | A breakout arms and freezes that exact bucket. Within RetestBars, a *later* candle intersects the frozen zone and closes back above its upper edge with a bullish body (BUY), or below its lower edge with a bearish body (SELL). A close through the opposite edge invalidates the setup; a new breakout replaces the armed reference. Each retest consumes its setup. |
| **Mode** | Breakout-and-Retest, Breakout-only or Retest-only. |
| **Stop** | BUY below the frozen bucket low, SELL above its high; padding = max(one symbol point, bucket width × StopPadding). |

**RSI divergence:** Wilder-smoothed RSI on closes, computed internally (no separate oscillator pane). A price pivot needs PivotBars bars on both sides (equality allowed only on the older side — the rightmost equal extreme wins) and becomes usable only once the right-hand bars have closed. Bullish divergence = two successive confirmed price lows forming a lower low while RSI forms a higher low; bearish mirrors this at highs. Divergence expires DivergenceLife bars after confirmation. Pills tagged **+ RSI** have a valid matching divergence; set `InpRequireDivergence=true` for the stricter RSI-confirmed variant.

**Pills:** BUY / SELL, POC BREAK / POC RETEST and optional + RSI — timestamped on the confirmation candle, never moved back to an earlier pivot. For a realistic forward-testing assumption use the next candle's open, plus spread / slippage; the displayed close is not a guaranteed fill.

**Stop line:** the chart shows the latest setup's original stop, labelled **LAST SETUP SL**. It is a reference, not a live-position tracker, and stays displayed after price passes it. No trailing, exit, target, position sizing or take profit is added — the video specifies no fixed take-profit rule.

**Signal defaults:** strategy on; both Breakout and Retest; mandatory RSI-divergence filter off (divergence is still calculated and tagged); RSI 14, pivot wings 3, divergence lifetime 60 bars, retest lifetime 20 bars, minimum signal spacing 5 bars, historical signal window 800 bars plus warm-up, stop padding 15 % of the POC bucket width, latest setup stop shown.

## 🖥️ Dashboard & chart

- **Dashboard:** live volume balance, coverage, anomaly and engine information; hover explanations; **PROFILE ON/OFF** and **REFRESH** buttons; draggable header — **X** collapses it to a draggable pill, click the pill to restore. Panel state persists. A compact mode hides the extra volume / anomaly blocks on shorter charts (calculations continue), and small charts may rearrange the columns.
- **Chart extras:** POC / VA price labels, optional POC-bin zone, whole-chart theme (restored on removal), auto screen fitting. Deleted layer / panel objects are rebuilt.
- **3D depth face** projects **down** only; DepthY controls its size (both signs project downward).
- **Glow intensity** 0–100 (default 70) controls halos around profile bars and volume beams.
- **POC zone:** purple rectangular rim, muted light grey / lilac core and soft halo, independent of the yellow profile POC (`InpZoneBorder`, `InpZoneFill`). A small minimum pixel height keeps it visible when zoomed out; the calculated bucket is unchanged.
- **High-volume ribbons:** continuous saturated turquoise / red bands with glow and a narrow upward-slanted end cap (decorative only). `InpBandPixels` defaults to 6 (range 2–16).
- **Labels:** six visible by default, collision-aware placement with anchor dots for additional signals. VA / POC guide lines stay on the profile side.
- **Link buttons** (RF / WhatsApp / YouTube / Forex Factory / IndicatorGenius) show their URL in the chart comment and Experts log — copy it into a browser. They are DLL-free and do not launch a browser.

## ⚙️ Key inputs

| Input | Default (range) |
|---|---|
| Length (window) | 200 (1–2500) |
| Price buckets | 35 (5–100) |
| Value area | 70 % (1–100) |
| Alignment | Center (left / center / right) |
| Placement | Right of Price (or on candles) |
| Width | 0.5 (0.1–1) |
| Depth X / Depth Y | 0.08 (−1–1) / 0.5 (−2–2) |
| Bounding box (`InpBoundingBox`) | Off |
| High-volume display | On |
| Anomaly factor | 2.5 (minimum 1) |
| Volume source | Tick volume — real volume is strict, with no silent substitution if the broker provides none |
| `ClosedBars` | false (current candle included) |
| `InpInstance` | Use different values for multiple copies on one chart |

Colours (bull / bear / POC / border) are configurable too. All parameters are edited in **Indicator Properties → Inputs**.

## 🔔 Optional alerts

Popup and push are **off** by default. Alerts check each newly closed candle against a separate profile of older bars (shifts 2 to Length+1): POC cross, close above VAH, close below VAL, and high volume versus that prior window's mean. No alert fires on initial attachment. Push needs the terminal's usual notification setup. These are context notifications, not trade orders, and alert anomaly classification can differ from the displayed rolling-window classification.

## 🔌 Data interface

Six `DRAW_NONE` buffers: **0** POC, **1** VAH, **2** VAL, **3** estimated delta, **4** classified total volume, **5** anomaly count. Read index 0 for the current snapshot. Older indices are snapshots accumulated while attached — not a historical recalculation. Unavailable initial cells are `EMPTY_VALUE`.

## 🛠️ Installation

1. In MetaTrader choose `File → Open Data Folder`.
2. Copy the `.ex5` into `MQL5 → Indicators` (MT5) or the `.ex4` into `MQL4 → Indicators` (MT4).
3. Refresh the Navigator and attach the indicator to a chart.
4. Download sufficient chart history.

No DLL imports, account lock, expiry, paid activation or order execution. After updating, reload the indicator on the chart — replacing an EX5 on disk does not guarantee that a running instance picks up the new file.

## ⚠️ Notes

- The large wireframe some users saw was the optional calculation-range bounding box, not a volume zone. It is now **off** by default; saved inputs may still keep it on — set it to false or re-attach with defaults.
- The overlay rejects a mismatched chart / calculation symbol or timeframe, clears stale graphics when history or coordinates are unavailable, and retries loading data.
- Signals are built from older profiles and confirmed pivots in chronological order, but history loading, broker corrections or a different starting history can change Wilder initialisation and early signals — this is not an unlimited non-repainting guarantee. The display profile remains rolling independently of the signal engine.
- The POC zone follows the calculated rolling bucket; prices, lengths and locations depend on chart data and settings, so different feeds will not produce identical geometry.
- Volume estimates and visual levels do not guarantee future outcomes.

## 🙏 Credits

- Original: [Order Flow 3D Delta Profile](https://www.tradingview.com/script/o0u6xrMj-Order-Flow-3D-Delta-Profile-LuxAlgo/) © LuxAlgo.
- Strategy video by [Soheil PKO](https://www.youtube.com/watch?v=5ZKai50qErM).
- Adaptation, native rendering, dashboard, extra controls and alerts: trader.lifestyle, 2026.
- License: **CC BY-NC-SA 4.0** — preserve attribution; non-commercial use and redistribution under the same license. No endorsement by LuxAlgo or the video creator is claimed.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
