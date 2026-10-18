<div align="center">

# ⚡ TL Real Time Price Analyzer Pro

**TheRumpledOne's Real Time Price Analyzer rewritten: 16 levels of the forming bar and how often past bars touched them.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Indicator-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_RealTimePriceAnalyzerPro_screenshot.png" alt="TL Real Time Price Analyzer Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Real Time Price Analyzer Pro.ex4`](MT4/TL%20Real%20Time%20Price%20Analyzer%20Pro.ex4) |
| **MT5** | [`TL Real Time Price Analyzer Pro.ex5`](MT5/TL%20Real%20Time%20Price%20Analyzer%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **Up to 16 levels for the forming bar** — pivots, mid levels, previous bar levels, fib % and fixed prices, on any analysis timeframe.
- **Historical odds per level** — how often past bars touched or closed beyond the same levels of their own bar, with sample size and 95 % margin of error.
- **Live price position** — the zone price is in, distance in pips and % of the average range, range used and a countdown to the close.
- **Level ladder** — every level sorted by price with touch % and close-beyond %.
- **EA-ready buffers** — including a hidden buffers-only mode that draws nothing.
- **Independent rewrite** — a long list of bugs of the 2017 original fixed.

## 🧠 How it works

For the bar that is forming right now (analysis timeframe = chart, H1, H4, D1, W1 …) the indicator builds up to **16 levels** from the previous bar:

- Classic pivots **PP, R1–R6, S1–S6** and the mid levels between them
- Previous bar **open / high / mid / low / close / body top / body bottom**
- **Fib %** of the previous range
- The **open** of the forming bar
- **Fixed prices**

Then it answers two questions: **where is price right now** — and **how often did the past N bars touch or close beyond the same levels of their own bar?**

### Sample modes

| Mode | Which past bars count |
|---|---|
| **ALL BARS** | Every past bar (like the original) |
| **SAME OPEN ZONE** | Only past bars that opened between the same two levels as the forming bar — fewer bars, closer situations |

## 🖥️ Dashboard & chart

| Block | What it shows |
|---|---|
| **PRICE POSITION** | Bid, the zone it is in (nearest level below → above), a zone gauge, distance in pips and in % of the average bar range, range used so far, countdown to the close |
| **HISTORICAL ODDS** | For the two nearest levels above and below: HIGH > level (touch), CLOSE > level, CLOSE inside the current zone, CLOSE < level, LOW < level. **HIT** = the forming bar already did it; the close row then shows how often a touch turned into a close beyond. **n** = sample size, **+/−** = 95 % margin of error |
| **LEVEL LADDER** | Every level sorted by price: price, pips away, touch %, close-beyond % (hover: held after a touch) |
| **CONTROLS** | Analysis bar (CHART / H1 / H4 / D1 / W1), sample (ALL BARS / SAME OPEN ZONE), number of bars, lines on/off |

The panel closes to a pill (**X**), reopens with one click, can be dragged anywhere, moves out of the way of other trader.lifestyle panels and keeps its place per chart. Hover any row for an explanation.

**On the chart:** level lines of the forming bar (nearest levels thicker, touched levels magenta) with labels like `R1 1.08423  T 35%  C 18%`. Optional: the levels of the previous N bars.

## ⚙️ Key inputs

| Input | What it does |
|---|---|
| Analysis bar timeframe | Current = chart timeframe; D1 = classic daily pivots |
| Number of past bars | 10 – 5000 (limited by the loaded history) |
| Skip the newest N bars | 1 = closed bars only (default); 0 = include the forming bar like the original |
| D1: ignore Sunday bars | Monday levels from Friday; switched off automatically for 7-day markets (crypto) |
| Level 1–16 + value | Value = offset in pips for pivots / bar levels, % for "Previous bar fib %", price for "Fixed price" (a fixed price of 0 = not used). Pips: 5/3-digit FX = 10 points, gold = 0.10, everything else = 1 point |
| Alerts | Price crosses a level (popup / sound / push / mail), once per level, direction and bar |

## 🔌 Buffers (for EAs via iCustom, newest bar)

| Buffer | Value |
|---|---|
| 0 | Level above price |
| 1 | Level below price |
| 2 | Above: touch % |
| 3 | Above: close beyond % |
| 4 | Below: touch % |
| 5 | Below: close beyond % |
| 6 | Close inside zone % |
| 7 | Sample size |

- Input **"Draw on the chart" = false** gives a hidden, buffers-only copy for your EA — it draws nothing and never touches the objects / panel choices of a visible copy.
- A second **visible** copy on the same chart needs its own "instance id" (1, 2 …).
- No sample (n = 0) → buffers 2–6 are `EMPTY_VALUE`, never a fake 0 %.

## 🔧 Fixed compared with the original (TRO, 2017)

- Crash / garbage when price was above the highest level, below the lowest level or between the two lowest levels (array index out of range).
- The "LOW LT …" row counted a different level than its label showed.
- Level "R4R6" never worked (it is the R3–R4 mid level).
- The forming bar was counted in its own statistics.
- Levels that use the forming bar's own high / low / close (always true or never true in the statistics) and CURRPRICE removed.
- Bars that do not exist in the history were counted as samples.
- Broker Sunday bars distorted Monday's daily pivots.
- Prices were shown with one digit less on 5 / 3-digit symbols.
- Pips for gold, indices and crypto.
- A "FIXEDPRICE" slot left at 0 created a level at 0.00.
- Two copies on one chart deleted each other's objects (tag 1 vs 10).
- Objects were left on the chart after removing the indicator.
- The layout broke in the lower corners and with bigger fonts.

## 🛠️ Installation

1. In MetaTrader open **File → Open Data Folder**.
2. **MT4:** copy `TL Real Time Price Analyzer Pro.ex4` into `MQL4 → Indicators`. **MT5:** copy `TL Real Time Price Analyzer Pro.ex5` into `MQL5 → Indicators`.
3. Restart the terminal or right-click **Refresh** in the Navigator, then drag the indicator onto a chart.
4. No DLL needed.

## ⚠️ Notes

- The statistics describe the past — they are no promise for the future.
- Not financial advice.

## 🙏 Credits

Idea: **TheRumpledOne**'s "Real Time Price Analyzer" (2017). This is an independent rewrite with the bugs of the original fixed.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
