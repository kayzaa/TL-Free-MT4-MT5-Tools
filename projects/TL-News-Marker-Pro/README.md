<div align="center">

# ⚡ TL News Marker Pro

**Economic news from the MT5 calendar right on the chart: actual / forecast / previous, filters and upcoming events.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Indicator-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_News_Marker_Pro_TNM_shot_s1.png" alt="TL News Marker Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT5** | [`TL News Marker Pro.ex5`](MT5/TL%20News%20Marker%20Pro.ex5) |

> Compiled build only — source code is not published.

## Overview

decodagobert's news trading request from Forex Factory as an MT5 indicator. Source: thread "Free EAs, Indicators & Strategies – MT4 / MT5 / TV + Coding Help", post #6: <https://www.forexfactory.com/thread/post/15931670#post15931670>

## What It Does (as requested)

- Marks PAST news on the chart with ACTUAL, FORECAST and PREVIOUS value.
- Marks UPCOMING events for the next days (dashed lines).
- Selectable currencies / countries.
- Selectable impact: HIGH / MEDIUM / LOW (each on/off, also clickable in the panel).
- Selectable events, e.g. "CPI y/y; Cash Rate; NFP" - only those are shown.
- Selectable range: how many days back, how many days ahead.

## Data Source

- The built-in MT5 economic calendar (MetaQuotes). No WebRequest, no DLL for the data, nothing to set up. Times are converted automatically - everything is in your broker's server time, exactly like the candles.
- Forecast = the forecast of the MT5 calendar. It can differ slightly from the Forex Factory consensus.
- Event names are always shown in ENGLISH, whatever language your terminal uses (built from the calendar's English event code). The filter understands English keywords and also the names in your terminal language.
- The MT5 calendar is NOT available in the Strategy Tester -> use it on a live chart.
- MT4 has no built-in calendar, so this is MT5 only.

## On The Chart

- One vertical line per time stamp. Colour = impact: red HIGH, orange MEDIUM, yellow LOW. Solid = past, dashed = upcoming.
- A small vertical text next to each line (bottom of the chart, or top - input): USD CPI y/y  A 3.2%  F 3.1%  P 3.0% GREEN = the result was better than the forecast for that currency, RED   = worse, GREY = in line / no forecast, BLUE = upcoming. "Better" comes from the MT5 calendar rating, so it is correct for inverse numbers too (higher unemployment or jobless claims = red).
- Hover a line: full name, actual / forecast / previous (revised) of ALL events at that time.
- Labels never overlap: if there is no room (zoomed out), high impact wins and the others are hidden until you zoom in. The lines always stay.

## Event Filter  (inputs "Only these events" / "Hide these events", separated by ;)

- Case, spaces and symbols are ignored:  "CPI y/y" = "cpi yy" = "cpi-yy".
- Put a currency in front to limit it:  "USD CPI y/y; AUD Cash Rate; USD NFP".
- Built-in shortcuts: Cash Rate, NFP, GDP, FOMC, ECB, BOE, BOJ, RBA, RBNZ, SNB, BOC (e.g. "Cash Rate" finds "RBA Interest Rate Decision").
- To see every event name + its keyword: set "Print all event names" = true and look at the Experts tab.
- Examples: Only these events:  CPI y/y; Cash Rate Only these events:  USD NFP; USD CPI; USD Interest Rate Decision Hide these events:  speech; CFTC; auction

## Currencies / Countries

- AUTO = the currencies of the chart symbol (EURUSD -> EUR + USD, XAUUSD -> USD).
- ALL  = every currency.
- Or a list: USD,EUR,AUD
- Countries (optional): US,EU,DE,FR,GB,AU,JP,CH,CA,NZ,CN ... e.g. only German data for EUR: DE

## Panel

- HIGH / MEDIUM / LOW buttons (click to toggle).
- NEXT EVENTS with countdown, LATEST RESULTS (actual / forecast in green / red).
- Minimise with the "–" button.
- Link buttons YOUTUBE / ROBOFOREX / WHATSAPP / FOREX FACTORY (need "Allow DLL imports" - the indicator works without it, only the buttons don't).

## Alerts (optional)

- X minutes before an event (high impact only, or all shown events).
- When the actual value is released (with better / worse).

## Installation

- MT5: File > Open Data Folder > MQL5\Indicators\  -> copy "TL News Marker Pro.ex5" there.
- Navigator: right-click "Indicators" > Refresh.
- Drag "TL News Marker Pro" on any chart. Tick "Allow DLL imports" for the link buttons.
- Tip: the input "Enable chart shift" (on by default) makes room on the right side for the upcoming events.

- FREE. No lock, no expiry, no license key. Source code included.
- Trading involves high risk. This is an information tool, not a signal.
- trader.lifestyle

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
