<!-- auto-generated: remove this line after hand-editing so publish keeps your text -->
<div align="center">

# ⚡ TL Signal Bands Pro

**Centred TMA signal bands with band-touch signals, band ladder and an optional companion EA.**

![version](https://img.shields.io/badge/version-v1.10-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Signal_Bands_Pro_tlsbp_shot_M5_s1.png" alt="TL Signal Bands Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT5** | [`TL Signal Bands EA.ex5`](MT5/TL%20Signal%20Bands%20EA.ex5) |
| **MT5** | [`TL Signal Bands Pro.ex5`](MT5/TL%20Signal%20Bands%20Pro.ex5) |

> Compiled build only — source code is not published.

## Overview

refresh the Navigator. The EA carries the indicator inside - it works alone as well. Enable "Allow DLL imports" only if you want the RoboForex / WhatsApp / YouTube / FF buttons to open links.

## Indicator

- Triangular moving average (TMA, half-length 60, typical price) with three bands per side: TMA +/- ATR(100, shifted 10 bars) x 2.4 (dotted) / 3.0 / 3.6.
- Buy (green) / sell (red) circles on the CLOSED bar - they never move or disappear.
- v1.10 signal logic (less noise, circles really at the bands):
- the signal bar itself must reach the middle band (3.0 x ATR) of that bar,
- a rejection candle (opposite colour, close back inside) within 2 bars of the touch,
- buy and sell alternate, no signal against a steep TMA (> 0.30 ATR per 10 bars).
- Band mode "Centered" (video look) recalculates the last 60 bars of the BANDS. "Real-time" never changes.
- Dashboard (collapsible, click the title or MIN): signal state, band ladder, market, live signal check, band scope, historical check (EA rule, 0.01 lot) and the live EA / martingale state.

EA
- Opens a trade on every circle (entry at the bar close).
- Exit: price touches the opposite inner band (2.4 x ATR) OR the next (opposite) circle closes and reverses the trade.
- Martingale (optional, default ON): after a losing trade the lot is multiplied (x2) until a trade closes in profit, max 6 steps, max lot 1.00. Optional hard stop (x ATR) and equity stop (%).
- WARNING: there is no stop loss by default (like the video). Martingale without a stop can wipe out an account. Always test on a demo first.
No lock, no expiry. Not financial advice - backtests are no promise.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
