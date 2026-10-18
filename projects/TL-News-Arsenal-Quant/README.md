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

## Overview

NO AUTO TRADING. Every tool can be switched on / off in the inputs and live in the panel (power icon or MODULES / ALL TOOLS tab).

## Install

- MT5: copy "TL News Arsenal Quant.ex5" to  MQL5\Experts\
- MT4: copy "TL News Arsenal Quant.ex4" to  MQL4\Experts\ Refresh the Navigator, drag the EA on any chart (FX, gold, indices, crypto).
- Tick "Allow DLL imports" (only used for the link buttons).

## Webrequest (Tools > Options > Expert Advisors > Allow WebRequest)

<https://nfs.faireconomy.media>      Forex Factory calendar (MT4, or MT5 source "FF") <https://www.fxstreet.com>           headline feed (default RSS) <https://investinglive.com>          second headline feed (optional input) <https://publicreporting.cftc.gov>   COT positioning <https://api.telegram.org>           Telegram alerts

## Data Sources

MT5: built-in economic calendar with ACTUAL values within seconds of the release, years of history for the reaction statistics. MT4: Forex Factory weekly feed (time, impact, forecast, previous - no actual). CALENDAR BRIDGE: run the MT5 version on the same PC and the MT4 version gets the ACTUAL values, next week's events and the 35 day history automatically. The Forex Factory feed is downloaded max. once per hour and shared by all charts and terminals (Forex Factory blocks more than 2 requests per 5 minutes).

## The 10 Categories (each with 2 pages)

CALENDAR   calendar list, countdown, today timeline, week heat grid, currency load, speeches, bank holidays, central bank meetings, event inspector, time zone converter, feed status, MT5->MT4 bridge PRE-NEWS   blackout window (+ GlobalVariable NAQ_LOCK_<symbol> for your EAs), pre-news range box, straddle planner (lines only), expected move from history, ATR / expected move cone, compression, pre-news drift, spreads at past releases, event risk score, checklist, positions at risk LIVE       spike detector, tick speed, velocity, spread, slippage estimate, liquidity vacuum, quote freeze, reaction timer, first candle, jumps, tick pressure, release flash card SURPRISE   surprise meter, z-score, Citi style surprise index, revisions, beat / miss streak, consensus accuracy, data heatmap, impact direction, macro dashboard (rate, CPI, unemployment, GDP, PMI), rate differential, central bank rates fade probability, MFE / MAE, event ranking, surprise beta, volatility around news, reaction journal (CSV), releases on the chart POST       fade monitor, continuation, mean reversion, post-news range, volatility decay, second wave, spike Fibonacci, release VWAP, pre-news price line, trailing guide lines MACRO      currency strength, correlation, dollar index, risk on/off, volatility regime, sessions, ADR, COT, movers since release, cross asset, liquidity WIRE       RSS headlines, keyword watch, sentiment, chart ticker, currency tags, breaking flash, central bank tone RISK       news position size, worst case risk, margin stress, currency exposure, close assistant, trade panel, straddle placer (OCO), trade manager, account health, daily loss guard ALERTS     pre-news / release / spike / spread alerts, Telegram, screenshots, news lines, countdown beeps, CSV export, chart theme, world clock

## Manual Trading Helpers (all Off by default)

Trade panel, close assistant and straddle placer only act on YOUR click and need a second confirm click within 4 seconds. The trade manager only moves stops of existing trades. The EA never opens a trade on its own.

## Panel

Drag the header to move it, X closes it to a small pill, click the pill to open. Hover anything for an explanation (tooltips can be switched off in the inputs).

Disclaimer: news trading is high risk. Spreads and slippage at releases can be extreme. All statistics are historical and no guarantee for the future.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
