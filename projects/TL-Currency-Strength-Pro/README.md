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

## ✨ Highlights

- **8 currencies, all 28 pairs** — EUR, GBP, AUD, NZD, USD, CAD, CHF and JPY in one view.
- **Strength *and* momentum** — see not just who is strong, but who is gaining or losing strength the fastest.
- **Diverging-pair finder** — spots pairs where one currency rises while the other falls, tagged TREND or EARLY.
- **Full-chart animated suite** — radar, strength lines, 8×8 pair matrix, multi-timeframe matrix, sessions map and ticker tape.
- **Click to act** — click a currency to focus it everywhere, click a pair to open its chart.
- **Alerts** — popup, sound, push or e-mail when a pair starts to diverge.

## 🧠 How it works

### The idea (flotsom)

Knowing which currency is strong or weak is not enough — a strong currency can already be losing strength fast. What matters is the currency **gaining** strength the fastest against the one **losing** it the fastest. This indicator shows exactly that, plus everything around it.

### How strength is calculated (fully transparent)

- **Range position:** for every pair, where is the close inside its high / low range of the last N bars (default 120)? 0 % = at the low, 100 % = at the high. The base currency gets that value, the quote currency the rest (100 % − value).
- **Currency strength:** 10 × the average over its 7 pairs → **0 (weak) … 10 (strong)**, SMA-smoothed.
- **Rate of change:** strength now − strength 5 bars ago (SMA-smoothed). One bar of the change graph = 0.20 strength points (input), max 10 bars.
- **Diverging pair:** base and quote change in opposite directions and **both** reach change level 5+.
  - **BUY** when the base currency is the one gaining strength, **SELL** otherwise.
  - **TREND** = the strength order already agrees.
  - **EARLY** = the move runs against the current strength order — the early turn flotsom was looking for (his point "B").

## 🖥️ Dashboard & chart

### Full chart suite (default) — covers the whole chart, everything animated

| Block | What it shows |
|---|---|
| **Header** | Timeframe tabs M5 … D1 (click = recalculate the whole suite on that timeframe), live clock, buttons, COMPACT switch, X |
| **Currency strength** | 8 segmented bars with live values, change level and today's % |
| **Strength lines** | Last 100 bars of all 8 currencies, signal ticks; hover any bar for the values |
| **Strength radar** | Strength shape + rate-of-change spokes, radar sweep |
| **Best trade now** | Fastest diverging pair, BUY / SELL, SIGNAL / WATCH, TREND / EARLY, divergence gauge, strongest classic trends (biggest strength gaps) |
| **Rate of change** | Who gains / loses strength the fastest, signal level marked |
| **Signals** | Pairs diverging now (or the closest candidates as WATCH) + a signal log |
| **Pair matrix 8 × 8** | Strength gap of every combination; diverging pairs pulse |
| **Multi-timeframe matrix** | M15, H1, H4, D1 by default, with average ranking |
| **Today & sessions** | % change of every currency since the D1 open, Sydney / Tokyo / London / New York session map with a live time marker |
| **Ticker tape** | All 28 pairs with bid and today's % |

**Interaction**

- Click a currency to focus it in all graphs.
- Click a pair (hero, signals, log, matrix, trends) to open that chart — input: this chart / new chart / off.
- Hover anything for an explanation.
- **X** closes the suite to a small pill (drag it anywhere); click the pill to open it again. While the suite is open the chart does not scroll underneath, and everything is restored on close.

### Compact panel

Switch with the **Compact** button or the input *"Display: full chart suite or compact panel"*: a movable panel with strength, rate of change, diverging pairs, lines and the MTF matrix.

## ⚙️ Key inputs

| Input | What it does |
|---|---|
| Range length (N bars) | Lookback for the high / low range position (default 120) |
| Change graph step | Strength points per bar of the change graph (default 0.20) |
| Display | Full chart suite or compact panel |
| Pair click | Open the pair on this chart / a new chart / off |
| Alerts | Popup / sound / push / e-mail when a pair starts to diverge, with a cool-down per pair (default 60 min) |
| Prefix / suffix | Manual symbol naming if your broker uses something unusual |

## 🔤 Symbols

Broker prefixes and suffixes are detected automatically (e.g. `EURUSD.r`, `mEURUSD`). If your broker uses something unusual, set the prefix / suffix inputs. Missing pairs are skipped.

## 🆕 What's new in v1.01

- **Rewritten symbol detection:** scans all symbols on the server and picks the prefix / suffix group that covers most of the 28 pairs (on a tie, the group of the chart — e.g. `XAUUSDc` → "c" pairs). Missing pairs are taken from another symbol group of the same broker (prices are identical).
- **No jumping lines:** waits until the history of all pairs is loaded before the first result.
- **Data check:** with fewer than 21 pairs, or fewer than 5 pairs per currency, the suite shows **"INCOMPLETE DATA"** and pauses signals and alerts instead of showing distorted strength.

## 🛠️ Installation

1. Choose **File → Open Data Folder**.
2. Copy the file for your platform:
   - **MT4:** `TL Currency Strength Pro.ex4` → **MQL4 → Indicators**
   - **MT5:** `TL Currency Strength Pro.ex5` → **MQL5 → Indicators**
3. Refresh the Navigator and drag the indicator onto any chart. The first load of all 28 pairs can take a few seconds.
4. Tick **Allow DLL imports** only if you want the YouTube / RoboForex / WhatsApp / Forex Factory buttons to work.

## 🙏 Credits

- Concept: **flotsom** — strength change and divergence between currencies (his point "B" for the early turn).

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
