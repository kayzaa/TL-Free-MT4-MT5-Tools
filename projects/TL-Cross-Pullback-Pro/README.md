<div align="center">

# ⚡ TL Cross Pullback Pro

**AlistairC's 8/21 EMA cross-and-pullback method, automated with a clean signal and trade panel.**

![version](https://img.shields.io/badge/version-v1.10-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/Cross%20Pullback%20Pro%20-%20XAUUSD%20H4.png" alt="TL Cross Pullback Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Cross Pullback Pro.ex4`](MT4/TL%20Cross%20Pullback%20Pro.ex4) |
| **MT5** | [`TL Cross Pullback Pro.ex5`](MT5/TL%20Cross%20Pullback%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **AlistairC's EMA 8 / 21 / 55 system** — Trend Cross Breakout plus inside bar and 2-bar pullback setups, independently coded from scratch.
- **Two entry types** — a breakout close beyond EMA 55, or a stop order beyond a pullback box.
- **Higher timeframe filter** — EMA 8/21 on D1 (by default) must agree.
- **Exit like the original** — close at the top of the next hour when EMA 8 crosses back over EMA 21; no fixed target by default, ride the trend.
- **Traffic-light panel** — MTF trend matrix, every condition as a light, armed orders and the current phase.
- **Signals only mode** — let the EA spot the setups and judge them yourself.

## 🆕 What's new in v1.10 (closer to the original system)

- EMA 8 / 21 / 55 instead of 8 / 21 only.
- **Entry 1 "Trend Cross Breakout":** the 8/21 cross primes a new trend; the **first** candle that closes beyond EMA 55 is the entry (at its close).
- **Entry 2:** inside bar (mother candle + one or more candles fully inside it) and 2-bar pullback (lower high **and** lower low in an uptrend) within 15 bars of the cross, max 1.5 ATR, stop order beyond the box, stop on the other side.
- Higher timeframe EMA 8/21 filter (D1 by default).
- Exit like the original: when EMA 8 crosses back over EMA 21 the trade is closed at the top of the next hour (not waiting for the H4 close), plus a fixed stop from the entry. No fixed target by default.
- No order traffic during the broker's daily break (gold 00:00 – 01:05).

## 🧠 Strategy rules

### 1. Trend Cross Breakout

> EMA 8 crosses EMA 21 → **primed**. The first close beyond EMA 55 in the same direction → **enter at the close**.

- Stop beyond the swing of the last 10 bars + ATR buffer.
- Options: the signal candle must really cross EMA 55, skip explosive signal candles, signal only within N bars of the cross.

### 2. Inside Bar / 2-Bar Pullback

> Within 15 bars of the 8/21 cross: **STOP order beyond the setup box**, stop on the other side of the box.

- A new inside bar of the same mother candle keeps the order; it expires after N bars or when the trend flips.
- Price already beyond the trigger: market entry up to X ATR away, otherwise the setup is skipped.

### Filters

- Higher timeframe EMA 8/21 must agree (closed bars of that timeframe).
- Optional: EMA 55 slope with the trend, anti-chop efficiency ratio, long / short only.

### Exit

- 8/21 cross back → close at the top of the next hour (or at once).
- Optional: close when a candle closes on the wrong side of EMA 21.
- Fixed stop from the entry, optional target in R, break-even, partial close, ATR or EMA trailing.

## 🖥️ Dashboard & chart

- **MTF trend matrix (H1 / H4 / D1 / W1):** 8/21 trend, "ALL 3" when 8/21/55 are fully aligned, bars since the cross, stretch from EMA 21 in ATR.
- **Trend Cross Breakout block:** every condition as a traffic light, pattern on the last bar, armed order with SL, exit status and phase (PRIMED / BREAKOUT SIGNAL / ARMED / ORDER WAITING / IN TRADE).
- **Signal track record** on your chart history (bar based, no costs).
- **Controls:** auto trading ON / signals only, close EA trades, daily guard, statistics.
- **On the chart:** EMA 8 / 21 / 55, setup box + trigger / SL lines, entry arrows and R result tags.

## 🛠️ Installation

1. In MetaTrader open **File → Open Data Folder**.
2. **MT4:** copy `TL Cross Pullback Pro.ex4` into `MQL4 → Experts`. **MT5:** copy `TL Cross Pullback Pro.ex5` into `MQL5 → Experts`.
3. Refresh the Navigator, drag the EA onto a chart and allow Algo Trading.
4. Made for **H4** (higher timeframe = D1). On H1, set the higher timeframe to H4.
5. **"Allow DLL imports"** is only needed for the link buttons in the panel.

## ⚠️ Notes

- No performance promises. Trading is risky — test on a demo account first.
- The original system also relies on the trader's eye (clean EMA fan, no trading into S/R, safety checklist). Use **signals only** and judge each setup yourself.
- The signal track record is bar based and ignores costs — it is a quick visual check, not a forecast.

## 🙏 Credits

Written from scratch by trader.lifestyle — own code. The trading rules follow **AlistairC**'s EMA 8 / 21 / 55 approach ("Trend Cross Breakout" + inside bar and 2-bar pullback setups) from his Forex Factory thread **"MA Crossover System that works for me"**. Big thanks to him for sharing.

## 🖼️ More screenshots

<img src="screenshots/TL_CrossPullbackPro_FF.png" width="49%">
<img src="screenshots/TL_CrossPullbackPro_v110_FF.png" width="49%">

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
