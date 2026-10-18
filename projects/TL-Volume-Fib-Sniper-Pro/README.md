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

## Overview

Volume Profile + Fibonacci = sniper entry. Every step of the popular "sniper entry" method is automated: swing high, swing low, fixed-range volume profile of the impulse, fibonacci, entry zone 0.5 - 0.618 where the volume confirms, stop beyond 0.618, target = 1.618 extension. Made for gold (XAUUSD) - recommended timeframes H1 and H4. Works on every symbol.

## Files

- MT5/Experts/TL Volume Fib Sniper Pro.ex5   EA - Mode "EA" (trades) or "Indicator mode only" (never trades)
- MT4/Experts/TL Volume Fib Sniper Pro.ex4   same EA for MT4

- Install: File -> Open Data Folder -> copy the file into MQL5 (MQL4) /Experts, refresh the Navigator.
- Allow DLL imports (only used to open the links of the dashboard buttons). For auto trading also enable "Algo Trading" / "Allow live trading".

## The Six Steps (closed bars only - no repaint)

1 SWING HIGH   confirmed pivot high (10 bars left / 5 bars right, inputs) = end of the impulse 2 SWING LOW    lowest low since the previous swing high = start of the impulse (impulse must be >= 4 ATR - input) 3 VOLUME       fixed-range volume profile from the swing low to the swing high (tick volume, teal = up candles, magenta = down candles), POC + value area 70 % 4 FIBONACCI    swing high (0) -> swing low (1), levels 0.236 / 0.382 / 0.5 / 0.618 / 0.786

## 5 Entry Zone   0.5 - 0.618. Armed only when the volume confirms it:

POC within 10 % of the swing range from the zone OR the zone inside the value area (filter: off / POC / value area / either / both) 6 TRADE        LIMIT order at 0.5 (default) or a confirmation candle (touch + close back out of the zone) Stop loss 0.65 (just beyond 0.618), TP1 = swing high (50 % closed + break-even), target = 1.618 extension. All levels are inputs. Shorts are the exact mirror. One trade at a time.

A setup ends when price makes a new extreme beyond the swing, when it waits longer than 60 bars, when a newer swing takes over or when price already reached the zone before the swing was confirmed.

## On The Chart (like in the video)

"Swing High" / "Swing Low" lines, the volume profile box with POC / VAH / VAL, the fibonacci bands with prices, the green "Entry Long" / red "Entry Short" zone, "Stop-loss" and "Target" lines, the position boxes (target / stop, open or closed P&L, risk/reward), BUY / SELL pills with the planned risk/reward, exit tags. Past trades are drawn compact. Follows scroll and zoom.

## Dashboard (drag the header, X folds it to a pill)

SETUP stepper (SW HIGH -> SW LOW -> VOLUME -> FIB -> ZONE -> ENTRY) - VOLUME PROFILE with a live mini profile - FIBONACCI ladder with the live price - TRADE PLAN - VIRTUAL RESULTS of the history -

## Position / Indicator Mode (pending order, Auto Trading on/off, Close All) - rotating rule card.

Hover any block for the details.

## Alerts

New setup armed, entry, TP1, exit - popup, sound, push, e-mail (inputs).

## Note

---- The virtual results in the panel are a bar simulation without spread / commission - a guide, not a backtest. Test on a demo account first and use your own judgement.

trader.lifestyle

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
