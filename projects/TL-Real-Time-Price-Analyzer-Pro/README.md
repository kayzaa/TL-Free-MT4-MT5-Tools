<!-- auto-generated: remove this line after hand-editing so publish keeps your text -->
<div align="center">

# ⚡ TL Real Time Price Analyzer Pro

**TheRumpledOne's Real Time Price Analyzer rewritten: 16 levels of the forming bar and how often past bars touched them.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Indicator-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_RealTimePriceAnalyzerPro_screenshot.png" alt="TL Real Time Price Analyzer Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Real Time Price Analyzer Pro.ex4`](MT4/TL%20Real%20Time%20Price%20Analyzer%20Pro.ex4) |
| **MT5** | [`TL Real Time Price Analyzer Pro.ex5`](MT5/TL%20Real%20Time%20Price%20Analyzer%20Pro.ex5) |

> Compiled build only — source code is not published.

## Overview

Idea: TheRumpledOne's "Real Time Price Analyzer" (2017). This is an independent rewrite with the bugs of the original fixed.

## What It Does

For the bar that is forming right now (analysis timeframe = chart, H1, H4, D1, W1 ...) it builds up to 16 levels from the previous bar: classic pivots PP, R1-R6, S1-S6 and the mid levels between them, previous bar open / high / mid / low / close / body top / body bottom, fib % of the previous range, the open of the forming bar, fixed prices.

Then it answers: where is price right now - and how often did the past N bars touch or close beyond the SAME levels of their own bar?

## Panel

- PRICE POSITION   bid, the zone it is in (nearest level below -> above), zone gauge, distance in pips and in % of the average bar range, range used so far, countdown to the close
- HISTORICAL ODDS  for the two nearest levels above and below: HIGH > level (touch), CLOSE > level, CLOSE inside the current zone, CLOSE < level, LOW < level. HIT = the forming bar already did it; the close row then shows how often a touch turned into a close beyond. n = sample size, +/- = 95 % margin of error
- LEVEL LADDER     every level sorted by price: price, pips away, touch %, close-beyond % (hover: held after a touch)
- CONTROLS         analysis bar (CHART / H1 / H4 / D1 / W1), sample (ALL BARS / SAME OPEN ZONE), number of bars, lines on/off
The panel closes to a pill (X), opens again with one click, can be dragged anywhere, moves out of the way of other trader.lifestyle panels and keeps its place per chart. Hover any row for an explanation.

## Chart

Level lines of the forming bar (nearest levels thicker, touched levels magenta) with labels "R1 1.08423  T 35%  C 18%". Optional: levels of the previous N bars.

## Sample Modes

ALL BARS        every past bar counts (like the original) SAME OPEN ZONE  only past bars that opened between the same two levels as the forming bar did - fewer bars, closer situations

## Inputs (most important)

Analysis bar timeframe   current = chart timeframe, D1 = classic daily pivots Number of past bars      10 - 5000 (limited by the loaded history) Skip the newest N bars   1 = closed bars only (default), 0 = include the forming bar like the original D1: ignore Sunday bars   Monday levels from Friday; switched off automatically for 7-day markets (crypto) Level 1-16 + value       value = offset in pips for pivots / bar levels, % for "Previous bar fib %", price for "Fixed price" (a fixed price of 0 = not used). Pips: 5/3-digit FX = 10 points, gold = 0.10, everything else = 1 point Alerts                   price crosses a level (popup / sound / push / mail), once per level, direction and bar

## For EA Builders (iCustom, newest bar)

0 level above price   1 level below price   2 above: touch % 3 above: close beyond %   4 below: touch %   5 below: close beyond % 6 close inside zone %     7 sample size Input "Draw on the chart" = false: a hidden buffers-only copy for your EA - it draws nothing and never touches the objects / panel choices of a visible copy. A 2nd VISIBLE copy on the same chart needs its own "instance id" (1, 2 ...). No sample (n = 0) -> buffers 2-6 are EMPTY_VALUE, never a fake 0 %.

## Fixed Compared With The Original (Tro 2017)

- crash / garbage when price is above the highest or below the lowest level or between the two lowest levels (array index out of range)
- row "LOW LT ..." counted a different level than its label showed
- level "R4R6" never worked (it is the R3-R4 mid level)
- the forming bar was counted in its own statistics
- levels that use the forming bar's own high / low / close (always true or never true in the statistics) and CURRPRICE removed
- bars that do not exist in the history were counted as samples
- Sunday bars of the broker distorted Monday's daily pivots
- prices were shown with one digit less on 5 / 3 digit symbols
- pips for gold, indices and crypto
- a "FIXEDPRICE" slot left at 0 created a level at 0.00
- two copies on one chart deleted each other's objects (tag 1 vs 10)
- objects left on the chart after removing the indicator
- layout broke in the lower corners and with bigger fonts

## Install

- MT5: copy the .ex5 to  MQL5\Indicators\   MT4: copy the .ex4 to  MQL4\Indicators\ Restart the terminal or right-click "Refresh" in the Navigator, drag it on a chart. No DLL needed.

- Statistics describe the past - they are no promise for the future.
- Not financial advice.  trader.lifestyle

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
