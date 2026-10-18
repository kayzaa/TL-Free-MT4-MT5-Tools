<div align="center">

# ⚡ TL Volume Fib Sniper Pro

**Volume profile + Fibonacci sniper entry automated: impulse profile, 0.5–0.618 entry zone with volume, target at the 1.618 extension.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_VolumeFibSniperPro_screenshot.png" alt="TL Volume Fib Sniper Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Volume Fib Sniper Pro.ex4`](MT4/TL%20Volume%20Fib%20Sniper%20Pro.ex4) |
| **MT5** | [`TL Volume Fib Sniper Pro.ex5`](MT5/TL%20Volume%20Fib%20Sniper%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- 🎯 **Volume Profile + Fibonacci = sniper entry** — every step of the popular method is automated.
- 📊 **Fixed-range volume profile of the impulse** — POC and 70 % value area, split into up / down candle volume.
- 🟩 **Volume-confirmed entry zone** — 0.5–0.618 is armed only when the volume backs it up.
- 🔒 **Closed bars only** — no repaint.
- 🧩 **Two modes** — "EA" (trades) or "Indicator mode only" (never trades).
- 🖥️ **Setup stepper dashboard** — watch each step light up from swing high to entry.

## 🧠 Strategy rules

Made for gold (**XAUUSD**), recommended timeframes **H1 and H4**; it runs on every symbol. Long setup shown — shorts are the exact mirror. One trade at a time.

| Step | Name | Rule |
|---|---|---|
| **1** | SWING HIGH | Confirmed pivot high (10 bars left / 5 bars right, inputs) = end of the impulse |
| **2** | SWING LOW | Lowest low since the previous swing high = start of the impulse (impulse must be ≥ 4 ATR — input) |
| **3** | VOLUME | Fixed-range volume profile from the swing low to the swing high (tick volume, teal = up candles, magenta = down candles), POC + 70 % value area |
| **4** | FIBONACCI | Swing high (0) → swing low (1), levels 0.236 / 0.382 / 0.5 / 0.618 / 0.786 |
| **5** | ENTRY ZONE | 0.5–0.618, armed only when the volume confirms it: POC within 10 % of the swing range from the zone OR the zone inside the value area (filter: off / POC / value area / either / both) |
| **6** | TRADE | LIMIT order at 0.5 (default) or a confirmation candle (touch + close back out of the zone) |

> **Stop loss** 0.65 (just beyond 0.618) · **TP1** = swing high (50 % closed + break-even) · **Target** = 1.618 extension. All levels are inputs.

**A setup ends** when price makes a new extreme beyond the swing, when it waits longer than 60 bars, when a newer swing takes over, or when price already reached the zone before the swing was confirmed.

## 🖥️ Dashboard & chart

**On the chart** (like in the video): "Swing High" / "Swing Low" lines, the volume profile box with POC / VAH / VAL, the Fibonacci bands with prices, the green "Entry Long" / red "Entry Short" zone, "Stop-loss" and "Target" lines, position boxes (target / stop, open or closed P&L, risk/reward), BUY / SELL pills with the planned risk/reward and exit tags. Past trades are drawn compact. Everything follows scroll and zoom.

**Dashboard** (drag the header, **X** folds it to a pill; hover any block for the details):
- **SETUP** stepper — SW HIGH → SW LOW → VOLUME → FIB → ZONE → ENTRY
- **VOLUME PROFILE** with a live mini profile
- **FIBONACCI** ladder with the live price
- **TRADE PLAN**
- **VIRTUAL RESULTS** of the history
- **POSITION / INDICATOR MODE** — pending order, Auto Trading on/off, Close All
- Rotating rule card

## 🔔 Alerts

New setup armed, entry, TP1 and exit — popup, sound, push and e-mail (inputs).

## 🛠️ Installation

1. **MT5:** copy `TL Volume Fib Sniper Pro.ex5` to `File → Open Data Folder → MQL5 → Experts`.
   **MT4:** copy `TL Volume Fib Sniper Pro.ex4` to `File → Open Data Folder → MQL4 → Experts`.
2. Refresh the Navigator and drag the EA onto a chart.
3. For auto trading enable **Algo Trading** / **Allow live trading**. For signals only, choose "Indicator mode only".
4. **Allow DLL imports** is only used to open the links of the dashboard buttons.

## ⚠️ Notes

- The virtual results in the panel are a simple bar simulation without spread / commission — a rough guide, not a full simulation of real trading.
- Built for gold H1 / H4; other symbols may need their own settings.
- Test on a demo account first and use your own judgement.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
