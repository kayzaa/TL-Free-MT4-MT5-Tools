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

## What It Shows

- TODAY vs ADR: animated ring with % of the ADR used today, day status (ROOM TO RUN / NORMAL DAY / STRETCHED / ADR HIT / EXTREME DAY), ADR, today's range, range left, ADR high + low target with the distance from price, change from the open and the PACE (how fast today moves compared with a normal day at this hour).
- DAY MAP: price, open and today's range inside the ADR window.
- ADR HISTORY: last 20 daily ranges + today live, ADR line, how often ADR was reached, ADR 5 / 10 / 20 / N, weekly range (AWR) and monthly range (AMR) with % used.
- ATR MATRIX: ATR on M1 M5 M15 M30 H1 H4 D1 W1 (your list), current candle in % of the ATR, ATR trend, volatility regime (LOW / NORMAL / HIGH / EXTREME = rank of the ATR inside its last 100 values) and a 30-bar sparkline.
- VOLATILITY CLOCK: average H1 range for every hour of the day (last 20 days), current hour live, Tokyo / London / New York sessions in server time, peak hour.
- ATR RISK PLANNER: stop = N x ATR, take profit = R x stop, lot size for your risk %, BUY / SELL levels, optional lines on the chart. It never places trades.
- ADR SCANNER: up to 14 symbols (Market Watch or your list) sorted by room left. Click a symbol to open it.
- ON THE CHART: today's ADR high + low target, day open, the targets of the last days.

## How It Calculates (100 % transparent)

- True range = max(high, previous close) - min(low, previous close).
- ATR = average of the true range of the last N CLOSED candles. Methods: SMA (MetaTrader standard, identical to the built-in ATR), Wilder / RMA (TradingView standard), EMA.
- ADR = average (high - low) of the last N completed days. Saturday / Sunday candles are skipped by default (some brokers have tiny Sunday candles).
- ADR high target = today's low + ADR.  ADR low target = today's high - ADR.

## Panel

- Drag the header to move it, X folds it to a small pill, click the pill to open it again.
- Square button = compact panel (today vs ADR + ATR matrix) / full dashboard.
- Hover anything for an explanation (tooltips can be switched off).
- AUTO PLACEMENT: if another trader.lifestyle panel is already on the chart, this panel moves to the nearest free spot. Not enough room for the full dashboard -> it switches to the compact panel, no room at all -> it folds to the pill, and it opens again by itself when room is free. Once you move or open it yourself, your choice wins.
- Position, mode and planner settings are remembered per chart.

## Alerts

- % of ADR used (default 80 and 100 %, once per day each).
- Volatility spike: chart candle range >= 2 x ATR.
- Popup / sound / push / e-mail.

## 0 = ADR (price units) | 1 = ADR high target | 2 = ADR low target | 3 = ADR used % |

4 = ATR of the chart timeframe. Buffers 0-3 use only the days BEFORE the bar's day and the day's high / low up to that bar.

## Install

- MT5: copy "TL ATR ADR Pro.ex5" to File > Open Data Folder > MQL5\Indicators
- MT4: copy "TL ATR ADR Pro.ex4" to File > Open Data Folder > MQL4\Indicators Refresh the Navigator and drag it on any chart.
- "Allow DLL imports" is only needed for the link buttons (YouTube / WhatsApp / RoboForex / FF).

- More free tools: <https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4>

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
