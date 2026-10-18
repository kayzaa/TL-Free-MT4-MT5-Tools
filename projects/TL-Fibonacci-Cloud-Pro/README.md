<div align="center">

# ⚡ TL Fibonacci Cloud Pro

**Multi-timeframe Fibonacci cloud (port of TrendX_'s TradingView script) for MT4 and MT5.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Indicator-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL%20Fibonacci%20Cloud%20Pro%20-%20XAUUSD%20D1%20(W1%20cloud).png" alt="TL Fibonacci Cloud Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Fibonacci Cloud Pro.ex4`](MT4/TL%20Fibonacci%20Cloud%20Pro.ex4) |
| **MT5** | [`TL Fibonacci Cloud Pro.ex5`](MT5/TL%20Fibonacci%20Cloud%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **Faithful port of TrendX_'s TradingView Fibonacci cloud** — same golden-zone math, same trailing bands, same gradient look.
- **True multi-timeframe** — any cloud timeframe on any lower chart timeframe (default Weekly, like the original).
- **Two modes** — *TradingView 1:1* for an exact match, or *No repaint* using only closed cloud candles.
- **Animated dashboard** with golden-zone gauge, MTF matrix (M15 → MN) and consensus bar.
- **Alerts + EA buffers** — trend changes, cloud entries, and six buffers for iCustom.

## 🧠 How it works

**Golden zone.** Takes the highest high / lowest low of the last 50 candles of the cloud timeframe and builds the Fibonacci golden zone **0.382 – 0.618** of that range.

**Trailing bands → the cloud.** Two trailing bands, one on each golden-zone level, move only with the trend and flip when price closes through them — exactly like `createCloud_Func` in the Pine script. The space between them is the cloud:

| Colour | Meaning |
|---|---|
| Teal | Bullish cloud |
| Maroon | Bearish cloud |

The cloud fades when price is close to the zone and turns solid when price is far away (same `color.from_gradient` logic as on TradingView).

**Signals.**
- Circle **below** the bar = **UPTREND** (the 0.382 band crosses above the 0.618 band).
- Circle **above** the bar = **DOWNTREND** (it crosses below).

**Multi-timeframe styles.**
- **TradingView 1:1** — matches the TV script on historical bars: the value of a weekly candle appears on the last chart bar of that week (weekly steps). The forming week is live on the current bar and can change until the week closes — same as on TradingView.
- **No repaint** — uses only **closed** cloud candles; the new value starts one bar later.

**Fibonacci levels.** Like the TV Fibonacci tool: yellow lines at 0 / 0.382 / 0.5 / 0.618 / 1 (0 = range high, 1 = range low) with prices.

**Alerts.** Trend change on candle close (default) or live, plus an optional alert when price enters the cloud. Popup / sound / push / e-mail.

## 🖥️ Dashboard & chart

- **TradingView dark look** of the original (background `#131722`, white candles, no grid, grey scale text). Your own chart colours are saved and restored when you remove the indicator — set **TradingView dark theme** = `false` to keep your colours.
- **Animated dashboard** (hover any block for an explanation):
  - cloud trend + since when; price above / inside / below the cloud with the distance in pips
  - golden-zone gauge with all levels and distances
  - MTF matrix: the same cloud on M15, H1, H4, D1, W1 and MN + consensus bar
  - last signal, number of signals on the chart, alert settings
  - click **X** to close it to a small pill, click the pill to reopen, drag the header to move it

## 🔌 Buffers for EAs

| Buffer | Value |
|---|---|
| 0 | Cloud line 0.618 |
| 1 | Cloud line 0.382 |
| 2 | Uptrend signal |
| 3 | Downtrend signal |
| 4 | Trend (+1 / -1) |
| 5 | Cloud colour (+1 bull / -1 bear) |

`EMPTY_VALUE` = no value.

## 🔧 Why the previously posted MT4 version showed no cloud

- Both cloud buffers were plotted with colour `clrNONE` (invisible) and nothing filled the space between them.
- The calculation restarted the stateful bands from scratch for every bar with only ~100 candles of history, and the higher-timeframe bars were mapped one chart bar at a time — so the lines did not match the TradingView script anyway.
- **This version** runs the bands once over the whole cloud-timeframe history (+ 300 warm-up candles) and draws the cloud on a transparent canvas behind the candles.

## 🛠️ Installation

1. Open `File → Open Data Folder`.
   - **MT4:** copy `MT4\TL Fibonacci Cloud Pro.ex4` into `MQL4 → Indicators`.
   - **MT5:** copy `MT5\TL Fibonacci Cloud Pro.ex5` into `MQL5 → Indicators`.
2. Refresh the Navigator and drag the indicator onto a chart.
3. The first start may take a few seconds until the Weekly history is loaded.
4. Optional: tick **Allow DLL imports** for the YouTube / RoboForex / WhatsApp / Forex Factory buttons.

## ⚠️ Notes

- In *TradingView 1:1* style the current (forming) cloud candle is live and can change until it closes. Use *No repaint* if you only want closed values.

## 🙏 Credits

- Original TradingView script by **TrendX_** — this is an MT4 / MT5 port.

## 🖼️ More screenshots

<img src="screenshots/TL%20Fibonacci%20Cloud%20Pro%20-%20XAUUSD%20H4%20(D1%20cloud).png" width="49%">

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
