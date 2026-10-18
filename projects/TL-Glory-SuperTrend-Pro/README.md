<div align="center">

# ⚡ TL Glory SuperTrend Pro

**bush01's SuperTrend break EA — stop trails on the ATR line, optional MACD and RSI filters.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Glory_SuperTrend_Pro_panel.png" alt="TL Glory SuperTrend Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT5** | [`TL Glory SuperTrend Pro.ex5`](MT5/TL%20Glory%20SuperTrend%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **SuperTrend break entries** — buy or sell when a candle closes through the ATR line.
- **Stop that rides the line** — SL starts on the ATR line and trails it every candle, only in the profit direction.
- **Flexible exits** — no TP, TP in points, a multiple of risk or a multiple of ATR, plus close (or reverse) on the opposite signal.
- **Optional MACD + RSI confirmations** — off by default, with several modes each and a "confirm bars" window.
- **Template built in** — SuperTrend line, MACD and RSI windows, signal arrows and markers drawn by the EA itself.
- **Runs in the Strategy Tester** — headless and visual mode.

## 🧠 Strategy rules

| | Condition |
|---|---|
| **BUY** | A candle closes above the red ATR line (the line turns blue) |
| **SELL** | A candle closes below the blue ATR line (the line turns red) |
| **Stop loss** | On the ATR line at entry, then trailed on the line every candle (profit direction only); optional extra buffer in points |
| **Take profit** | None (default), points, X × risk, or X × ATR |
| **Opposite signal** | Closes the trade (default on), optionally stop & reverse |

### Optional confirmations (default OFF, as requested in post #81,074)

- **MACD:** above / below its signal line, above / below zero, or rising / falling.
- **RSI:** above / below 50, not overbought / oversold, or **SCALP** mode (buy only after oversold, sell only after overbought within X bars).
- The filters may confirm up to X candles after the break (**confirm bars**).

### What was asked — and what was fixed

The request in the thread: PZ_SuperTrend template (ATR period 14, multiplier 3.0), MACD (12, 26, 9) and RSI (14) with 70 / 30 — *"open trade order once the ATR is broken on either side"*, a trailing stop that follows below (buy) / above (sell) the ATR line, *"an opportunity to input a target or TP"*, closing on the opposite signal, and a version that also runs in the Strategy Tester.

Why the original `EBAKEM_EA_GLORY.mq5` did not trade:

- It needed the ATR break **and** a MACD divergence **and** RSI below 30 (buy) / above 70 (sell) on the **same** candle. When the line breaks upward the RSI is almost never below 30, so there were practically no trades.
- The SuperTrend was rebuilt from only 50 bars on every candle and mixed the upper and lower band, so the line did not match the PZ_SuperTrend on the chart.
- The break was read from the unfinished candle (bar 0 at its first tick).
- `PositionsTotal()` also counted the trades of all other EAs and symbols.

This EA reads the break on the closed candle, builds the SuperTrend line properly and makes the MACD / RSI conditions optional.

## 🖥️ Dashboard & chart

- **On the chart:** SuperTrend line (blue / red, with a gap at every break), MACD window, RSI window, arrows and dotted vertical lines at every signal.
- **Panel:** position, SuperTrend state + distance, candle timer, MACD / RSI gauges with 40-candle strips, filter status, results, chart history simulation, **TRADING ON / PAUSE**, **CLOSE ALL** and link buttons.
- **Alerts:** popup, sound, push, e-mail.

## ⚙️ Key inputs

| Input | What it does |
|---|---|
| Trading timeframe | Current chart by default |
| Lot mode | Fixed lot or risk % (stop = ATR line) |
| SL buffer | Extra distance in points beyond the ATR line |
| Take profit mode | None / points / X × risk / X × ATR |
| Close on opposite signal | On by default, optional stop & reverse |
| MACD / RSI filters | Confirmation modes (default off) and confirm bars |
| Magic number | Use a different one if you run the same pair twice |

## 🛠️ Installation

1. In MT5 choose **File → Open Data Folder → MQL5 → Experts** and copy `TL Glory SuperTrend Pro.ex5` there.
2. Right-click **Expert Advisors** in the Navigator → **Refresh**.
3. Drag the EA onto a chart and enable **Allow Algo Trading**.
4. Tick **Allow DLL imports** only if you want the link buttons (YouTube / RoboForex / WhatsApp / Myfxbook) to open your browser.
5. Use one chart per pair, and a different magic number if you run the same pair twice.

## 🙏 Credits

- Idea: **bush01** in the Forex Factory thread "I will code your EAs and Indicators for no charge" — [post #81,062](https://www.forexfactory.com/thread/post/15565728#post15565728) and [post #81,074](https://www.forexfactory.com/thread/post/15567701#post15567701) (Feb 2026)

## ⚠️ Notes

- A SuperTrend break system is built to catch trends; in sideways ranges it can take many small losing trades. Test on a demo account first — there is no profit promise.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
