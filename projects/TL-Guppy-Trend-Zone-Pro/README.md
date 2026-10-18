<div align="center">

# ⚡ TL Guppy Trend Zone Pro

**Guppy multiple-MA trend zones as EA + indicator with the standard animated canvas panel.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_GuppyTrendZonePro_screenshot.png" alt="TL Guppy Trend Zone Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Guppy Trend Zone Pro Indicator.ex4`](MT4/TL%20Guppy%20Trend%20Zone%20Pro%20Indicator.ex4) |
| **MT4** | [`TL Guppy Trend Zone Pro.ex4`](MT4/TL%20Guppy%20Trend%20Zone%20Pro.ex4) |
| **MT5** | [`TL Guppy Trend Zone Pro Indicator.ex5`](MT5/TL%20Guppy%20Trend%20Zone%20Pro%20Indicator.ex5) |
| **MT5** | [`TL Guppy Trend Zone Pro.ex5`](MT5/TL%20Guppy%20Trend%20Zone%20Pro.ex5) |

> Compiled build only — source code is not published.

## Overview

What it is An independent EA + indicator built from the rules that are PUBLICLY described in the ANTSSYS "SuperGuppy" user guide (Daryl Guppy's GMMA concept). It is NOT the original ANTS software: the ANTS signal itself and the "Traders ATR" stop are proprietary and not published, so they are replaced here by clearly defined, open rules. No code or files of the original are used.

The building blocks (as described in the guide)
- **Candle colour** — green  = EMA 60 AND WMA 60 above the 300 EMA (uptrend) red    = both below (downtrend) yellow = mixed - heads-up, the trend may be changing GMMA            Guppy multiple moving averages: fast group 3,5,8,10,12,15 / slow group 30-60 Zone            a band around the 300 EMA (guide: 10 pips each side). Default here: 1 x ATR(14) each side, so it works on every symbol (gold, indices, JPY pairs). Fixed pips selectable. Filters         stochastic oversold / overbought, MACD direction (both optional, like in the guide) ADR levels      25 / 50 / 75 / 100 % of the average daily range (5 days) from today's low and high

The signal (my open replacement for the proprietary ANTS arrow)
- **BUY** — 1. candle colour is green
  - price pulled back into the zone in the last 5 bars and did not close below it
  - a candle closes back ABOVE the whole GMMA fast group (trigger)
  - MACD main above its signal line (filter, default on) optional: stochastic was oversold in the last 5 bars, whole slow GMMA group above the 300 EMA SELL exact mirror (red, zone touch from below, close below the fast group, MACD below signal) Signals use closed bars only - they never repaint.

Trade management of the EA
- **Stop loss** — beyond the low / high of the last 5 bars + 0.2 ATR (or a fixed ATR multiple) Take profit  ADR 100 % level (BUY: today's low + ADR, SELL: today's high - ADR). If that target is less than 1R away the day's move is used up -> trade skipped (or: use a 2R target / trade without TP - input) Trailing     ATR trailing stop (2.5 ATR from the best close) once the trade is +1R Colour exit  a long closes when a candle closes red, a short when it closes green Lots         1 % risk of the balance per trade (or fixed lots), one trade at a time

Installation
- **MT5: MT5\Experts\TL Guppy Trend Zone Pro.ex5** — -> File > Open Data Folder > MQL5\Experts MT5\Indicators\TL Guppy Trend Zone Pro Indicator.ex5 -> MQL5\Indicators (optional, for manual use) The MT5 EA already contains the indicator and draws it on the chart by itself. MT4: MT4\Experts\TL Guppy Trend Zone Pro.ex4            -> MQL4\Experts MT4\Indicators\TL Guppy Trend Zone Pro Indicator.ex4 -> MQL4\Indicators In MT4 attach the indicator to the same chart for the drawing (MT4 EAs cannot add indicators). Restart the terminal or right-click the Navigator > Refresh. Enable "Allow DLL imports" if you want the YouTube / RoboForex / WhatsApp / Forex Factory buttons to open links (the EA trades without it).

On the chart (indicator) Coloured candles (green / red / yellow), blue fast GMMA, orange slow GMMA, thick orange 300 EMA with the dotted zone, arrows = signals, grey lines = today's ADR levels, info strip with buttons. Data window / EA buffers: "Signal" (+1 buy, -1 sell, 0) and "Colour" (+1, -1, 0).

Dashboard (EA) trend colour, EMA/WMA 60 vs 300, GMMA state, zone + price position, a BUY | SELL checklist of every condition on the last closed bar, last signal and why it was (not) traded, ADR used today, ADR targets, stop / target / trailing settings, position, results, auto trading on/off, close all.

Main inputs Timeframe, base EMA (300), trend MA (60), GMMA groups, zone mode ATR / pips, trigger (fast GMMA reclaim or breakout candle), filters on/off (colour, zone, slow GMMA, stochastic, MACD), stop mode, ADR days / level / min. reward:risk, R target, trailing on/off + distance + start, colour exit, risk % or fixed lots, max. open trades, max. spread, magic, alerts.

Risk warning: no profit promise - trading involves high risk. Test on a demo account first.

trader.lifestyle - free tools thread on Forex Factory: <https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4>

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
