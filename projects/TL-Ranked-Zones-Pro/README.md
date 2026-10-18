<!-- auto-generated: remove this line after hand-editing so publish keeps your text -->
<div align="center">

# ⚡ TL Ranked Zones Pro

**Supply & demand zones ranked by strength, based on Zeiierman's ranked-zone algorithms.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Indicator-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Ranked_Zones_Pro_Dashboard.png" alt="TL Ranked Zones Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Ranked Zones Pro.ex4`](MT4/TL%20Ranked%20Zones%20Pro.ex4) |
| **MT5** | [`TL Ranked Zones Pro.ex5`](MT5/TL%20Ranked%20Zones%20Pro.ex5) |

> Compiled build only — source code is not published.

## Overview

MetaTrader port and FF interface: trader.lifestyle

## What This Is

One chart indicator combining the three tools introduced by Soheil PKO: Ranked Order Block Zones, Ranked FVG Imbalance Zones, and Ranked Support & Resistance Zones. Each module has its own ON/OFF button and initial input. This is an analysis indicator. It does not place orders or invent a complete entry/exit system that was not specified in the video.

## Installation

- MT4: File > Open Data Folder > MQL4 > Indicators. Copy TL Ranked Zones Pro.ex4.
- MT5: File > Open Data Folder > MQL5 > Indicators. Copy TL Ranked Zones Pro.ex5.
- Refresh Navigator > Indicators, then drag the indicator onto your chart.
- DLL imports and AutoTrading are not required. There is no account lock or expiry.
- For upgrades remove and re-add the indicator; use Inputs > Reset for defaults.

## 1. Order Blocks

A bullish candle following a bearish candle creates a bullish OB if the new candle body is at least 1.1 ATR. The bearish case is mirrored. The zone is the FULL high/low range of the previous candle. Same-direction overlapping OBs can merge when overlap reaches 50% of the smaller zone and combined size <= 2 ATR. Stored: 50; displayed: strongest 10. Original raw-price quality formula: zone height * 100 + source volume ratio * 10 + trend score * 20
- mitigation * 50 - age in bars * 0.1.
The ATR-normalized strength display is a DIFFERENT calculation from ranking.

## 2. Fair Value Gaps

Bullish: current low > high two bars earlier. Bearish: current high < low two bars earlier. The exact wick-to-wick gap becomes the zone. Stored: 50; displayed: strongest 10. Ranking uses the same original raw-price formula as OB, with current-bar volume and candle strength. No FVG merging is added. The source's conditional ATR call is represented by a gap-event ATR state; its early warm-up can leave strength unavailable. It is not silently replaced by the globally calculated OB/SR ATR.

## 3. Support / Resistance

Confirmed pivot highs form resistance; confirmed pivot lows form support. Default pivot span is five bars on EACH side. The zone is only discovered after the five right-side bars exist; its drawing begins at the pivot time. Min adjacent swing quality: 0.15 ATR. Zone total width: 0.40 ATR. Same-side zones absorb when midpoint separation <= 0.55 ATR or overlap >=35% of the smaller zone. A close beyond the outer edge + 0.12 ATR breaks the zone. Stored: 60; displayed: strongest 8; broken references: latest 4. S/R zones expire after 450 bars. Ranking incorporates current ATR-normalized width, stored volume/trend/swing factors, touches, mitigation and age.

## Original Behaviour Is Retained

Volume SMA: 20; trend EMA: 50; ATR length: 14. OB volume is from its source candle, FVG volume from the formation candle, and SR volume from the pivot. All ratios use the volume baseline at the detection bar. OB/FVG trend and strength factors are retained from creation, while score changes with mitigation and age. SR strengths are recalculated with score. Mitigation follows the CURRENT touching bar, so it can decrease after a shallower revisit. Merges reset mitigation. These source behaviours remain. OB/FVG are removed at full mitigation. SR uses its separate close-break rule. Merged OB bull/bear strength maxima may sum to more than 100%. SR strengths are two independent scores and need not sum to 100%. They are NOT measured

## Live Candle And History

The open candle is provisional. Each recalculation starts from the last closed bar's committed state, then evaluates the current candle again, corresponding to Pine's realtime rollback model. Zones and ranking can change intrabar. Do not describe this as a closed-bar-only or never-repainting indicator. Default history budget: 5,000 bars; configurable 100–50,000. Broker history, start date, symbol tick size, candles and tick volume affect the result. MT4/MT5 here use broker TICK VOLUME. A different TradingView feed will not necessarily produce the same zones. Exact cross-platform numerical identity requires the same input series and initialization history.

## Controls And Visuals

ON/OFF hides that module's zones and suppresses its notifications; internal tracking continues so re-enabling restores the current ranked result. Input toggles set the initial state on attachment/reinitialization; button states are not saved as permanent input presets. Drag the header to reposition; X collapses to a compact pill; click to reopen. Panel position/collapse are remembered per chart and instance ID. Short chart windows use multiple panel columns. Hover sections for help. Use a different Instance ID for an independent second visible dashboard. A same-ID additional reader calculates without replacing the existing display. The panel reports the top stored zone; a global direction display filter can hide that zone on the chart. Top N is selected within each module. Zone labels avoid one another; when insufficient space remains, a lower-rank label is omitted while its exact zone remains visible. Thin zones stay thin. Dark chart styling, shaded zones, light edges and floating cards are visual additions; they do not modify the mathematical zone boundaries. Theme and modified chart settings are restored when the indicator is removed. RF / WhatsApp / YouTube / FF / IndicatorGenius buttons display the destination URL in a dialog for opening in your browser. No DLL or browser-launch trick.

## Alerts

Popup and push alerts are OFF by default. Enable the corresponding inputs. Push notifications require MetaTrader's own notification configuration. Events: new zones, touches, leader changes, removals/breaks and SR 75% mitigation. Events are aggregated by module and deduplicated within the candle. Initial loading does not replay historical alerts. An intrabar alert can become invalid before candle close. No email alerts, sound files, or trading execution added. The three hidden data buffers expose current active zone counts (OB/FVG/SR).

## How To Use The Levels

- The video discusses zones as context for retests, entries, stops and targets.
- A bearish OB/FVG or resistance can be a potential resistance reference; a bullish OB/FVG or support can be a potential support reference. A retest is not an automatic buy or sell instruction. The video does not specify complete entry confirmation, fixed RR, position sizing or mechanical exit rules.
- Accordingly, this indicator adds no invented BUY/SELL signals, SL/TP orders, partials, trailing stops, performance statistics or profit claims.

## Attribution / License

Original algorithms: Zeiierman, licensed CC BY-NC-SA 4.0. The MQL adaptation is supplied under the same license: attribution required, noncommercial use, share adaptations under the same terms. No author endorsement. License: <https://creativecommons.org/licenses/by-nc-sa/4.0/> Video: <https://www.youtube.com/watch?v=k0-dCuI2gaE> OB: <https://www.tradingview.com/script/Ce4kPpHV-Ranked-Order-Block-Zones-Zeiierman/> FVG: <https://www.tradingview.com/script/Z4h7vDqN-Ranked-FVG-Imbalance-Zones-Zeiierman/> SR: <https://www.tradingview.com/script/jTQU8WBS-Ranked-Support-Resistance-Zones-Zeiierman/>

Trading involves risk. Scores describe the model, not future trade outcomes.

## 🖼️ More screenshots

<img src="screenshots/TL_Ranked_Zones_Pro_Chart.png" width="49%">

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
