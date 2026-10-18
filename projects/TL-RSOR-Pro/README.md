<!-- auto-generated: remove this line after hand-editing so publish keeps your text -->
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

## Overview

RSOR = RobinHood Stochastics Oscillator RSI. Built after RobinHood's RSOR from the Forex Factory thread "Trading Made Simple(r)" (post #11,434) and the rules RobinHood, pewebly and StonebankS1 posted there. All credit for the method goes to them.

## Files

- MT5/Experts/TL RSOR Pro.ex5               EA - Mode "EA" (trades) or "Indicator only" (never trades)
- MT5/Indicators/TL RSOR Pro Indicator.ex5  real indicator in its own window (buffers for iCustom)
- MT4/Experts/TL RSOR Pro.ex4               same EA for MT4 MT4/Indicators/TL RSOR Pro Indicator.ex4  same indicator for MT4

- Install: File -> Open Data Folder -> copy the files into MQL5 (MQL4) /Experts and /Indicators, refresh the Navigator. Allow DLL imports (only used to open the links of the dashboard buttons).

## The Three Lines (one lower window)

Cyan       Stochastic 34,10,3 EMA  -> trend gate (long only above ~60, short below 40) Dark blue  RSI(4) of the 14 EMA    -> trigger, pegs FLAT at 100 / 0 (RobinHood's exact sum formula) Orange     Stochastic 8,3,3 EMA    -> exits + divergence Zones: GREEN 70-100, PURPLE 40-60, RED 0-30.

## Entries (closed bars only - no repaint)

KICK    One Best Kick: cyan > 60 and rising, dark blue flat at 100, dips any amount, back flat at 100 = enter long. Shorts are the exact mirror at 0. 50X     First cross of the 50 area after the dark blue line left the red / green zone.

## Star    (optional) orange and dark blue cross the cyan line, dark blue beyond 50.

Filters: RoadMap EMA (default), EMA stack, higher timeframes (MTF boxes > / < 50).

## Exits And Trade Management

ALWAYS rule      exit when the dark blue line goes from FLAT to NOT FLAT (on / only after TP1 / off) Orange exits     one of the 5 variations: below 90 / 80 / 70, through cyan, dark blue below 90 Zone leave       dark blue leaves its zone (default for 50X / sniper / star trades) 2R trail         StonebankS1: at +2R with the long stoch > 80, exit when it drops below 70 TP1              default 1R: 50 % closed, stop to break-even TP2              default 2R: final target Smart trailing   from +0.7R: best price since the entry - 2 ATR (or swing low / high), only tightens Stop loss        behind the swing of the last 10 bars + 0.2 ATR (or ATR multiple)

## Position / Indicator Mode - rotating rule card. Hover any block for the details.

The RSOR window is docked at the bottom of the chart (EA) or in its own window (indicator): zones, flat segments, signals, exits, live values, MTF tiles.

## Indicator Buffers (iCustom)

0 dark blue, 1 orange, 2 cyan, 3 signal (+-1 kick, +-2 50x, +-3 sniper, +-4 star), 4 exit reason of the virtual trade, 5 virtual trade direction.

## Note

---- The virtual results in the panel are a bar simulation without spread / commission - a guide, not a backtest. As pewebly said in the thread: the raw rules alone are not enough - test on a demo account first and use your own judgement.

trader.lifestyle

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
