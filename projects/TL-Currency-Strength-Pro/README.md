<div align="center">

# ⚡ TL Currency Strength Pro

**Full-chart currency strength suite: strength, rate of change and divergence across all majors.**

![version](https://img.shields.io/badge/version-v1.01-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Indicator-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_CurrencyStrengthPro_Screenshot.png" alt="TL Currency Strength Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Currency Strength Pro.ex4`](MT4/TL%20Currency%20Strength%20Pro.ex4) |
| **MT5** | [`TL Currency Strength Pro.ex5`](MT5/TL%20Currency%20Strength%20Pro.ex5) |

> Compiled build only — source code is not published.

## The Idea (flotsom)

Knowing which currency is strong or weak is not enough - a strong currency can already be losing strength fast. The edge is the currency GAINING strength the fastest against the one LOSING it the fastest. This indicator shows exactly that, plus everything around it.

## How Strength Is Calculated (fully transparent)

- 8 currencies (EUR GBP AUD NZD USD CAD CHF JPY), all 28 pairs.
- Every pair: where is the close inside its high / low range of the last N bars (default 120)? 0 % = at the low, 100 % = at the high. The base currency gets that value, the quote currency the rest (100 % - value).
- Currency strength = 10 x average over its 7 pairs  ->  0 (weak) ... 10 (strong), SMA-smoothed.
- Rate of change = strength now - strength 5 bars ago (SMA-smoothed). 1 bar of the change graph = 0.20 strength points (input), max 10 bars.
- Diverging pair = base and quote change in opposite directions and BOTH reach change level 5+. BUY when the base currency is the one gaining strength, SELL otherwise. TREND = the strength order already agrees, EARLY = the move runs against the current strength order (the early turn flotsom was looking for, his point "B").

## Full Chart Suite (default) - covers the whole chart, everything animated

- Header: timeframe tabs M5 ... D1 (click = recalculate the whole suite on that timeframe), live clock, buttons, COMPACT switch, X.
- Currency strength: 8 segmented bars with live values, change level and today's %.
- Strength lines: last 100 bars of all 8 currencies, signal ticks, hover any bar for the values.
- Strength radar: strength shape + rate-of-change spokes, radar sweep.
- Best trade now: fastest diverging pair, BUY / SELL, SIGNAL / WATCH, TREND / EARLY, divergence gauge, strongest classic trends (biggest strength gaps).
- Rate of change: who gains / loses strength the fastest, signal level marked.
- Signals: pairs diverging now (or the closest candidates as WATCH) + signal log of the history.
- Pair matrix 8 x 8: strength gap of every combination, diverging pairs pulse.
- Multi-timeframe matrix (M15 H1 H4 D1 by default) with average ranking.
- Today & sessions: % change of every currency since the D1 open, Sydney / Tokyo / London / New York session map with a live time marker.
- Ticker tape with all 28 pairs, bid and today's %.
- Click a currency = focus it in all graphs. Click a pair (hero, signals, log, matrix, trends) = open that chart (input: this chart / new chart / off).
- Hover anything for an explanation.
- X closes the suite to a small pill (drag it anywhere), click the pill to open it again. While the suite is open the chart does not scroll underneath; everything is restored on close.

## Compact Panel (switch with the Compact button or input "Display: full chart suite or compact panel")

- Movable panel with strength, rate of change, diverging pairs, lines and MTF matrix.

## Alerts

Popup / sound / push / e-mail when a pair starts to diverge (cool-down per pair, default 60 min).

## Symbols

Broker prefix / suffix are detected automatically (e.g. EURUSD.r, mEURUSD). If your broker uses something unusual, set the prefix / suffix inputs. Missing pairs are skipped.

## Install

- MT5: copy MT5\TL Currency Strength Pro.ex5 to  File > Open Data Folder > MQL5\Indicators
- MT4: copy MT4\TL Currency Strength Pro.ex4 to  File > Open Data Folder > MQL4\Indicators Refresh the Navigator, drag the indicator on any chart. The first load of all 28 pairs can take a few seconds. For the YouTube / RoboForex / WhatsApp / Forex Factory buttons tick "Allow DLL imports".

- Questions / more free tools: <https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4>

- CHANGES v1.01
- Symbol detection rewritten: scans ALL symbols of the server and picks the prefix / suffix group that covers the most of the 28 pairs (on a tie the group of the chart, e.g. XAUUSDc -> "c" pairs). Missing pairs are taken from another symbol group of the same broker (prices are identical).
- Waits until the history of all pairs is loaded before the first result (no jumping lines).
- Data check: with fewer than 21 pairs or fewer than 5 pairs per currency the suite shows "INCOMPLETE DATA" and pauses signals and alerts instead of showing distorted strength.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
