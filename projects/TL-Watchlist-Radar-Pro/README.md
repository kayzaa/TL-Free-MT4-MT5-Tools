<div align="center">

# ⚡ TL Watchlist Radar Pro

**Multi-symbol watchlist radar: scanner, heatmap, metrics and rules — scanner only, no trading.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Indicator-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Watchlist_Radar_Pro_MT5_radar_detail.png" alt="TL Watchlist Radar Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL_Watchlist_Radar_Pro.ex4`](MT4/TL_Watchlist_Radar_Pro.ex4) |
| **MT5** | [`TL_Watchlist_Radar_Pro.ex5`](MT5/TL_Watchlist_Radar_Pro.ex5) |

> Compiled build only — source code is not published.

## Important Scope

This is an independent reconstruction of publicly demonstrated scanner functions, with the requested price/VWAP/MA/candle-series extensions. It is not the original Multi Market Scanner, is not endorsed by its author, and does not reproduce a published proprietary source code. Identical scores, preset values and hidden behavior cannot be established from screenshots and a demonstration video. English is the complete primary interface. Spanish, Italian and French cover navigation and many setting labels; help, rule descriptions and some status/value strings remain English. This is not a claim of complete four-language parity.

## Installation

- MT4: File > Open Data Folder > MQL4 > Experts. Copy TL_Watchlist_Radar_Pro.ex4 there.
- MT5: File > Open Data Folder > MQL5 > Experts. Copy TL_Watchlist_Radar_Pro.ex5 there.
- Refresh Navigator > Expert Advisors and attach the matching EA to one chart.
- Open SETTINGS in the dashboard. All production configuration is in the panel; the standard EA Inputs tab intentionally has no scanner parameters.
- Select Scan universe, Timeframes and the desired filters. Wait for history.
- No DLL import, WebRequest permission, account lock or expiry is used.
- No orders are opened, modified or closed. Trading permission is unnecessary for scanner calculations. The platform must allow the EA to run and fetch history.
- Minimum practical chart area: approximately 784 x 532 pixels. Enlarge the chart if controls are clipped. Panel scale is capped to available chart space.

## Quick Start — The Requested 20-Point Example

SETTINGS > SCAN: choose Market Watch, Custom List, or Favorites. SETTINGS > TIMEFRAMES: enter M15,H4 (or your preferred comma-separated periods). SETTINGS > PRICE RULES: Daily open: side = Above; Day Open Points = 20. Enable Only show rule matches to reduce the displayed symbol list to matches. Use RULE SCANNER to inspect each symbol/timeframe and each enabled condition. Above means strictly price > reference + 20 * that symbol's broker point. Below means strictly price < reference - 20 * that symbol's broker point. Equality fails. A tiny numerical tolerance rejects floating-point equality noise. Points are not pips: on a five-decimal EURUSD quote, 20 points = 0.00020; on a symbol with point size 0.01, 20 points = 0.20.

## Universes And Timeframes

Up to 200 symbols. Market Watch additions/removals are checked every 30 seconds. Custom/Favorites lists use commas. Exact broker names are preferred; suffix resolution is accepted only when unique. Ambiguous/missing names are reported. Changing the universe rebuilds the scan and starts signal-age tracking again.

## MT5: M1,M2,M3,M4,M5,M6,M10,M12,M15,M20,M30,H1,H2,H3,H4,H6,H8,H12,D1,W1,Mn1.

The same enabled rules run independently on every selected timeframe. Reference timeframe governs sparkline, spread/ATR, volatility and overall age. Equal or custom nonnegative weights combine the timeframe scores. Supply one weight per selected timeframe when custom weighting is enabled.

## Seven Rule Families

- Daily reference: previous broker D1 close, open, high, low, HLC3 or HL2.
- Daily open: opening price of the evaluated candle's broker D1 session.
- Session VWAP: M1 typical price (H+L+C)/3, weighted by tick volume or real volume, accumulated from broker D1 open through the evaluated time. This is a bar-volume approximation, not exchange tick-by-tick VWAP. Real volume must be supplied by the broker; there is no silent tick fallback.
- Timeframe open: open of the evaluated candle on each selected timeframe.
- Candle pivot: HLC3, HL2 or OHLC4; choose the evaluated candle or the candle immediately preceding it. This is a candle average, not a swing-pivot detector.
- Moving average: period 1..2000; SMA, EMA, SMMA or LWMA; close/open/high/low/ median/typical/weighted applied price. Native platform MA, evaluated on each TF.
- Consecutive candles: 1..100 bullish, bearish, or either; At Least or Exactly N. Only completed candles count, including in LIVE mode. Doji and candles whose body is not greater than the minimum-body setting break the sequence. Counts are capped by the requested lookback (N+2 closed candles); they are sufficient to decide At Least/Exactly, not unlimited historical run lengths.
Rules 1..6 have their own Disabled/Above/Below choice and nonnegative point offset. ALL / ANY combines enabled rule families. No enabled rules means no rule match. Missing data in any enabled rule blocks a match, including ANY mode. Any timeframe / ALL timeframes is a separate symbol-level match requirement. The upper scoring filters also apply if you explicitly enable them.

## Confirmed And Live

CONFIRMED compares the most recently closed candle's close with references anchored to that candle. A Friday candle remains anchored to Friday across a weekend. LIVE compares the current bid and may change until the candle closes. The score in LIVE mode includes the forming bar. Stale live quotes do not match. Closed-bar rule results can remain valid while the market is closed; the health label and alert gate separately indicate market closure or stale quotes.

## Dashboard

SCANNER: one row per symbol, price/change, individual TF scores, overall score, alignment, age, trend sparkline, favorite, mute and chart-open actions. Click a column to sort; TOP SETUPS ranks strength, alignment, then freshness. Use page/TF arrows for lists and columns that do not fit. Click a score for Detail. HEATMAP: signed directional strength across symbols and timeframes. DETAIL: candle/tick-volume chart and four score contributions; METRICS opens the full indicator list and signals by timeframe, including on smaller charts. RECENT SIGNALS: confirmed transitions, newest first. Retention 5..100 rows. RULE SCANNER: pass/fail and distance in broker points for every enabled rule. SETTINGS: ten pages; numeric/text values open an editor, enums cycle on click. Enter/APPLY saves; Esc/CANCEL cancels. Changes autosave locally per chart ID. The star edits Favorites. A/M toggles per-symbol alert muting. OPEN opens that symbol at the reference timeframe, or the selected detail timeframe. X collapses to a draggable pill; click to reopen. Drag the header to reposition. Dark/light theme, animated logo, hover explanations and scale 1..2 are included. Community buttons display the destination URL in a dialog; open it in a browser.

## Filters And Alerts

Direction, strong-only, minimum score/alignment, freshness, favorites, category, volatility, spread quality and symbol search are available under SETTINGS. Market categories use broker paths/name heuristics; unusual names may be Other. Spread/ATR can be ignored, warned about, or filtered. Missing history is shown. Alerts default OFF. Popup and sound channels default ON but are inactive until Enable alerts is ON. Push/email require the terminal's own notification setup. Events: new Buy/Sell, Strong Buy/Sell, score crossing, direction reversal, new Watch, alignment reached and new rule match. Alerts require a transition, not every tick. Default cooldown: 900 seconds per symbol/timeframe/event. Minimum score/alignment, confirmed-only, fresh-only and broker-time active hours are independent alert gates. Overnight hours are supported; equal hours = all day. Muted symbols, stale/closed-market health and configured spread exclusions suppress notifications. In the tester, notifications are logged, never sent. On first initialization, existing states do not generate transition alerts. Recent history and signal age restart when configuration rebuilds the scanner.

## Independent Scoring Formula — Not Original Numerical Parity

Score is descriptive strength, not a probability or an instruction to trade. Four signed components use weights 30/25/25/20 by default, normalized to 100. Each component is bounded to [-1,1] before its weighted contribution. Trend = .65*clip((EMAfast-EMAslow)/ATR) + .35*clip(4*EMAfastSlope/ATR). Momentum = .6*clip((RSI14-50)/30) + .4*clip(5*MACDhist/ATR). Structure = .4*(2*rangePosition-1) + .3*mean(highDirection,lowDirection) + .3*breakoutDirection. Range uses the previous 20 bars; high/low direction compares with a 20-bar range shifted back 10 bars. Breakout compares the evaluated close with that prior range. DMI strength = clip(2*(DIplus-DIminus)/max(1,DIplus+DIminus))*clip01(ADX14/40). Sum the four weighted contributions. EMA defaults20/50, MACD12/26/signal9; Wilder-smoothed ATR/RSI/DMI/ADX use period14 with zero-seeded smoothing over max(350,6*slowEMA) bars where available, requiring max(100,3*slowEMA) bars. EMA starts from the first available close. This seed convention is explicit and may differ from other indicators. EMA slope is a one-bar change. Magnitude <40 neutral; >=40 watch; >=55 buy/sell; >=75 strong. Sign gives direction. Overall is the weighted signed mean of selected TF scores. Alignment counts non-neutral timeframe signals with the same sign as the overall classification. All selected TF scores and reference TF data must be available for overall status. Volatility is ATR14 / mean(previous50 ATR14 values): <.7 low, <1.3 normal, <2 high, otherwise extreme. Overall age is bars since observed classification change on the reference timeframe; it does not backfill before attachment. Default/Trend/Swing/Intraday presets are available; non-default preset values are independent choices, not recovered original values. Fast/Normal/Low CPU/Custom modes control refresh and bounded scan batches.

## Limitations / Evidence

All six original MQL5 screenshots and 80 sampled video frames across the full video, plus its transcript, informed the feature inventory. Not every frame of the video was inspected. Hidden menu behavior and original mathematics remain unverified. Pagination substitutes for the original scrolling/TF-chip layout; there is no separate ellipsis action menu or distinct minimize/close pair. Market Watch reconciliation is periodic; the scheduler uses sequential bounded batches, not an original proprietary prioritization algorithm. MT4 Strategy Tester validates only its selected test symbol; use a demo terminal for a live multi-symbol acceptance test. Historical modeled ticks are not real ticks. Native MT4/MT5 QA runs and native canvas render captures were completed. The MT5 visual-tester run completed, with native UI audit assertions passing. A journal 'nothing to analyze' message did not stop that completed run. Exhaustive manual mouse/DPI/language testing is not claimed. This build should be reviewed on your demo installation before posting. Rule computations were independently compared with exported native bar data; this is not a profitability test or a validation of the original proprietary score.

## Source Credit

Original concept: Multi Market Scanner MT4, Eduardo Cumplido / Cloud Portfolios. <https://www.mql5.com/en/market/product/198327> Demonstration: <https://www.youtube.com/watch?v=n0kDJ0xZeaM> Independent extensions and FF edition: trader.lifestyle. <https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4> <https://www.youtube.com/@traderlifestyle> <https://wa.me/18585003724> CREATED WITH INDICATORGENIUS.COM — <https://indicatorgenius.com/>

Trading involves risk. Scanner conditions are information, not guaranteed outcomes.

## 🖼️ More screenshots

<img src="screenshots/TL_Watchlist_Radar_Pro_MT5_radar_heatmap.png" width="49%">
<img src="screenshots/TL_Watchlist_Radar_Pro_MT5_radar_metrics.png" width="49%">
<img src="screenshots/TL_Watchlist_Radar_Pro_MT5_radar_scanner.png" width="49%">

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
