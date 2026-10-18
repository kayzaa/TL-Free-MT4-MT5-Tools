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

## Installation

- Extract the appropriate EX5/EX4. In MetaTrader choose File > Open Data Folder, then copy into MQL5/Indicators or MQL4/Indicators. Refresh Navigator and attach to a chart. No DLL imports, account lock, expiry, paid activation or order execution. Download sufficient chart history. Parameters are edited in Indicator Properties > Inputs. Use different InpInstance values for multiple copies on one chart.

## What It Does

This adapts LuxAlgo's Order Flow 3D Delta Profile to native MT4/MT5 with a trader.lifestyle dark/cyan/gold canvas dashboard and 3D chart layer. Up candles contribute their entire selected volume to bullish volume, down candles to bearish volume, and dojis are excluded from the profile. Each candle is assigned to one price bin at HL2, not distributed over its range. Delta is bullish minus bearish candle volume: a proxy, not measured bid/ask aggressor flow or a footprint.

The original profile width is TOTAL VOLUME. Color and center alignment direction reflect delta. Optional ABSOLUTE_DELTA width is an extra mode; POC and value area always use total volume. POC is the largest-volume bin; equal maxima choose the lowest price bin. Value area expands contiguously from POC toward the larger neighboring volume, with upper-bin priority on ties. Whole-bin coverage may exceed the requested percentage. POC is the bin midpoint; VA boundaries use outer bin edges.

Original features: configurable window and price bins, POC, percentage value area, left/center/right alignment, on-candles/right-of-price placement, width, horizontal/vertical 3D depth, bounding box, bull/bear/POC/border colors, high-volume glow and first-retest beams. Anomalies exceed the window average times the threshold (strict >); the average includes dojis. Glow spans high to low. Beam starts at HL2 and ends at the first subsequent candle touching that price; absent a touch, it reaches the profile start.

## Defaults And Limits

Length 200 (1–2500), buckets 35 (5–100), value area 70% (1–100), alignment Center, placement Right of Price, width 0.5 (0.1–1), depth X 0.08 (-1–1), depth Y 0.5 (-2–2), bounding box disabled and high-volume display enabled, anomaly factor 2.5 (minimum 1). Tick volume is default. Real volume is strict: no silent substitution when the broker provides none. The default developing window includes the current candle. ClosedBars=true excludes it. Both are rolling profiles: bins, POC, value area and old anomaly classifications can change as the window moves. This is not a fixed historical signal indicator.

## Added Controls

POC/VA price labels and optional POC-bin zone; whole-chart theme; auto screen fitting; live volume balance, coverage, anomaly and engine information; draggable header; X collapses to a draggable pill and clicking the pill restores it; hover explanations; PROFILE ON/OFF; REFRESH. Panel state persists. Theme is restored on removal. Deleted layer/panel objects are rebuilt. Small charts may rearrange dashboard columns. RF/WhatsApp/YouTube/Forex Factory/IndicatorGenius buttons display their URL in the chart comment and Experts log. Copy the address into a browser; these are DLL-free address controls, not automatic browser launchers.

## Optional Alerts

Popup and push are OFF by default. Notifications examine a newly closed candle against a separate profile of older bars (shifts 2 through Length+1): POC crossing, close above VAH, close below VAL, and high volume versus that prior window's mean. No alert on initial attachment. Push requires the terminal's usual notification configuration. These are context notifications, not trade orders. Alert anomaly classification can differ from the displayed rolling-window classification.

STRATEGY — v1.12 The video explains discretionary POC role reversal, RSI divergence and a short stop above the zone (04:05–06:56). This version turns those examples into explicit, adjustable closed-candle rules. These confirmation details are our implementation, not a claim that the video specifies a complete automated strategy. No orders are placed.

DEFAULTS: Strategy on; both Breakout and Retest; mandatory RSI-divergence filter OFF (divergence still calculated and tagged); RSI14, pivot wings3, divergence lifetime60 bars, retest lifetime20 bars, minimum signal spacing5 bars, historical signal window800 plus calculation warmup, stop padding15% of the POC bucket width, latest setup stop shown. Optional popup/push notifications remain off. Set InpRequireDivergence=true for the stricter RSI-confirmed variant.

BUY BREAK: Calculate the POC bucket from the Length candles BEFORE the tested candle. Previous close is at/below the bucket high and tested closed candle closes above it. SELL BREAK mirrors this at the bucket low. No current/future candle is used in that reference profile.

RETEST: A breakout arms and freezes that exact bucket. Within RetestBars, a LATER candle intersects the frozen zone and closes back above its upper edge with a bullish body for BUY, or below its lower edge with a bearish body for SELL. A close through the opposite edge invalidates the armed setup. A new breakout replaces the armed reference. Each qualifying retest consumes its setup; signal spacing and the optional RSI gate still apply. Breakout-and-Retest, Breakout-only and Retest-only are selectable.

