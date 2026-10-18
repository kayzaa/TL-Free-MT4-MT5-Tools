<div align="center">

# ⚡ TL Bigger TF Candles Pro

**Draws higher-timeframe candles (with weekday labels) directly on your lower-timeframe chart.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Indicator-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_BiggerTFCandlesPro_screenshot.png" alt="TL Bigger TF Candles Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT5** | [`TL Bigger TF Candles Pro.ex5`](MT5/TL%20Bigger%20TF%20Candles%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **Higher-timeframe candles on your chart** — body box plus upper and lower wick, drawn right over your price bars.
- **Two layers in one indicator** — e.g. the 10-minute candle with the 2-minute candles inside it.
- **Any MT5 timeframe** can be picked for both layers.
- **Smart labels** — time for intraday, weekday for D1, date for W1/MN1 — plus the range in pips or price distance.
- **Countdown** to the close of the current big candle.
- **Hover any box** to see O / H / L / C and the range of that candle.

## 🧠 How it works

- The **big candle** layer (default **M10**) is drawn as a filled box behind the price bars.
- The **inner candle** layer (default **M2**) is drawn as an outline box on top.
- Each candle shows its body as a box and its wicks as lines, coloured bull / bear.
- Need 3 or 4 timeframes? Load the indicator a second time with other timeframes. Set a different **"Instance tag"** only if both copies use the same timeframes.

## ⚙️ Key inputs

| Input | What it does |
|---|---|
| Big candle timeframe | Outer layer, filled box behind the price bars (default M10). |
| Inner candle timeframe | Inner layer, outline box drawn on top (default M2). |
| Colors / style | Bull and bear body and wick colors, filled or outline, line width. |
| Label | Auto (time for intraday, weekday for D1, date for W1/MN1), Weekday, Time or Weekday+Time. |
| Range in label | Pips for forex, price distance for gold / indices. |
| Countdown | Time left until the current big candle closes. |
| Max candles per layer | How many candles are drawn per layer (default 150). |
| Instance tag | Lets two copies with the same timeframes run on one chart. |
| Show link buttons | Set to `false` to hide the link buttons. |

## 🛠️ Installation

1. In MT5 open `File → Open Data Folder → MQL5 → Indicators` and copy `TL Bigger TF Candles Pro.ex5` there.
2. In the Navigator right-click **Indicators → Refresh**, then drag the indicator onto a chart.
3. Put the chart on a **lower timeframe than both layers** (e.g. an M1 chart for M10 + M2).
4. Optional: tick **Allow DLL imports** in the Dependencies tab only if you want the link buttons (YouTube / RoboForex / WhatsApp / Forex Factory) to open your browser — the indicator itself works without it.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
