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

## Overview

rebuilt as ONE expert advisor for MT4 and MT5. No extra indicators needed.

## What You See On The Chart (M1 chart, like the original template)

- The normal candles and volumes are hidden (restored when you remove the EA).
- M5 Heiken Ashi drawn on the M1 chart as a teal / red band (interpolated like heiken_ashi_-_mtf_on_chart_nmc) -> you see the M5 breaks and direction on M1.
- Yellow line = MA(1) close (price as a line, "less deceiving than the candles").
- Buzzer(54) trend line: cyan = up, red = down.
- Step One More Average arrows (lime up / orange down) = pullback over.
- Entry signals: big arrows with "PB" (pullback) or "RIDE" (M5 flip).
- Dashboard: M5 HA bias + last 26 M5 candles, signal stack, confluence gauge, MOMENTUM window (SMI 13,25,2,5 + fast stochastic 14,3,3 - the indicator window of the template), auto-trade block with ON/OFF button. Click X to close it to a pill, click the pill to reopen, drag the header to move it.

## Rules (defaults) - only the Big moves, held until the change

- Bias = colour of the last COMPLETED M5 Heiken Ashi candle (no repaint).
- Entry only on a new M5 Heiken Ashi flip when the M15, H1 and H4 Heiken Ashi candles point the same way AND volatility is above the daily average (ATR(50) / ATR(1440) >= 1). Shown in the dashboard as "BIG MOVE LONG / SHORT".
- No target, no break-even: the trade rides until the M5 Heiken Ashi flips back.
- Emergency stop 4 x ATR(50). Risk 0.5 % per trade (input).
- Other modes (pullback / both) and the Buzzer / SMI / stochastic filters are inputs.

## Install

- MT5: copy TL HA MTF Rider Pro.ex5 to MQL5\Experts, MT4: the .ex4 to MQL4\Experts.
- Allow algo trading. The buttons (YouTube / RoboForex / WhatsApp / Forex Factory)
- need "Allow DLL imports".

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
