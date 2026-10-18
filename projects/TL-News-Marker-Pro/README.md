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

## ✨ Highlights

- **News right on your chart.** Past events with **actual / forecast / previous**, upcoming events as dashed lines.
- **Better or worse at a glance.** Green / red labels based on the MT5 calendar rating — correct even for inverse numbers like unemployment.
- **Filter exactly what you trade.** Currencies, countries, impact level and event keywords.
- **Zero setup.** Uses the built-in MT5 economic calendar — no WebRequest, no DLL for the data.
- **Panel with countdown** to the next events, latest results and optional alerts.

## 🧠 How it works

Built from **decodagobert's** news-trading request on Forex Factory. It:

- Marks **past** news on the chart with the actual, forecast and previous value.
- Marks **upcoming** events for the next days (dashed lines).
- Lets you choose currencies / countries, impact (HIGH / MEDIUM / LOW, each on/off, also clickable in the panel), specific events (e.g. `CPI y/y; Cash Rate; NFP`) and how many days back / ahead to show.

### 📡 Data source

- The built-in **MT5 economic calendar** (MetaQuotes). Times are converted automatically — everything is shown in your broker's server time, exactly like the candles.
- Forecast = the forecast of the MT5 calendar. It can differ slightly from the Forex Factory consensus.
- Event names are always shown in **English**, whatever language your terminal uses (built from the calendar's English event code). The filter understands English keywords and also the names in your terminal language.

## 🖥️ Dashboard & chart

**On the chart**
- One vertical line per time stamp. Colour = impact: **red** HIGH, **orange** MEDIUM, **yellow** LOW. Solid = past, dashed = upcoming.
- A small vertical label next to each line (bottom or top of the chart — input), e.g. `USD CPI y/y  A 3.2%  F 3.1%  P 3.0%`.

| Label colour | Meaning |
|---|---|
| Green | Result better than the forecast for that currency |
| Red | Worse than the forecast |
| Grey | In line / no forecast |
| Blue | Upcoming |

- Hover a line to see the full name and actual / forecast / previous (revised) of **all** events at that time.
- Labels never overlap: when there is no room (zoomed out), high impact wins and the others are hidden until you zoom in. The lines always stay.

**Panel**
- HIGH / MEDIUM / LOW buttons (click to toggle).
- **NEXT EVENTS** with countdown and **LATEST RESULTS** (actual / forecast in green / red).
- Minimise with the "–" button.
- Link buttons YOUTUBE / ROBOFOREX / WHATSAPP / FOREX FACTORY.

**Alerts (optional)**
- X minutes before an event (high impact only, or all shown events).
- When the actual value is released (with better / worse).

## ⚙️ Key inputs

| Input | What it does |
|---|---|
| **Only these events** / **Hide these events** | Keyword lists separated by `;`. Case, spaces and symbols are ignored (`CPI y/y` = `cpi yy` = `cpi-yy`). Put a currency in front to limit it: `USD CPI y/y; AUD Cash Rate; USD NFP`. |
| **Built-in shortcuts** | Cash Rate, NFP, GDP, FOMC, ECB, BOE, BOJ, RBA, RBNZ, SNB, BOC (e.g. "Cash Rate" finds "RBA Interest Rate Decision") |
| **Print all event names** | `true` prints every event name + its keyword to the Experts tab |
| **Currencies** | `AUTO` = the currencies of the chart symbol (EURUSD → EUR + USD, XAUUSD → USD), `ALL` = every currency, or a list like `USD,EUR,AUD` |
| **Countries** (optional) | US, EU, DE, FR, GB, AU, JP, CH, CA, NZ, CN … e.g. only German data for EUR: `DE` |
| **Enable chart shift** | On by default — makes room on the right side for upcoming events |

**Filter examples**
- Only these events: `CPI y/y; Cash Rate`
- Only these events: `USD NFP; USD CPI; USD Interest Rate Decision`
- Hide these events: `speech; CFTC; auction`

## 🛠️ Installation

1. In MT5 open **File → Open Data Folder** and copy `TL News Marker Pro.ex5` to `MQL5 → Indicators`.
2. In the Navigator right-click **Indicators → Refresh**.
3. Drag **TL News Marker Pro** onto any chart.
4. Optional: tick **"Allow DLL imports"** for the link buttons — the indicator works without it, only the buttons don't.

## 🙏 Credits

Request by **decodagobert** in the Forex Factory thread "Free EAs, Indicators & Strategies – MT4 / MT5 / TV + Coding Help" — [post #6](https://www.forexfactory.com/thread/post/15931670#post15931670).

## ⚠️ Notes

- **MT5 only** — MT4 has no built-in economic calendar.
- The MT5 calendar is **not available in the Strategy Tester** — use the indicator on a live chart.
- This is an information tool, not a trading signal.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
