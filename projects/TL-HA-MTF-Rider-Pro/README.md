<div align="center">

# ⚡ TL HA MTF Rider Pro

**RplusT's multi-timeframe Heikin Ashi system rebuilt as one EA — no extra indicators needed.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_HA_MTF_Rider_Pro_XAUUSD_M1_hmr_shot.png" alt="TL HA MTF Rider Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL HA MTF Rider Pro.ex4`](MT4/TL%20HA%20MTF%20Rider%20Pro.ex4) |
| **MT5** | [`TL HA MTF Rider Pro.ex5`](MT5/TL%20HA%20MTF%20Rider%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **One EA, whole template** — RplusT's multi-timeframe Heiken Ashi system for MT4 and MT5, no extra indicators needed.
- **M5 Heiken Ashi on M1** — a teal / red band shows the M5 breaks and direction right on the M1 chart.
- **Big moves only (default)** — enter on an M5 flip when M15, H1 and H4 agree and volatility is above the daily average.
- **Ride until the change** — no target, no break-even; the trade runs until the M5 Heiken Ashi flips back.
- **No repaint on the bias** — it uses the last *completed* M5 candle.
- **Full dashboard** — HA bias, signal stack, confluence gauge, momentum window and an auto-trade ON/OFF button.

## 🧠 Strategy rules (defaults)

> Only the big moves, held until the change.

| | Rule |
|---|---|
| **Bias** | Colour of the last **completed** M5 Heiken Ashi candle (no repaint) |
| **Entry** | A new M5 Heiken Ashi flip while the M15, H1 and H4 Heiken Ashi candles point the same way **and** volatility is above the daily average (ATR(50) / ATR(1440) >= 1) — shown as **"BIG MOVE LONG / SHORT"** |
| **Exit** | No target, no break-even: the trade rides until the M5 Heiken Ashi flips back |
| **Emergency stop** | 4 × ATR(50) |
| **Risk** | 0.5 % per trade (input) |

Other entry modes (pullback / both) and the Buzzer / SMI / stochastic filters are available as inputs.

## 🖥️ Dashboard & chart

Built for the M1 chart, like the original template:

- The normal candles and volumes are hidden (restored when you remove the EA).
- **M5 Heiken Ashi band** (teal / red) drawn on M1, interpolated like *heiken_ashi_-_mtf_on_chart_nmc*.
- **Yellow line** = MA(1) close — price as a line, "less deceiving than the candles".
- **Buzzer(54) trend line:** cyan = up, red = down.
- **Step One More Average arrows** (lime up / orange down) = pullback over.
- **Entry signals:** big arrows labelled **PB** (pullback) or **RIDE** (M5 flip).
- **Dashboard:** M5 HA bias + last 26 M5 candles, signal stack, confluence gauge, **MOMENTUM** window (SMI 13,25,2,5 + fast stochastic 14,3,3 — the indicator window of the template) and the auto-trade block with ON/OFF button.
- Click **X** to close the dashboard to a pill, click the pill to reopen, drag the header to move it.

## 🛠️ Installation

1. Choose **File → Open Data Folder**.
2. Copy the file for your platform:
   - **MT4:** `TL HA MTF Rider Pro.ex4` → **MQL4 → Experts**
   - **MT5:** `TL HA MTF Rider Pro.ex5` → **MQL5 → Experts**
3. Refresh the Navigator and drag the EA onto an **M1** chart.
4. Allow algo trading.
5. Tick **Allow DLL imports** only if you want the YouTube / RoboForex / WhatsApp / Forex Factory buttons to work.

## 🙏 Credits

- Original multi-timeframe Heiken Ashi system and template: **RplusT**.

## ⚠️ Notes

- With no target and only an emergency stop, a trade can stay open for a long time and give back open profit before the M5 flip — test on demo first.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
