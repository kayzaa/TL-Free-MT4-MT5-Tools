<div align="center">

# ⚡ TL RSOR Pro

**RSOR suite — indicator and EA from one ruleset, with signal markers and trade panel.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_RSOR_Pro_screenshot.png" alt="TL RSOR Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL RSOR Pro Indicator.ex4`](MT4/TL%20RSOR%20Pro%20Indicator.ex4) |
| **MT4** | [`TL RSOR Pro.ex4`](MT4/TL%20RSOR%20Pro.ex4) |
| **MT5** | [`TL RSOR Pro Indicator.ex5`](MT5/TL%20RSOR%20Pro%20Indicator.ex5) |
| **MT5** | [`TL RSOR Pro.ex5`](MT5/TL%20RSOR%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **RSOR = RobinHood Stochastics Oscillator RSI** — built after RobinHood's RSOR from the Forex Factory thread "Trading Made Simple(r)".
- **One ruleset, two tools:** an EA (trading or "Indicator only" mode) plus a standalone indicator with iCustom buffers.
- **Four entry types** — KICK, 50X, Star and sniper — on closed bars only, no repaint.
- **Rich exit toolkit:** the ALWAYS rule, orange exits, zone leave, 2R trail, TP1 / TP2 and smart trailing.
- **Multi-timeframe tiles** and a rotating rule card on the panel.
- **MT4 + MT5.**

## 📦 What's included

| File | What it is |
|---|---|
| `TL RSOR Pro.ex5` / `.ex4` | EA — mode **"EA"** (trades) or **"Indicator only"** (never trades) |
| `TL RSOR Pro Indicator.ex5` / `.ex4` | Real indicator in its own window (buffers for iCustom) |

## 🧠 Strategy rules

### The three lines (one lower window)

| Line | Calculation | Role |
|---|---|---|
| **Cyan** | Stochastic 34,10,3 EMA | Trend gate (long only above ~60, short below 40) |
| **Dark blue** | RSI(4) of the 14 EMA | Trigger — pegs **flat** at 100 / 0 (RobinHood's exact sum formula) |
| **Orange** | Stochastic 8,3,3 EMA | Exits + divergence |

Zones: **green** 70–100, **purple** 40–60, **red** 0–30.

### Entries (closed bars only — no repaint)

- **KICK — One Best Kick:** cyan > 60 and rising, dark blue flat at 100, dips any amount, back flat at 100 = enter long. Shorts are the exact mirror at 0.
- **50X:** first cross of the 50 area after the dark blue line left the red / green zone.
- **Star** (optional): orange and dark blue cross the cyan line, dark blue beyond 50.
- **Filters:** RoadMap EMA (default), EMA stack, higher timeframes (MTF boxes > / < 50).

### Exits & trade management

| Rule | What it does |
|---|---|
| **ALWAYS rule** | Exit when the dark blue line goes from flat to not flat (on / only after TP1 / off) |
| **Orange exits** | One of 5 variations: below 90 / 80 / 70, through cyan, dark blue below 90 |
| **Zone leave** | Dark blue leaves its zone (default for 50X / sniper / star trades) |
| **2R trail** (StonebankS1) | At +2R with the long stoch > 80, exit when it drops below 70 |
| **TP1** | Default 1R: 50 % closed, stop to break-even |
| **TP2** | Default 2R: final target |
| **Smart trailing** | From +0.7R: best price since the entry − 2 ATR (or swing low / high), only tightens |
| **Stop loss** | Behind the swing of the last 10 bars + 0.2 ATR (or ATR multiple) |

## 🖥️ Dashboard & chart

- Position / indicator mode with a **rotating rule card** — hover any block for the details.
- The RSOR window is docked at the bottom of the chart (EA) or in its own window (indicator): zones, flat segments, signals, exits, live values and MTF tiles.

## 🔌 Indicator buffers (iCustom)

| Buffer | Content |
|---|---|
| 0 | Dark blue |
| 1 | Orange |
| 2 | Cyan |
| 3 | Signal (±1 kick, ±2 50x, ±3 sniper, ±4 star) |
| 4 | Exit reason of the virtual trade |
| 5 | Virtual trade direction |

## 🛠️ Installation

1. In your terminal open **File → Open Data Folder**.
2. **MT4:** copy `TL RSOR Pro.ex4` to `MQL4 → Experts` and `TL RSOR Pro Indicator.ex4` to `MQL4 → Indicators`.
   **MT5:** copy `TL RSOR Pro.ex5` to `MQL5 → Experts` and `TL RSOR Pro Indicator.ex5` to `MQL5 → Indicators`.
3. Refresh the Navigator and drag the EA or the indicator onto a chart.
4. Optional: allow **"Allow DLL imports"** — only used to open the links of the dashboard buttons.

## 🙏 Credits

Built after **RobinHood's** RSOR from the Forex Factory thread "Trading Made Simple(r)" (post #11,434), and the rules **RobinHood**, **pewebly** and **StonebankS1** posted there. All credit for the method goes to them.

## ⚠️ Notes

- The virtual results in the panel are a simple bar simulation without spread / commission — a guide only.
- As pewebly said in the thread: the raw rules alone are not enough — test on a demo account first and use your own judgement.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
