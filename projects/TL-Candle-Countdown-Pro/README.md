<div align="center">

# ⚡ TL Candle Countdown Pro

**Candle countdown for any timeframe list — including custom M4 / M7 / S30 — with trend state per candle.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Indicator-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Candle_Countdown_Pro_ccp_7_XAU_M1.png" alt="TL Candle Countdown Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT5** | [`TL Candle Countdown Pro.ex5`](MT5/TL%20Candle%20Countdown%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **A whole list of timers at once** — count down M1, M4, M15, H1, H4, D1 … side by side, on any chart timeframe (e.g. the M4 candle on an M1 chart).
- **Custom timeframes MT5 doesn't have** — M7, M45, H5, D2, even S30 (seconds), or just a number (`7` = 7 minutes).
- **Trend state per candle** — mini candle, arrow and pips since the open for every running candle, plus a BULL / BEAR BIAS summary.
- **Focus timer** — big countdown with a progress ring and a live tag right next to the current candle.
- **Market-aware** — timers pause while the market is closed and show when it reopens.
- **EA-ready buffers** for your own automation.

## 🧠 How it works

**Timer list.** Enter the timeframes in **Timers: list**, separated by commas, e.g. `M1,M4,M15,H1,H4,D1`. Every MT5 timeframe works (M1 M2 M3 M4 M5 M6 M10 M12 M15 M20 M30 H1 H2 H3 H4 H6 H8 H12 D1 W1 MN), plus custom lengths.

**Trend per candle.** Each running candle in each timeframe gets a mini candle, an arrow and the pips since its open — green = bullish, red = bearish. A **BULL / BEAR BIAS** summary covers all timers, the focus timer shows a direction pill, and the chart tag turns green / red too.

**Focus timer.** Set it with **Timers: focus timer** or simply click a row in the panel. You get a big countdown with a progress ring, context such as *"M1 candle 3 of 4 in this M4"*, and a live tag next to the current candle on the chart. The final seconds pulse red (**Timers: final seconds highlighted**).

**Market open / closed.** Uses the broker's sessions. All times are server time, exactly like the chart.

**How custom timeframes are aligned.** Intraday timers start at midnight server time, like MT5's own bars. A length that does not divide the day evenly (e.g. M7) ends its last candle at midnight. W1 starts on Sunday, MN on the 1st of the month.

**Alerts.** Popup / sound / push / e-mail before the close — e.g. for `M4,H1`, 10 seconds before the close, or `0` = when the new candle opens. Optional tick sound in the final seconds.

## 🖥️ Dashboard & chart

- Click **X** to close the panel to a small pill that keeps counting; click the pill to reopen.
- Drag the header to move the panel.
- Position, focus timer and open / closed state survive timeframe changes.

## 🔌 Buffers for EAs

| Buffer | Value |
|---|---|
| 0 | Focus candle — seconds left |
| 1 | Chart candle — seconds left |
| 2 | Focus candle direction (+1 bullish / -1 bearish / 0 flat) |

## 🛠️ Installation

1. In MT5 open `File → Open Data Folder → MQL5 → Indicators` and copy `TL Candle Countdown Pro.ex5` there.
2. Refresh the Navigator and drag the indicator onto a chart.
3. Optional: tick **Allow DLL imports** — only needed for the YouTube / RoboForex / WhatsApp / Forex Factory link buttons.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
