<div align="center">

# ⚡ TL News Arsenal Quant

**106 news trading tools in ONE animated quant dashboard — MT5 calendar + Forex Factory feed.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL News Arsenal Quant.ex4`](MT4/TL%20News%20Arsenal%20Quant.ex4) |
| **MT5** | [`TL News Arsenal Quant.ex5`](MT5/TL%20News%20Arsenal%20Quant.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **A complete news-trading cockpit** — calendar, pre-news, live spike, surprise, post-news, macro, headlines, risk and alerts in one panel.
- **Organised by category, 2 pages each** — every tool can be switched on / off in the inputs and live in the panel.
- **Real release data on MT5** — built-in economic calendar with ACTUAL values within seconds of the release.
- **Calendar Bridge for MT4** — run the MT5 version on the same PC and MT4 gets the actual values too.
- **No auto trading** — the EA never opens a trade on its own; manual helpers need a confirm click.
- **Works on any chart** — FX, gold, indices, crypto.

## 🧠 Data sources

| Platform | Source |
|---|---|
| **MT5** | Built-in economic calendar with ACTUAL values within seconds of the release, plus years of history for the reaction statistics |
| **MT4** | Forex Factory weekly feed (time, impact, forecast, previous — no actual) |
| **MT4 + Calendar Bridge** | Run the MT5 version on the same PC and the MT4 version gets the ACTUAL values, next week's events and the 35-day history automatically |

The Forex Factory feed is downloaded at most once per hour and shared by all charts and terminals (Forex Factory blocks more than 2 requests per 5 minutes).

## 🧰 The tool categories

| Category | Tools |
|---|---|
| **CALENDAR** | Calendar list, countdown, today timeline, week heat grid, currency load, speeches, bank holidays, central bank meetings, event inspector, time zone converter, feed status, MT5 → MT4 bridge |
| **PRE-NEWS** | Blackout window (+ GlobalVariable `NAQ_LOCK_<symbol>` for your EAs), pre-news range box, straddle planner (lines only), expected move from history, ATR / expected move cone, compression, pre-news drift, spreads at past releases, event risk score, checklist, positions at risk |
| **LIVE** | Spike detector, tick speed, velocity, spread, slippage estimate, liquidity vacuum, quote freeze, reaction timer, first candle, jumps, tick pressure, release flash card |
| **SURPRISE** | Surprise meter, z-score, Citi-style surprise index, revisions, beat / miss streak, consensus accuracy, data heatmap, impact direction, macro dashboard (rate, CPI, unemployment, GDP, PMI), rate differential, central bank rates, fade probability, MFE / MAE, event ranking, surprise beta, volatility around news, reaction journal (CSV), releases on the chart |
| **POST** | Fade monitor, continuation, mean reversion, post-news range, volatility decay, second wave, spike Fibonacci, release VWAP, pre-news price line, trailing guide lines |
| **MACRO** | Currency strength, correlation, dollar index, risk on / off, volatility regime, sessions, ADR, COT, movers since release, cross asset, liquidity |
| **WIRE** | RSS headlines, keyword watch, sentiment, chart ticker, currency tags, breaking flash, central bank tone |
| **RISK** | News position size, worst-case risk, margin stress, currency exposure, close assistant, trade panel, straddle placer (OCO), trade manager, account health, daily loss guard |
| **ALERTS** | Pre-news / release / spike / spread alerts, Telegram, screenshots, news lines, countdown beeps, CSV export, chart theme, world clock |

## 🤝 Manual trading helpers (all OFF by default)

- **Trade panel, close assistant and straddle placer** only act on **your** click and need a second confirm click within 4 seconds.
- The **trade manager** only moves stops of existing trades.
- The EA **never opens a trade on its own**.

## 🖥️ Dashboard

- Drag the header to move the panel, **X** closes it to a small pill, click the pill to reopen.
- Turn any tool on / off with the power icon or the **MODULES / ALL TOOLS** tab.
- Hover anything for an explanation (tooltips can be switched off in the inputs).

## 🛠️ Installation

1. Copy the file for your platform:
   - **MT5:** `TL News Arsenal Quant.ex5` → **File → Open Data Folder → MQL5 → Experts**
   - **MT4:** `TL News Arsenal Quant.ex4` → **File → Open Data Folder → MQL4 → Experts**
2. Refresh the Navigator and drag the EA onto any chart (FX, gold, indices, crypto).
3. Tick **"Allow DLL imports"** (only used for the link buttons).
4. Add the WebRequest URLs below under **Tools → Options → Expert Advisors → Allow WebRequest**.

## 📋 Requirements — WebRequest URLs

| URL | Used for |
|---|---|
| `https://nfs.faireconomy.media` | Forex Factory calendar (MT4, or MT5 with source "FF") |
| `https://www.fxstreet.com` | Headline feed (default RSS) |
| `https://investinglive.com` | Second headline feed (optional input) |
| `https://publicreporting.cftc.gov` | COT positioning |
| `https://api.telegram.org` | Telegram alerts |

## ⚠️ Notes

- News trading is high risk — spreads and slippage at releases can be extreme.
- All statistics are historical and no guarantee for the future.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
