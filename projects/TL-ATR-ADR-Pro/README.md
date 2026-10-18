<div align="center">

# ⚡ TL ATR ADR Pro

**ATR matrix across every timeframe plus ADR / AWR / AMR, session clock, trade planner and multi-symbol scanner in one dashboard.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Indicator-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_ATR_ADR_Pro_FF_post.png" alt="TL ATR ADR Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL ATR ADR Pro.ex4`](MT4/TL%20ATR%20ADR%20Pro.ex4) |
| **MT5** | [`TL ATR ADR Pro.ex5`](MT5/TL%20ATR%20ADR%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **Today vs ADR at a glance** — an animated ring shows how much of the average daily range is already used, with a clear day status from ROOM TO RUN to EXTREME DAY.
- **ATR matrix on every timeframe** — M1 to W1 (your own list), with candle size in % of ATR, ATR trend, volatility regime and a sparkline.
- **ADR, AWR and AMR** — daily, weekly and monthly ranges with % used, plus a 20-day range history.
- **Volatility clock** — the average H1 range for every hour of the day, with Tokyo / London / New York sessions and the peak hour.
- **ATR risk planner** — stop, target and lot size for your risk %, with optional chart lines. It never places trades.
- **Multi-symbol ADR scanner** — up to 14 symbols sorted by room left; click one to open it.

## 🖥️ Dashboard & chart

| Block | What you get |
|---|---|
| **TODAY vs ADR** | Animated ring with % of ADR used today and the day status (ROOM TO RUN / NORMAL DAY / STRETCHED / ADR HIT / EXTREME DAY). Shows ADR, today's range, range left, ADR high + low target with the distance from price, change from the open, and **PACE** — how fast today moves compared with a normal day at this hour. |
| **DAY MAP** | Price, open and today's range drawn inside the ADR window. |
| **ADR HISTORY** | The last 20 daily ranges plus today live, the ADR line, how often ADR was reached, ADR 5 / 10 / 20 / N, the weekly range (AWR) and the monthly range (AMR) with % used. |
| **ATR MATRIX** | ATR on M1 M5 M15 M30 H1 H4 D1 W1 (your list), the current candle in % of the ATR, ATR trend, volatility regime (LOW / NORMAL / HIGH / EXTREME = rank of the ATR inside its last 100 values) and a 30-bar sparkline. |
| **VOLATILITY CLOCK** | Average H1 range for every hour of the day (last 20 days), the current hour live, Tokyo / London / New York sessions in server time and the peak hour. |
| **ATR RISK PLANNER** | Stop = N × ATR, take profit = R × stop, lot size for your risk %, BUY / SELL levels and optional lines on the chart. Planning only — it never places trades. |
| **ADR SCANNER** | Up to 14 symbols (Market Watch or your own list) sorted by room left. Click a symbol to open it. |

**On the chart:** today's ADR high + low target, the day open and the targets of the last days.

### Panel handling

- Drag the header to move the panel; **X** folds it to a small pill, click the pill to open it again.
- The square button switches between the **compact panel** (today vs ADR + ATR matrix) and the **full dashboard**.
- Hover anything for an explanation (tooltips can be switched off).
- **Auto placement:** if another trader.lifestyle panel is already on the chart, this panel moves to the nearest free spot. Not enough room for the full dashboard → it switches to the compact panel; no room at all → it folds to the pill, and it opens again by itself once there is room. As soon as you move or open it yourself, your choice wins.
- Position, mode and planner settings are remembered per chart.

## 🧠 How it calculates (100 % transparent)

- **True range** = max(high, previous close) − min(low, previous close).
- **ATR** = average true range of the last N **closed** candles. Methods: SMA (MetaTrader standard, identical to the built-in ATR), Wilder / RMA (TradingView standard) or EMA.
- **ADR** = average (high − low) of the last N completed days. Saturday / Sunday candles are skipped by default, because some brokers print tiny Sunday candles.
- **ADR high target** = today's low + ADR. **ADR low target** = today's high − ADR.

## 🔔 Alerts

- % of ADR used (default 80 % and 100 %, each once per day).
- Volatility spike: chart candle range ≥ 2 × ATR.
- Delivered as popup, sound, push notification or e-mail.

## 🔌 Buffers (for EAs via iCustom)

| Buffer | Value |
|---|---|
| 0 | ADR (price units) |
| 1 | ADR high target |
| 2 | ADR low target |
| 3 | ADR used % |
| 4 | ATR of the chart timeframe |

Buffers 0–3 use only the days **before** the bar's day, plus that day's high / low up to the bar itself.

## 🛠️ Installation

1. In MetaTrader open **File → Open Data Folder**.
2. **MT4:** copy `TL ATR ADR Pro.ex4` into `MQL4 → Indicators`. **MT5:** copy `TL ATR ADR Pro.ex5` into `MQL5 → Indicators`.
3. Refresh the Navigator and drag the indicator onto any chart.
4. Enable **"Allow DLL imports"** only if you want the panel's link buttons (YouTube / WhatsApp / RoboForex / Forex Factory) to work.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