RSI: Wilder-smoothed RSI on closes. A price pivot requires PivotBars bars on both sides; equality is allowed only on the older side (rightmost equal extreme wins). It becomes usable only when the right-hand bars have closed. Bullish divergence: the two successive confirmed price lows form a lower low while RSI sampled at those lows forms a higher low. Bearish divergence mirrors that at highs. Divergence expires DivergenceLife bars after confirmation. Pills tagged + RSI have a valid matching divergence. Mandatory filtering is optional. The engine computes RSI internally; it does not open a separate oscillator pane.

PILLS: BUY/SELL, POC BREAK/POC RETEST and optional + RSI. They are timestamped on the confirmation candle, never moved back to an earlier pivot. Use the next candle/open for an executable forward-testing assumption, with spread/slippage; the displayed close is not a guaranteed fill.

STOP: BUY below the frozen bucket low; SELL above its high; padding is max(one symbol point, bucket width times StopPadding). The chart shows the latest setup's original stop, explicitly LAST SETUP SL. It is a reference, not a live-position tracker; it remains displayed after price passes it. No automatic trailing, exit, target, position sizing or TP is invented. The video specifies no fixed take-profit rule.

HISTORY: Signal generation processes bars in chronological order using older profiles and confirmed pivots. Prefix tests check that adding later candles does not change existing signals for the same starting history. History loading, broker corrections and a different starting history can change Wilder initialization and early signals; do not interpret this as an unlimited non-repainting guarantee. The display profile remains rolling/developing independently of the signal engine.

DESIGN: The 3D depth face now projects DOWN only. DepthY controls its magnitude (both signs give downward projection). No upper depth face is drawn. Glow intensity 0–100 (default70) controls halos around profile bars and volume beams. BUY/SELL pills have rounded corners, glow, a connector and an anchor dot. Default six visible labels, with collision-aware placement and anchor dots for additional signals. Compact dashboard hides the extra volume/anomaly blocks on shorter charts; all calculations continue. Bright red/turquoise faces and a yellow POC match the supplied visual reference. Layout adapts to chart dimensions.

## Data Interface

Six DRAW_NONE buffers: 0 POC, 1 VAH, 2 VAL, 3 estimated delta, 4 classified total volume, 5 anomaly count. Read index 0 for current snapshots. Older indices are snapshots accumulated while attached, NOT a historical recalculation service. Unavailable initial cells are EMPTY_VALUE.

## Source And License

Original © LuxAlgo, Order Flow 3D Delta Profile: <https://www.tradingview.com/script/o0u6xrMj-Order-Flow-3D-Delta-Profile-LuxAlgo/> Video by Soheil PKO: <https://www.youtube.com/watch?v=5ZKai50qErM> Adaptation, native rendering, dashboard, extra controls and alerts: trader.lifestyle, 2026. CC BY-NC-SA 4.0. Preserve attribution; noncommercial use and redistribution under the same license. See LICENSE.txt. No claim of endorsement by LuxAlgo or the video creator. Trading involves risk. Volume estimates and visual levels do not guarantee future outcomes.

ZONE APPEARANCE — v1.12 The chart POC zone now has the reference image's purple rectangular rim, muted light gray/lilac core and soft halo. Its color is independent of the yellow profile POC. InpZoneBorder and InpZoneFill allow adjustment. A small minimum pixel height preserves a visible border/core when zoomed out; the calculated price bucket is unchanged. High-volume ribbons are continuous saturated turquoise/red bands, with glow and a narrow upward-slanted extension at the end, matching the supplied reference style. InpBandPixels defaults to 6 (range 2–16); price-scaled thickness can exceed that minimum. Candle glow, threshold and first-touch termination rules are unchanged. The small decorative end cap is not an extension of the signal's time validity. Additional VA/POC price guide lines now stay on the profile side, avoiding a yellow line through the violet chart zone. Profile rendering, compact dashboard and BUY/SELL strategy remain unchanged. This matches the requested visual treatment. The POC zone still follows the calculated rolling bucket; the reference rectangle was manually drawn. Prices, lengths and locations depend on chart data and settings, so different feeds will not create identical geometry.

v1.12 / Timeframe and clean chart The large wireframe was the optional calculation-range bounding box, not a volume zone. Its default is now OFF (InpBoundingBox=false). Existing saved inputs can preserve true: change it to false or remove/re-attach using defaults. Overlay rendering now rejects mismatched chart/calculation symbol or timeframe, clears stale graphics when history or coordinates are unavailable, and retries loading data. Our iCustom test harness also now deletes/releases its old-period handle before creating the new-period handle. Attach the indicator normally via Navigator on your own charts. Reload the updated indicator; replacing an EX5 on disk does not guarantee that an existing chart instance loads the new binary. High-volume bands are conditional: volume must exceed 2.5x the rolling mean and each band ends at the first later HL2 touch. A quick next-bar retest creates a short band; the video does not imply long horizontal bands on every market. No threshold was silently reduced and no fictitious zones were added.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
