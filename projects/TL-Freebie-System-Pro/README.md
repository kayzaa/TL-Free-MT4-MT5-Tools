<div align="center">

# ⚡ TL Freebie System Pro

**Dredding82's Freebie system: Semafor + pivot fail + Stochastic + Heikin Ashi in one EA.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Freebie_System_Pro_fbs_shot_M15.png" alt="TL Freebie System Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT5** | [`TL Freebie System Pro.ex5`](MT5/TL%20Freebie%20System%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **The classic Forex Factory "Freebie System"** by Dredding82 (2011), turned into one MT5 Expert Advisor.
- **One file, the whole template** — every indicator of the original template is calculated and drawn by the EA itself. Nothing else to install.
- **Rule-by-rule checklist** — the panel shows YES / no for every BUY and SELL rule on the last closed candle.
- **Higher-timeframe trend filter** — trade only with the trend of the next timeframe up.
- **"Free trade" management** — half off at 1R and the stop to break even, as in the thread.
- **Signal-only mode** — set *Trading ON* = false and use it as a pure signal / alert tool.

## 📊 Built-in indicators

- **Heiken Ashi candles** (the normal candles are hidden behind them)
- **Stochastic 10, 3, 3** (simple, close/close) in its own window
- **ZZ Semafor dots**, 3 levels (5 / 13 / 34)
- **ZigZag line** (12 / 5 / 3)
- **Fib pivots + mid pivots** — daily on M1–H1, weekly on H4, monthly on D1 ("Myperiod")
- **Daily Range Calculator** — ADR, range used today, expected high / low — in the panel

## 🧠 Strategy rules

The original rules — trade with the trend of a higher timeframe. Everything is checked at **candle close**.

| | BUY | SELL |
|---|---|---|
| **Semafor** | ZZ Semafor dot at the bottom (within 1–3 candles) | Dot at the top |
| **Pivot fail** | Candle touches / pierces a Fib pivot (1–5 pips is fine) and closes back **above** it | Closes back **below** it |
| **Stochastic** | Crossed **up** | Crossed **down** |
| **Heiken Ashi** | Candle closed **green** | Candle closed **red** |
| **Stop loss** | Last low (the semafor dot) + buffer | Last high + buffer |
| **Take profit** | 1:1 – 1:4 risk:reward or the other pivots — "the Daily Range indicator will tell you what pivot to max profits" | Mirror |

**Money management from the thread:**

- Post #1041: risk 2 % of the account, close half the lots at 1:1 and move the stop to break even → "a free trade".
- Post #234: a trailing stop is safer when you leave the position alone.
- Friday: no new trades after the London close.

### How the EA trades it

- **Signal** = all enabled rules are true on the candle that just closed (and were not on the candle before). The trade opens at the start of the next candle.
- **Trend filter** (default): colour of the last *closed* Heiken Ashi candle of the higher timeframe (M1–M5 → H1, M15–H1 → H4, H4 → D1, D1 → W1). Other modes: higher highs / lower lows of the higher timeframe, EMA, or off.
- **SL:** below / above the semafor dot (+2 pips buffer, min. 5 pips).
- **TP** (default "pivot inside the daily range"): the farthest pivot that today's average daily range still allows — at least 1:1, at most 1:4. Other modes: next pivot, fixed R:R, none.
- **At 1R:** 50 % closed, SL to break even + 1 pip.
- **One trade at a time** per chart (magic number).

## 🖥️ Dashboard & chart

- **Status:** position, higher-TF trend, trading state, last signal.
- **THE RULES:** YES / no for BUY and SELL, rule by rule, for the last closed candle.
- **Fib pivots + Daily Range:** all levels, nearest level, ADR bar, expected high / low.
- **Position:** R multiple, SL, TP, partial done, results, and a chart history of the signals.
- **Buttons:** TRADING ON / PAUSED, CLOSE ALL, YOUTUBE, ROBOFOREX, WHATSAPP. Click **MYFXBOOK** to open the original thread; **–** minimises the panel.

## 🛠️ Installation

1. Copy `TL Freebie System Pro.ex5` to `File → Open Data Folder → MQL5 → Experts`.
2. Restart MT5, or right-click **Expert Advisors** in the Navigator → **Refresh**.
3. Drag the EA onto a chart (e.g. EURUSD M15 or H1).
4. Tick **"Allow Algo Trading"** — and **"Allow DLL imports"** only if you want the link buttons to work.
5. Click **Algo Trading** in the toolbar.

Tip: set **Trading ON = false** to use it as a pure signal / alert tool.

## 🙏 Credits

Built after the Forex Factory thread [Price Action Trading with Indicators! The Freebie System](https://www.forexfactory.com/thread/276813-price-action-trading-with-indicators-the-freebie-system) by **Dredding82** (2011).

## ⚠️ Notes

Trading involves high risk and no profit is promised. Test it on a demo account first — as Dredding82 said himself.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
