<div align="center">

# ⚡ TL Big Bull Fire EA

**The BigBull System 2.0 chart setup rebuilt as a fully automated Expert Advisor with visual trade management.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_BigBullFireEA_screenshot.png" alt="TL Big Bull Fire EA" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Big Bull Fire EA.ex4`](MT4/TL%20Big%20Bull%20Fire%20EA.ex4) |
| **MT5** | [`TL Big Bull Fire EA.ex5`](MT5/TL%20Big%20Bull%20Fire%20EA.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- 🐂 **The BigBull System 2.0 template, fully automated** — the EA calculates the whole system on every closed candle and trades its arrows.
- 🔁 **Stop-and-reverse logic** — an opposite arrow closes the open trade and (optionally) opens the new direction.
- 🧭 **Trend filter on by default** — buys only above the magenta trend line, sells only below.
- 🔒 **No repaint** — arrows are calculated on closed candles only.
- 🔥 **A chart like no other** — an animated 3D bull behind the candles that snorts fire, plus an optional full view of clouds, lines and histograms.
- 📰 **Built-in risk tools** — fixed lot or % risk, ATR stops and targets, break-even, daily profit target and an optional news filter.

## 🧠 Strategy rules

| Signal | Condition | Action |
|---|---|---|
| **BUY arrow** | The yellow signal line turns up | Close sell, open buy |
| **SELL arrow** | The yellow signal line turns down | Close buy, open sell |

> **Trend filter (ON by default):** buys only above the magenta trend line, sells only below. An arrow against the trend still closes the open trade, but does not open a new one.

- **Cloud filter** — optional extra filter (off by default).
- **Start behaviour** — wait for the next arrow, or enter the current one.
- **Stop Loss / Take Profit** — in ATR; `0` means exit on the opposite arrow.
- **Break-even** — in ATR.
- **Daily profit target** — `0` = off. Once reached, the EA stops for the day (optionally closing the open trade).
- **News filter** — off by default. Blocks new trades around high / medium impact news of the symbol's currencies.

## 🖥️ Dashboard & chart

By default the chart stays clean: candles, BUY / SELL arrows and the animated fire-breathing 3D bull. The system lines are always calculated in the background — switch them on if you want to see them:

- **Clouds / zones** — fast lime/yellow, mid purple/green, slow blue/salmon cloud
- **Lines** — rainbow EMAs, yellow signal line, magenta trend line
- **Histograms** — power + momentum histogram at the bottom

The panel shows trend state, candle countdown, the performance of this EA, an equity curve, settings and a clock. Drag it by the header, `-` collapses it, and on small chart windows it switches to a compact layout automatically. Hover any section for an English tooltip (tooltips can be turned off).

## ⚙️ Key inputs

| Input | What it does |
|---|---|
| Yellow signal line period (`80`) | Arrows appear at its turns — higher = fewer arrows |
| Magenta trend line period (`200`) | Trend line used by the trend filter |
| Auto trading on arrows (`true`) | `false` = signals only |
| Start behaviour | Wait for the next arrow / enter the current one |
| Opposite arrow closes AND reverses (`true`) | Stop-and-reverse on every opposite arrow |
| Trend filter (`true`) / Cloud filter (`false`) | Entry filters |
| Fixed lot or % risk | Risk sizing; stop distance = Stop Loss, or 3 × ATR without a Stop Loss |
| Stop Loss / Take Profit (ATR) | `0` = exit on the opposite arrow |
| Break-even (ATR) | Moves the stop to entry |
| Max spread, magic number, comment | Trade housekeeping |
| Daily profit target | `0` = off; stops for the day when reached |
| News filter | Off by default; no new trades around high / medium impact news |
| Design | Fire chart, 3D bull, zones, lines, histograms, panel, FPS, fire intensity, tooltips |

## 🛠️ Installation

1. **MT5:** copy the `.ex5` to `File → Open Data Folder → MQL5 → Experts`.
   **MT4:** copy the `.ex4` to `File → Open Data Folder → MQL4 → Experts`.
2. Refresh the Navigator and drag the EA onto a chart.
3. Enable **Allow Algo Trading**.
4. Enable **Allow DLL imports** only if you want the link buttons to open in your browser.
5. **News filter (MT4 only):** MT4 loads the Forex Factory calendar — allow WebRequest for `https://nfs.faireconomy.media` under `Tools → Options → Expert Advisors`. MT5 uses the built-in economic calendar.

Your own chart colours come back when you remove the EA.

## ⚠️ Notes

- Runs on any symbol and any timeframe; the default settings are made for **XAUUSD M5–H1**. Other symbols may need their own settings.
- Lower the Animation FPS if your PC gets slow (default `15`).
- Free — no lock, no expiry.
- Trading involves risk. Test on a demo account first. This is not investment advice.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
