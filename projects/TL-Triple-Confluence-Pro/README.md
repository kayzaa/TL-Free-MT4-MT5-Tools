<!-- auto-generated: remove this line after hand-editing so publish keeps your text -->
<div align="center">

# ⚡ TL Triple Confluence Pro

**EMA / RSI / Stochastic confluence indicator with a large canvas dashboard, sculpted EMA ribbon and BUY / SELL pills. Never trades.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Indicator-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Triple_Confluence_Pro_Dashboard.png" alt="TL Triple Confluence Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Triple Confluence Pro.ex4`](MT4/TL%20Triple%20Confluence%20Pro.ex4) |
| **MT5** | [`TL Triple Confluence Pro.ex5`](MT5/TL%20Triple%20Confluence%20Pro.ex5) |

> Compiled build only — source code is not published.

## Overview

An EMA / RSI / stochastic indicator with a large Canvas dashboard, sculpted EMA ribbon, BUY/SELL pills and independent historical signal results. It never places, modifies or closes orders. No account lock, no expiry, no DLL.

## Validation Status

MT5: compiled and run in MetaTrader; native calculation, UI and visual-tester checks completed. MT4: compiled successfully, but the isolated MT4 terminal stalled during startup before loading the indicator. Its EX4 is supplied in MT4_COMPILE_ONLY and must not be described as runtime-verified. See VALIDATION_STATUS.txt for the precise scope of the tests.

## Source And Credit

Strategy explanation: Trader DNA, video wf6s7HHUP_8 (37:18). <https://www.youtube.com/watch?v=wf6s7HHUP_8> This is an independent implementation, not an original Trader DNA product. The video's claims that losses are impossible are not adopted or verified.

## What The Video Actually Teaches

- EMA calibration is discretionary. The introductory examples discuss 20, 34, 50, 75, 100, 150 and 200, a single EMA 100, then 50 / 110 / 250. These illustrate choosing periods for a market/timeframe. They are not additional filters in the later three-indicator setup.
- The combined example uses EMA 25 / 75 / 140, RSI 75, and stochastic 14/3/3.
- Establish a trend from ordered, sloping EMAs and price on the trend side.
- A pullback can reach the fast, middle or slow EMA. Breaking the fast EMA alone does not invalidate the underlying trend.
- RSI above 50 confirms bullish conditions; below 50 confirms bearish ones.
- A stochastic turn from the oversold/overbought area provides the stronger entry. The explicit SELL example crosses downward after a deeper EMA test.
- The video also discusses weaker entries that never reach an extreme zone, suggesting a smaller target such as 1.5R or 2R, or skipping them.
- The detailed SELL example puts the stop above the slow EMA and holds through a later fast-EMA pullback while RSI remains bearish.

## Exact Implemented Rules

All decisions use completed candles. Entry is the NEXT bar's open, so the pill is attached to the decision candle but its entry price belongs to the next bar.

STRICT TREND v1.10 — requested extra filters, not original video rules: Recheck ALL conditions on EVERY completed candle. No retained trend permission. BUY requires EMA fast > middle > slow; SELL is the directional mirror. Each EMA must move at least 0.12 ATR in the trend direction over 8 bars. Fast-to-slow ribbon width must be at least 0.50 ATR. Signed efficiency over 30 bars must be at least 0.20 in the EMA direction: direction * (close - close[30]) / sum(abs(close changes), 30 bars). This rejects both low net movement/chop and price moving against EMA order. BUY requires RSI > 53; SELL requires RSI < 47. Close must stay beyond slow EMA on the trend side. Three consecutive qualifying bars are required for entry. Any failed trend gate immediately blocks entries and clears the EMA touch. At least 20 bars must separate decision candles, including opposite directions. The entry candle must additionally close beyond the FAST EMA in trend direction and have a matching bullish/bearish candle body. No entry during an unrecovered pullback. Long quiet periods are expected with these strict defaults. These are mechanical classifications; they cannot predict future reversals.

A candle's high-low range must overlap an EMA, allowing the configured ATR tolerance. Track the deepest touched layer. A touch remains armed for the configured number of bars; further touches refresh the window.

BUY: bullish regime, recent EMA touch, close above the touched EMA and above the previous close, and stochastic K crossing above D. SELL: bearish regime, recent EMA touch, close below the touched EMA and below the previous close, and K crossing below D.

A / EXTREME: both K and D are below/equal 20 for BUY, or above/equal 80 for SELL, on either the cross candle or its immediately preceding candle. B / STANDARD: the same setup and cross without that extreme-zone qualification. Only A / EXTREME is enabled by default. ALL_SETUPS optionally adds B entries, but all strict trend and spacing filters still apply. After an entry signal, its touch is consumed; another touch is needed to re-arm.

## Implementation Choices — Not Fully Specified By The Video

The video does not give a complete algorithm for slope, near-touch distance, touch expiry, candle-close timing, all stop locations or final TP placement. These choices are explicit additions, not hidden claims of exact replication:

- **Slope span** — 8 completed bars, each EMA >= 0.12 ATR EMA touch tolerance         0.10 x simple ATR(14) Touch validity              5 bars, including the touch candle Rejection confirmation      Close beyond fast AND touched EMA + body + momentum Entry execution             Next bar open Stop                        Slow EMA at signal +/- 0.15 ATR, minimum 1 point Strong/A target             5R (configurable; not a complete video exit rule) Standard/B target           1.5R (configurable; video example) Default history             5,000 bars, plus calculation warm-up Hypothetical position size   0.10 lot Fixed simulated spread      0 points Round-turn commission       0 account-currency units per lot

BUY stop is below the slow EMA; SELL stop is above it. Stops/targets are fixed at entry. There are no partial exits, trailing stop, break-even or forced RSI exit in this version. RSI invalidation prevents new setups; it does not close an existing simulated signal. If the next open is already beyond the stop, the signal is marked GAP SKIP rather than assigned an invalid target.

For an existing chart, remove/re-add the indicator and use Inputs > Reset to load v1.10 defaults. Saved v1.00 templates may retain older shared settings. The strict trend gates are always active, including when grade B is enabled.

These parameters can be changed in Inputs. Periods must satisfy fast < middle < slow. RSI is separately configurable; changing the middle EMA does not silently change RSI. Manual EMA calibration is not automatic optimization.

## Dashboard And Chart

Large dark/cyan/gold Canvas dashboard with animated emblem, drag header, X-to-pill collapse, reopen, hover explanations and responsive columns. Trend engine, stochastic gauge, signal totals, selected-signal prices/results, recent signals and two momentum lenses are included.

PREVIOUS / NEXT selects a historical signal and moves the chart to it. The selected signal has a gold border; its entry, stop and target are drawn where within the visible price range. A target far outside view remains in the dashboard. Pills show direction, grade, EMA layer, decision time, status, points, R and estimated money. Dense charts show smaller dots where a full pill cannot fit. Increase chart space, zoom in or collapse the panel to see more.

The EMA ribbon, candles, wicks and scales share a coordinated theme. Removing the indicator restores its saved chart settings. Multiple instances on one chart require different Instance IDs; use only one theme-owning instance.

The RF / WA / YT / FF / source / IndicatorGenius buttons display their URL in a dialog. They do not require DLL imports or automatically launch a browser.

## Export

EXPORT CSV writes the current simulated ledger into the terminal's MQL4/Files or MQL5/Files folder. InpExportCSV enables an update after each new bar. Filename: TL_Triple_Confluence_SYMBOL_TIMEFRAME_INSTANCE.csv. The file is overwritten with the currently loaded history, not appended forever. It includes decision/entry time, side, grade, EMA layer, prices, status, exit-bar time, points, R, money estimate and cost assumptions. Nothing is uploaded.

## Installation

- MT5: File > Open Data Folder > MQL5 > Indicators. Copy the EX5 there (or to a TripleConfluence subfolder), refresh Navigator, then attach it to a chart.
- MT4: the same procedure under MQL4 > Indicators with the supplied EX4, noting the compile-only validation status. Both files are named: TL Triple Confluence Pro.ex5 TL Triple Confluence Pro.ex4 No other indicator, DLL or internet service is required by this indicator.
- Allow enough history: defaults need at least 843 bars to finish warm-up.
- Alerts and push notifications are OFF by default. Enabling push uses the terminal's own configured notification service. Attaching does not alert old signals.

## Buffer Map (same on MT4 and MT5)

0 fast EMA; 1 middle EMA; 2 slow EMA; 3 BUY next-open entry; 4 SELL next-open entry; 5 signal SL; 6 signal TP; 7 outcome status. Non-signals use EMPTY_VALUE in buffers 3-7. Status values are 0 OPEN, 1 TP, 2 SL, 3 AMBIGUOUS, 4 GAP SKIP. Status is retrospective and changes as later bars resolve a signal; do not use that future outcome as an entry filter. Decision buffers appear after the decision candle closes. The current-bar EMA display is sampled on recalculation; it is not an intrabar trading trigger.

Created with IndicatorGenius.com | <https://indicatorgenius.com/> <https://trader.lifestyle> Trading involves losses. A functioning implementation does not establish an edge.

## 🖼️ More screenshots

<img src="screenshots/TL_Triple_Confluence_Pro_Sell.png" width="49%">
<img src="screenshots/TL_Triple_Confluence_Pro_Chart.png" width="49%">

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
